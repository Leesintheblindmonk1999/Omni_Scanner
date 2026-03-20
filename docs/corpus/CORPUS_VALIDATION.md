# Omni-Scanner Semantic — Validation Corpus v1.0

**Author:** Gonzalo Emir Durante  
**Registry:** EX-2026-18792778 (TAD, Argentina)  
**Zenodo:** [10.5281/zenodo.19052627](https://zenodo.org/records/19052627)  
**Date:** March 2026  

---

## Purpose

This corpus provides ground-truth labeled documents for empirical validation
of the ManifoldScore pipeline and the κD = 0.56 operational threshold.

Each document pair (A/B) is designed so that:
- **Version A** is structurally coherent (expected: ManifoldScore ≥ 0.56, ISI ≈ 1.0)
- **Version B** contains a documented logical hallucination or structural manipulation
  (expected: ManifoldScore < 0.56 or ISI < 0.56 in Semantic Diff A→B)

Ground truth is established by the author at document creation time.
No external annotation is required — the manipulation is documented explicitly
in the `hallucination_type` field of each record.

---

## Corpus Structure

```
docs/corpus/
├── CORPUS_VALIDATION.md          ← this file
├── corpus_index.json             ← machine-readable index of all records
├── legal/
│   ├── legal_01A_clean.txt
│   ├── legal_01B_hallucination.txt
│   └── ...
├── financial/
│   ├── finance_01A_clean.txt
│   ├── finance_01B_hallucination.txt
│   └── ...
├── medical/
│   ├── medical_01A_clean.txt
│   ├── medical_01B_hallucination.txt
│   └── ...
├── code/
│   ├── code_01A_clean.txt
│   ├── code_01B_hallucination.txt
│   └── ...
├── historical/
│   ├── history_01A_clean.txt
│   ├── history_01B_hallucination.txt
│   └── ...
└── results/
    └── benchmark_corpus_v1.json  ← scanner output on all 30 documents
```

---

## Labeling Schema

Each document in `corpus_index.json` contains:

| Field | Type | Description |
|---|---|---|
| `id` | string | Unique identifier (e.g. `legal_01A`) |
| `domain` | string | `legal` / `financial` / `medical` / `code` / `historical` |
| `label` | string | `CLEAN` or `HALLUCINATION` |
| `pair_id` | string | Links A and B versions (e.g. `legal_01`) |
| `hallucination_type` | string | Null if CLEAN, else: `logical_contradiction` / `impossible_math` / `unit_confusion` / `logical_collapse` / `fabricated_event` |
| `hallucination_description` | string | Explicit description of the introduced manipulation |
| `word_count` | int | Token count of the document |
| `expected_verdict` | string | `CLEAR` or `REVIEW` |
| `scanner_manifold_score` | float | Populated after running benchmark |
| `scanner_isi_vs_pair` | float | ISI of B vs A — populated after benchmark |
| `scanner_verdict` | string | Populated after running benchmark |
| `correct_detection` | bool | `true` if scanner_verdict matches expected_verdict |

---

## Hallucination Taxonomy

### 1. `logical_contradiction`
A clause or statement that establishes a condition and then violates it within
the same text, using different vocabulary to obscure the contradiction.
*Domain: Legal, Discourse*

### 2. `impossible_math`
A quantitative analysis that cites non-existent indicators or produces a
mathematical result that is impossible given the stated premises.
*Domain: Financial*

### 3. `unit_confusion`
A subtle change of measurement unit mid-text (e.g. mg → kg, %, absolute value)
that produces an impossible or dangerous conclusion while maintaining fluency.
*Domain: Medical, Technical*

### 4. `logical_collapse`
Code or reasoning that is syntactically correct but produces undefined,
infinite, or random behavior disguised as intentional logic.
*Domain: Code*

### 5. `fabricated_event`
A biographical or historical text that mixes verified facts with a plausible
but non-existent event, treaty, or date inserted to fit the chronology.
*Domain: Historical, Factual*

---

## Benchmark Execution

To run the scanner on the full corpus and populate results:

```bash
cd <project_root>
python tests/benchmark_corpus.py --corpus docs/corpus/ --output docs/corpus/results/
```

Expected output per document:
- ManifoldScore
- ISI vs pair (for B documents)
- Semantic Diff verdict
- Detection correct: true/false

Aggregate metrics reported:
- **Precision**: TP / (TP + FP)
- **Recall**: TP / (TP + FN)
- **F1 Score**
- **CIR (Corpus Integrity Rate)**: fraction of CLEAN docs scoring ≥ κD

---

## Corpus Index — v1.0 (30 documents / 15 pairs)

| ID | Domain | Label | Hallucination Type | Words | Expected |
|---|---|---|---|---|---|
| legal_01A | legal | CLEAN | — | ~200 | CLEAR |
| legal_01B | legal | HALLUCINATION | logical_contradiction | ~200 | REVIEW |
| legal_02A | legal | CLEAN | — | ~200 | CLEAR |
| legal_02B | legal | HALLUCINATION | logical_contradiction | ~200 | REVIEW |
| legal_03A | legal | CLEAN | — | ~300 | CLEAR |
| legal_03B | legal | HALLUCINATION | logical_contradiction | ~300 | REVIEW |
| finance_01A | financial | CLEAN | — | ~200 | CLEAR |
| finance_01B | financial | HALLUCINATION | impossible_math | ~200 | REVIEW |
| finance_02A | financial | CLEAN | — | ~200 | CLEAR |
| finance_02B | financial | HALLUCINATION | impossible_math | ~200 | REVIEW |
| medical_01A | medical | CLEAN | — | ~150 | CLEAR |
| medical_01B | medical | HALLUCINATION | unit_confusion | ~150 | REVIEW |
| medical_02A | medical | CLEAN | — | ~150 | CLEAR |
| medical_02B | medical | HALLUCINATION | unit_confusion | ~150 | REVIEW |
| code_01A | code | CLEAN | — | ~100 | CLEAR |
| code_01B | code | HALLUCINATION | logical_collapse | ~100 | REVIEW |
| code_02A | code | CLEAN | — | ~100 | CLEAR |
| code_02B | code | HALLUCINATION | logical_collapse | ~100 | REVIEW |
| history_01A | historical | CLEAN | — | ~200 | CLEAR |
| history_01B | historical | HALLUCINATION | fabricated_event | ~200 | REVIEW |
| history_02A | historical | CLEAN | — | ~200 | CLEAR |
| history_02B | historical | HALLUCINATION | fabricated_event | ~200 | REVIEW |
| llm_01A | llm_output | CLEAN | — | ~200 | CLEAR |
| llm_01B | llm_output | HALLUCINATION | logical_contradiction | ~200 | REVIEW |
| llm_02A | llm_output | CLEAN | — | ~200 | CLEAR |
| llm_02B | llm_output | HALLUCINATION | fabricated_event | ~200 | REVIEW |
| llm_03A | llm_output | CLEAN | — | ~200 | CLEAR |
| llm_03B | llm_output | HALLUCINATION | impossible_math | ~200 | REVIEW |
| paper_01A | scientific | CLEAN | — | ~300 | CLEAR |
| paper_01B | scientific | HALLUCINATION | logical_contradiction | ~300 | REVIEW |

---

## Integrity

This corpus is part of the Durante Semantic Stability Framework validation suite.  
Ground truth labels are established by the author and documented at creation time.  
The corpus index will be SHA-256 signed upon first public release.

**License:** Durante Invariance License v1.0  
**Registry:** EX-2026-18792778 — TAD, República Argentina  
**DOI:** 10.5281/zenodo.19052627
