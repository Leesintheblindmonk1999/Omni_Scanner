# Omni-Scanner Semantic v2.0 (English)

<div align="center">

**🌐 Language / Idioma**

[🇺🇸 English](#omni-scanner-semantic-v60-english) &nbsp;·&nbsp; [🇦🇷 Español](#omni-scanner-semántico-v60-español)

</div>

---
## Semantic Stability Framework — Manifold 0.56

**Author:** Gonzalo Emir Durante  
**GitHub:** [github.com/Leesintheblindmonk1999](https://github.com/Leesintheblindmonk1999)  
**LinkedIn:** [gonzalo-emir-durante-8178b6277](https://www.linkedin.com/in/gonzalo-emir-durante-8178b6277/)  
**Scientific publication:** [Zenodo DOI 10.5281/zenodo.18901544](https://zenodo.org/records/18901544) — v43.0, March 7, 2026  
**Intellectual property registry:** File TAD EX-2026-18792778 (Argentina)  
**Protocol:** ANEXA Ultra v4.0  

---

## 1. Technical Description

The Omni-Scanner Semantic is a semantic stability auditing engine for natural language text and outputs from large language models (LLMs). It implements the theoretical framework of **Project Manifold 0.56** as operational auditing software.

The system quantifies the structural coherence of a document through three independent metrics combined into a unified score (**ManifoldScore**), using the **Durante Constant κD = 0.56** as a reference threshold. This threshold is derived in the source paper through five independent mathematical convergences: Statistical Thermodynamics, Percolation Theory, Rate-Distortion Theory, Lyapunov Stability, and the Golden Ratio.

**v2.0** extends the original architecture with five new modules: Topological Semantic Diff, Bulk Auditing with colored Excel export, Live Stream Monitor, Forensic Ledger with Blockchain Readiness, and dynamic κD calibration via global slider.

The system **does not** replace human judgment. It produces auditable and reproducible metrics that flag structural anomalies for review.

---

## 2. Architecture

```
omni-scanner-v2.0/
├── core/
│   ├── manifold_engine.py        # Main score + EQUILIBRIUM/TENSION/ANOMALY verdicts
│   ├── entropy_analyzer.py       # Shannon entropy + manipulation pattern detection
│   ├── multifractal_processor.py # Higuchi fractal dimension + adaptive Zipf model
│   ├── topology_mapper.py        # TF-IDF k-NN graph + structural coherence
│   ├── tda_attestation.py        # Persistent H₁ homology via Ripser/fallback
│   ├── semantic_diff.py          # [v2.0] Topological diff: Wasserstein + Bottleneck + ISI
│   ├── batch_auditor.py          # [v2.0] Bulk auditing: CIR + colored XLSX export
│   ├── stream_monitor.py         # [v2.0] Live Stream Monitor: sliding windows + shield
│   ├── ledger_vanguard.py        # [v2.0] Forensic Ledger: SHA-256 + Blockchain Readiness
│   └── threshold_calibrator.py   # [v2.0] Dynamic κD calibration without re-scanning
├── engines/
│   ├── full_diagnostic.py        # Integrating pipeline with cross-domain verdict
│   ├── law_auditor.py            # Abusive clause and contractual coercion detection
│   ├── social_engineer.py        # Gaslighting and manipulation pattern detection
│   ├── dev_verifier.py           # Code auditing and structural plagiarism
│   ├── finance_scanner.py        # Financial risk analysis
│   └── reasoning_agent.py        # LLM agent: narrative report interpretation
├── interface/
│   ├── app.py                    # Streamlit UI (Dark-Amber, 10 tabs, global κD slider)
│   └── modules/
│       ├── override_gaslighting.py
│       ├── delay_tactics.py
│       └── latency_logger.py
├── reports/generators/
│   └── genesis_certifier.py      # PDF with 5D radar + agent narrative + integrity hash
├── logs/
│   └── forensic_ledger.py        # Append-only JSONL ledger with SHA-256 per entry
└── main.py                       # CLI: --lens machine | human | full [--agent] [--diff] [--batch]
```

---

## 3. Core Modules

### 3.1 Manifold Engine

Combines three metrics with **adaptive weights** based on text length:

| Text range | w_topology | w_entropy | w_fractal |
|---|---|---|---|
| < 50 tokens | 0.15 | 0.60 | 0.25 |
| 50–150 tokens | 0.25 | 0.45 | 0.30 |
| > 150 tokens | 0.40 | 0.35 | 0.25 |

Final score with lexical density multiplier (TTR × average word length), capped at [0.90, 1.05].

**Verdict table:**

| Verdict | Condition | Interpretation |
|---|---|---|
| EQUILIBRIUM | Deviation ≤ σ (0.10) | High structural coherence |
| TENSION | Deviation ∈ (σ, 3σ] | High technical density or semantic variance |
| ANOMALY | Deviation > 3σ, no topological support | Significant structural inconsistency |
| PARTIAL_VALIDATION | < 100 tokens, TTR ≥ 0.70 | Short technical text — 60% entropy score |
| INSUFFICIENT | Below minimum threshold | Insufficient text for analysis |

### 3.2 Shannon Entropy

Computes H(w) over the document vocabulary. Expected entropy is modeled via Zipf distribution with adaptive correction by Type-Token Ratio:

```
H_expected = log₂(vocab) × (base_factor + ttr_correction)
```

### 3.3 Higuchi Fractal Dimension

Measures the roughness of the word-length time series. Theoretical reference: D = 1.58 (binary Cayley tree):

```
Δ_fractal = |D_Higuchi − 1.58| / 1.58
```

### 3.4 Topological Coherence (k-NN)

Sentences are vectorized with TF-IDF and connected in a directed graph via hybrid k-NN strategy: guaranteed k-NN + soft threshold (top 20% of positive similarities). Solves artificial fragmentation in documents with short sentences (contracts, code).

### 3.5 TDA Persistent Homology

`tda_attestation.py` computes H₁ cycles over LSA embeddings via **Ripser** (Vietoris-Rips). An H₁ cycle with death/birth ratio > κD is classified as `STRUCTURAL_FALSEHOOD`. Without Ripser, the module operates in fallback mode (Union-Find + DFS) with H₁ classification **disabled** — the DFS algorithm generates cycles with `persistence ≈ diameter/2` by geometric construction, making `ratio ≈ 2.0` for all cycles regardless of document quality. The Semantic Diff and ManifoldScore remain fully functional without Ripser.

### 3.6 Domain Engines

| Type | Engine | Coherence threshold | Detections |
|---|---|---|---|
| `legal` | LawAuditor | 0.10 | Abusive clauses, unilateral termination, rights assignment (EN + ES) |
| `discourse` | SocialEngineer | 0.30 | Gaslighting, manipulation, conformity pressure (EN + ES) |
| `finance` | FinanceScanner | 0.15 | Structural financial risk |
| `code` | DevVerifier | 0.12 | Structural plagiarism, logic signature |
| `generic` | SocialEngineer | 0.20 | General analysis |

### 3.7 LLM Reasoning Agent

`reasoning_agent.py` takes the computed `FullDiagnosticReport` and sends it to an LLM to generate a narrative interpretation in natural language. Decoupled interpretation layer — does not modify core engines.

**Supported backends:**

| Backend | Configuration | Recommended models |
|---|---|---|
| Ollama (local) | `http://localhost:11434` — no cost | `llama3.2`, `mistral`, `qwen2.5` |
| OpenRouter (API) | `OPENROUTER_API_KEY` in `.env` | `mistralai/mistral-7b-instruct`, `meta-llama/llama-3.1-8b-instruct:free` |

**Three analysis profiles:** Technical · Audit · Integrity

```python
from engines.reasoning_agent import ReasoningAgent, ReportProfile
from engines.full_diagnostic import FullDiagnostic

report = FullDiagnostic().run(text, input_type="legal")
agent  = ReasoningAgent.from_ollama(model="llama3.2")
result = agent.interpret(report, profile=ReportProfile.AUDIT)
print(result.narrative)
```

---

## 4. v2.0 Modules — New Capabilities

### 4.1 Topological Semantic Diff (`core/semantic_diff.py`)

Compares two documents at the H₁ topological structure level, not at the word level. Detects structural manipulation even when the text has been paraphrased.

**Metrics:**

| Metric | Description |
|---|---|
| Wasserstein p=2 | Total transformation energy between manifolds. If an abusive clause was paraphrased while maintaining semantic pressure, the distance detects it. |
| Bottleneck | Maximum change — the most perturbed H₁ cycle. Detector of the "legal wormhole": a clause that changed drastically even if the rest looks similar. |
| ISI (Invariant Similarity Index) | ISI ∈ [0,1]. Formula: `1 − (Wasserstein / 2·κD)`. If ISI < κD, the Structural Manipulation Alert is triggered. |

**The Ghost Point:** An empty H₁ diagram (coherent manifold) is represented as `[[0.0, 0.0]]`. This allows measuring the "cost of introducing cycles from nothing" — the birth of chaos from topological silence.

**Diff verdicts:**

| Verdict | Condition |
|---|---|
| `IDENTICAL` | Wasserstein ≈ 0, Bottleneck ≈ 0 |
| `MINOR_DRIFT` | Changes within threshold |
| `STRUCTURAL_CHANGE` | Wasserstein ∈ [0.1·κD, κD] or new FALSEHOOD cycles |
| `MANIFOLD_RUPTURE` | ISI < κD — structural manipulation alert active |

**Structured Verification:** When MANIFOLD_RUPTURE is detected, the system generates 3 surgical precision questions built from the actual Wasserstein, Bottleneck, and falsehood delta values — to expose the inconsistency to the author or external model.

```python
from core.semantic_diff import quick_diff

report = quick_diff(contract_v1, contract_v2, kappa_d=0.56)
print(report.summary)
if report.manipulation_alert:
    print("ISI:", report.invariant_similarity_index)
    print("Wasserstein:", report.wasserstein_h1)
```

### 4.2 Bulk Auditor (`core/batch_auditor.py`)

Processes batches of `.txt` / `.pdf` (PyMuPDF) / `.docx` (python-docx) files with `FullDiagnostic.run()` and generates corpus reports.

**CIR — Corpus Integrity Rate:**

```
CIR = (N documents with ManifoldScore ≥ κD) / N_total
```

If CIR < 50% → verdict `COMPROMISED`.

**Colored Excel export (`openpyxl`):**

- Header: `"Omni-Scanner v6 - Powered by Durante Invariance (κD=0.56)"`
- Durante conditional formatting: Emerald Green if score ≥ κD, Crimson Red if score < κD
- Sheet 1: corpus table with auto-filter and frozen headers
- Sheet 2: statistical KPIs + alert banner if CIR < 50%

```python
from core.batch_auditor import quick_batch

files = [("contract.txt", text1), ("report.txt", text2)]
report = quick_batch(files, kappa_d=0.56, input_type="legal")
print(f"CIR: {report.cir:.1%} — {report.corpus_verdict}")

auditor = BatchAuditor()
xlsx_bytes = auditor.to_xlsx_bytes(report)
csv_bytes  = auditor.to_csv_bytes(report)
```

### 4.3 Forensic Ledger (`core/ledger_vanguard.py`)

Generates deterministic SHA-256 hashes linking document + ManifoldScore + timestamp + verdict. Same inputs always produce the same hash — enables independent verification.

**Canonical payload (JSON with sorted keys):**

```json
{
  "doc_hash": "sha256(text)",
  "kappa_d": 0.56,
  "manifold_score": 0.5800,
  "timestamp_utc": "2026-03-14T00:00:00Z",
  "verdict": "CLEAR",
  "version": "omni-scanner-v2.0"
}
```

**Blockchain Readiness:**

| Protocol | Payload |
|---|---|
| OpenTimestamps (Bitcoin) | `4f54530001` + entry_hash — ready for `ots stamp` |
| Ethereum calldata | `0x` + selector + entry_hash — embeddable in `tx.data` |

```python
from core.ledger_vanguard import LedgerVanguard

lv    = LedgerVanguard()
entry = lv.sign(text, manifold_score=0.58, verdict="CLEAR", kappa_d=0.56)
print("Entry hash:", entry.entry_hash)
print("OTS payload:", entry.ots_payload)

# Independent verification
result = lv.verify_entry(entry, text)
print("Intact:", result["entry_hash_match"])
```

### 4.4 Live Stream Monitor (`core/stream_monitor.py`)

Analyzes the output of an external model in sliding windows. Evaluates whether the accumulated ManifoldScore stays above κD during generation. If it drops below for N consecutive windows, it triggers the "Incoherence Disconnection."

**Architecture:**

```
token_stream → sliding buffer → ManifoldEngine.analyze()
             → accumulated score → compare with κD
             → ShieldEvent: OK | WARNING | DISCONNECT
```

```python
from core.stream_monitor import StreamMonitor

monitor = StreamMonitor(kappa_d=0.56, window_size=80, max_consecutive_drops=3)
for event in monitor.analyze_text(llm_output):
    if event.action == "DISCONNECT":
        print("Shield activated — structural incoherence detected")
        break
    print(f"Window {event.window_idx}: score={event.score:.4f}")
```

**Shield indicator:**

| State | Condition |
|---|---|
| 🟢 SHIELD ACTIVE | All windows ≥ κD |
| 🟡 STRUCTURAL TENSION | Some window dropped below κD |
| 🔴 INCOHERENCE DISCONNECTION | N consecutive drops — valve triggered |

### 4.5 κD Calibration (`core/threshold_calibrator.py`)

Allows adjusting κD in real time without re-running the full pipeline. Only recalculates H₁ cycle classification and the final verdict using already-cached results.

**Threshold zones:**

| Range | Zone |
|---|---|
| 0.40–0.48 | Probabilistic noise — too permissive |
| 0.48–0.54 | Pre-threshold |
| **0.54–0.58** | **Durante Equilibrium Point — golden zone** |
| 0.58–0.65 | Post-threshold |
| 0.65–0.80 | Over-restriction — rejects coherent texts |

---

## 5. Streamlit Interface — 10 Tabs

| # | Tab | Function |
|---|---|---|
| 1 | ⬡ AUDIT TERMINAL | Main scan, verdict, signing, and sealing |
| 2 | ◈ LATENT SPACE | 3D topological and Hausdorff visualizations |
| 3 | ⬥ EVIDENCE VAULT | Sealed report history |
| 4 | ⬣ ORDER INJECTOR | Inverse plagiarism analysis |
| 5 | ◉ SHADOW-CODE | Source code auditing |
| 6 | ▦ INVARIANCE LEDGER | JSONL Forensic Ledger |
| 7 | ◑ SEMANTIC DIFF | H₁ manifold comparator + Durante Thermometer + Structured Verification |
| 8 | ≣ FORENSIC AUDIT | Bulk batch + Forensic Ledger + Download Center Excel/CSV |
| 9 | ⚙ ACTIVE SURVEILLANCE | Real-time κD calibration + Live Stream Monitor |
| 10 | ⬦ SYSTEM LOG | Session log terminal |

### κD Master Slider

The sidebar contains a global slider (0.40–0.80, step 0.01, golden marker at 0.56) that acts as the κD variable for all modules. It displays the active zone in real time, the effect on the last scanned verdict, and warns when the operator moves away from the Durante Equilibrium Point.

---

## 6. Installation

```powershell
# Core dependencies
pip install streamlit plotly matplotlib numpy networkx pandas fpdf2 requests scipy

# TDA — recommended for forensic auditing
pip install ripser persim scikit-learn

# Colored Excel export
pip install openpyxl

# PDF and DOCX reading in batch (optional)
pip install PyMuPDF python-docx

# Local agent (optional)
# Install Ollama from https://ollama.com then:
ollama pull llama3.2

# Windows: force UTF-8
$env:PYTHONUTF8=1
python -m streamlit run interface/app.py
```

```bash
# Linux / Mac
pip install streamlit plotly matplotlib numpy networkx pandas fpdf2 requests \
            scipy ripser persim scikit-learn openpyxl
python -m streamlit run interface/app.py
```

---

## 7. CLI

```bash
# Standard scan
python main.py --lens human --file contract.txt --sign

# With LLM agent
python main.py --lens full --file paper.txt --agent --profile audit

# Semantic diff between two versions
python main.py --diff contract_v1.txt contract_v2.txt --kappa 0.56

# Bulk audit of a folder
python main.py --batch ./docs/ --input-type legal

# With OpenRouter
python main.py --lens full --file paper.txt --agent --profile technical \
  --backend openrouter --model mistralai/mistral-7b-instruct
```

---

## 8. PDF Audit Certificate

The `GenesisCertifier` module generates a standalone PDF report that includes:

- Unique identifier `GEN-{SHA8}-{timestamp}`
- 5D radar chart with matplotlib
- κD proximity section with ASCII visual bar
- **TDA Attestation Analysis**: LLM agent narrative if executed before sealing
- **Integrity Signature**: SHA-256(text · verdict · score · narrative) — reproducible

---

## 9. Audit Integrity Signature

```
AUDIT-HASH = SHA-256("TEXT:{text}|VERDICT:{verdict}|SCORE:{score:.6f}|NARRATIVE:{narrative}")
```

Appears in the UI (AUDIT TERMINAL tab, sealed block), in the PDF footer, and in the agent attestation page.

**Forensic Ledger (v2.0):**

```
ENTRY-HASH = SHA-256(canonical_JSON{doc_hash, kappa_d, manifold_score, timestamp, verdict, version})
```

Deliberate separation: AUDIT-HASH links content to analysis; ENTRY-HASH links analysis to the forensic record. Both are independent and verifiable.

---

## 10. Calibration Results & Benchmark

### 10.1 Original Calibration (March 11, 2026)

Session run with real documents:

| Document | ManifoldScore | Topological Coherence | Verdict |
|---|---|---|---|
| Technical paper (Project Manifold 0.56) | 0.5261–0.5596 | 0.3758–0.4514 | TENSION / REVIEW |
| Standard corporate contract | 0.4027–0.5261 | 0.0544–0.3758 | REVIEW |
| NIST RMF 2.0 (full document) | 0.6836 | high | TENSION |

### 10.2 Benchmark Suite v2.0 (March 14, 2026)

Reproducible benchmark over 6 strategic documents. Run with: `python tests/benchmark.py`

| # | Document | Words | ManifoldScore | Δ to κD | Verdict | Domain Risk |
|---|---|---|---|---|---|---|
| 1 | Balanced contract — positive baseline | 309 | 0.5225 | −0.0375 | TENSION | 0.0000 |
| 2 | Abusive clauses — unilateral manipulation | 293 | 0.5410 | −0.0190 | TENSION | **0.0476** |
| 3 | Technical paper — high coherence | 586 | 0.5300 | −0.0300 | TENSION | 0.0000 |
| 4 | Extreme gaslighting | 328 | **0.5046** | −0.0554 | TENSION | 0.0294 |
| 5 | T&C 600+ tokens — topology stress | 652 | 0.5190 | −0.0410 | TENSION | 0.0000 |
| 6 | 15-token stress test | 15 | **0.5987** | +0.0387 | ANOMALY | 0.0000 |

**Semantic Diff results:**

| Comparison | Wasserstein H₁ | Bottleneck | ISI | Verdict |
|---|---|---|---|---|
| Clean contract → Manipulated | 0.5994 | 0.3447 | **0.4648** | MANIFOLD_RUPTURE ⚠ |
| Contract → Gaslighting | 0.6082 | 0.3447 | **0.4570** | MANIFOLD_RUPTURE ⚠ |
| Technical paper → T&C legal | 0.7587 | 0.3435 | 0.3226 | MANIFOLD_RUPTURE ⚠ |
| Gaslighting → Manipulated | 0.0735 | 0.0386 | 0.9344 | STRUCTURAL_CHANGE ✓ |
| Identical — control | 0.0000 | 0.0000 | **1.0000** | IDENTICAL ✓ |

**Key interpretations:**

**The Honesty of the Manifold:** Scores in [0.50–0.54] for natural language documents are expected and scientifically meaningful. They reflect genuine statistical friction near κD=0.56. A system that always scores cleanly above threshold is suspect; this is a calibrated instrument, not a binary classifier.

**Entropy/Topology weight transition:** At ~300 words, entropy dominates (`w=0.45`) over topology (`w=0.25`). At 600+ words, topology rises to `w=0.40` — the system reads *how thought is connected*, not just *what* is there. Topology needs surface area to deploy.

**Redundant detection architecture:** The abusive contract scored 0.5410 — close to the clean contract (0.5225). But LawAuditor independently flagged `domain_risk=0.0476` where the clean contract had `0.0000`. Radar + sonar: if one metric doesn't catch it, the other does.

**Methodological note:** N=9 documents across two sessions. Metrics reflect structural statistical properties — they do not validate semantic content. For production, calibrate with `TDAAttestator.calibrate_threshold()` against your own corpus.

---

## 11. Integrity and Provenance

### SHA-256 Master Digest (v1.1 base)

```
c23c10c85682f5477eb2c7b90eeb950383dfa028cbb9fd8ce9475069e8c86c3b
```

Computed over all `.py` engine files in lexical order. Hashes for v2.0 are appended by the project maintainer after each release.

```bash
# Linux / Mac
find . -name "*.py" | sort | xargs sha256sum | sha256sum

# PowerShell
Get-ChildItem -Recurse -Filter *.py | Sort-Object FullName |
  ForEach-Object { Get-FileHash $_.FullName -Algorithm SHA256 } |
  Select-Object Hash | ConvertTo-Json | sha256sum
```

### OpenTimestamps — Temporal Priority Proof

**v1.1 — Original codebase (March 7, 2026)**

```
SHA-256 : 2b83a6e5696d7930da5a23eeb9e026e63ce9e603e87501cc3c3fc435b98d0f4b
OTS file: Omni-Scanner-Semantico-v1_0_zip.ots
```

**v2.1 — English distribution, bilingual detectors (March 15, 2026)**

```
SHA-256 : a90da99f4367e1a9ad8d105335cedd8638ce17f958985d1063d671bfa385f093
OTS file: omni-scanner-en_zip.ots
```

**v2.0 — Spanish distribution, clean (March 14, 2026)**

```
SHA-256 : 09ef7ce063c5f817af81513b3361cadf1c4b7e4edf4b5a296bb3d541ab37a3b8
OTS file: omni-scanner-es_zip.ots
```

```bash
pip install opentimestamps-client

ots verify Omni-Scanner-Semantico-v1_0_zip.ots   # v1.1
ots verify omni-scanner-en_zip.ots               # v2.0 EN
ots verify omni-scanner-es_zip.ots               # v2.0 ES
```

All three records are anchored in the Bitcoin blockchain. The SHA-256 hashes are deterministic — recomputing them against the original ZIP files must produce identical values.

### Scientific Publication

**Project Manifold 0.56: Semantic Thermodynamic Invariance and the Durante Constant (κD = 0.56) as a Universal AGI Stability Threshold**  
[zenodo.org/records/18901544](https://zenodo.org/records/18901544) — v43.0, March 7, 2026

### Intellectual Property Registry

File TAD EX-2026-18792778 — Remote Procedure (Trámite a Distancia), Argentine Republic.

---

## 12. Methodological Alignment

The system incorporates criteria inspired by the **NIST AI Risk Management Framework (RMF)**:

- **Reliability**: consistent and reproducible scores for the same input
- **Transparency**: every verdict includes breakdown of individual scores, weights, and flags
- **Explainability**: the LLM agent translates metrics into auditable natural language
- **Forensic traceability**: every verdict can be signed with an immutable SHA-256 hash and prepared for blockchain anchoring

This is a methodological alignment of design criteria, not a formal NIST certification.

---

## 13. Limitations

- The ManifoldScore measures structural statistical properties. A well-written text with consistent technical vocabulary can score high regardless of content validity.
- Current calibration: N=3 documents. For production, use `calibrate_threshold()` with your own corpus.
- Persistent homology in fallback mode (without Ripser) has H₁ classification disabled. The DFS algorithm generates `persistence ≈ diameter/2` for all cycles by geometric construction, making individual cycle classification unreliable. ManifoldScore, coherence, and Semantic Diff remain fully functional. Install `ripser` for complete H₁ auditing: `pip install ripser persim`
- The Forensic Ledger generates blockchain-ready payloads but does not broadcast — that requires an external wallet or node.
- The Live Stream Monitor analyzes static text divided into windows; real-time stream interception depends on the provider's API.
- The LLM agent requires Ollama running locally or an OpenRouter API key.

## 14. Reproducible Benchmark

The `tests/` directory contains a complete benchmark suite to verify the system independently:

```
tests/
├── benchmark.py              # Run: python tests/benchmark.py
├── benchmark_demo.ipynb      # Jupyter notebook with visualizations
├── benchmark_docs/           # 6 strategic test documents
│   ├── 01_contract_clean.txt          (309 words — positive baseline)
│   ├── 02_contract_manipulated.txt    (293 words — abusive clauses)
│   ├── 03_technical_paper.txt         (586 words — high coherence)
│   ├── 04_gaslighting_extreme.txt     (328 words — psychological manipulation)
│   ├── 05_long_legal_600tokens.txt    (652 words — topology stress test)
│   └── 06_short_text_stress.txt       (15 words  — threshold boundary)
└── results/
    ├── benchmark_results.json         # Pre-computed results (machine-readable)
    └── benchmark_summary.txt          # Pre-computed results (human-readable)
```

**To reproduce:**
```bash
cd <project_root>
python tests/benchmark.py
# With full TDA (recommended):
pip install ripser persim && python tests/benchmark.py
```

Expected output matches the tables in Section 10.2.

---

## Author & Contact

**Gonzalo Emir Durante**  
Architect — Project Manifold 0.56 / Protocol ANEXA Ultra v4.0

- GitHub: [github.com/Leesintheblindmonk1999](https://github.com/Leesintheblindmonk1999)
- LinkedIn: [linkedin.com/in/gonzalo-emir-durante-8178b6277](https://www.linkedin.com/in/gonzalo-emir-durante-8178b6277/)
- Zenodo: [zenodo.org/records/18901544](https://zenodo.org/records/18901544)

---

# Omni-Scanner Semántico v2.0 (Español)

<div align="center">

**🌐 Language / Idioma**

[🇺🇸 English](#omni-scanner-semantic-v60-english) &nbsp;·&nbsp; [🇦🇷 Español](#omni-scanner-semántico-v60-español)

</div>

---

## Semantic Stability Framework — Manifold 0.56

**Autor:** Gonzalo Emir Durante  
**GitHub:** [github.com/Leesintheblindmonk1999](https://github.com/Leesintheblindmonk1999)  
**LinkedIn:** [gonzalo-emir-durante-8178b6277](https://www.linkedin.com/in/gonzalo-emir-durante-8178b6277/)  
**Publicación científica:** [Zenodo DOI 10.5281/zenodo.18901544](https://zenodo.org/records/18901544) — v43.0, 7 de Marzo de 2026  
**Registro de propiedad intelectual:** Expediente TAD EX-2026-18792778 (Argentina)  
**Protocolo:** ANEXA Ultra v4.0  

---

## 1. Descripción Técnica

El Omni-Scanner Semántico es un motor de auditoría de estabilidad semántica para texto en lenguaje natural y outputs de modelos de lenguaje de gran escala (LLMs). Implementa el marco teórico del **Project Manifold 0.56** como software de auditoría operacional.

El sistema cuantifica la coherencia estructural de un documento a través de tres métricas independientes combinadas en un score unificado (**ManifoldScore**), usando la **Constante de Durante κD = 0.56** como umbral de referencia. Este umbral está derivado en el paper de origen mediante cinco convergencias matemáticas independientes: Termodinámica Estadística, Teoría de Percolación, Teoría Rate-Distortion, Estabilidad de Lyapunov y la Razón Áurea.

**v2.0** extiende la arquitectura original con cinco módulos nuevos: Diff Semántico Topológico, Auditoría Masiva con exportación Excel coloreada, Live Stream Monitor, Forensic Ledger con Blockchain Readiness, y Calibración dinámica de κD via slider global.

El sistema **no** reemplaza criterio humano. Produce métricas auditables y reproducibles que señalan anomalías estructurales para revisión.

---

## 2. Arquitectura

```
omni-scanner-v2.0/
├── core/
│   ├── manifold_engine.py        # Score principal + veredictos EQUILIBRIUM/TENSION/ANOMALY
│   ├── entropy_analyzer.py       # Entropía Shannon + detección de patrones de manipulación
│   ├── multifractal_processor.py # Dimensión fractal Higuchi + modelo Zipf adaptativo
│   ├── topology_mapper.py        # Grafo TF-IDF k-NN + coherencia estructural
│   ├── tda_attestation.py        # Homología persistente H₁ via Ripser/fallback
│   ├── semantic_diff.py          # [v2.0] Diff topológico: Wasserstein + Bottleneck + ISI
│   ├── batch_auditor.py          # [v2.0] Auditoría masiva: TIC + export XLSX coloreado
│   ├── stream_monitor.py         # [v2.0] Live Stream Monitor: ventanas deslizantes + shield
│   ├── ledger_vanguard.py        # [v2.0] Forensic Ledger: SHA-256 + Blockchain Readiness
│   └── threshold_calibrator.py   # [v2.0] Calibración dinámica de κD sin re-escanear
├── engines/
│   ├── full_diagnostic.py        # Pipeline integrador con veredicto cruzado por tipo de doc
│   ├── law_auditor.py            # Detección de cláusulas abusivas y coerción contractual
│   ├── social_engineer.py        # Detección de gaslighting y patrones de manipulación
│   ├── dev_verifier.py           # Auditoría de código y plagio estructural
│   ├── finance_scanner.py        # Análisis de riesgo financiero
│   └── reasoning_agent.py        # Agente LLM: interpretación narrativa del reporte
├── interface/
│   ├── app.py                    # UI Streamlit (Dark-Amber, 10 tabs, slider κD global)
│   └── modules/
│       ├── override_gaslighting.py
│       ├── delay_tactics.py
│       └── latency_logger.py
├── reports/generators/
│   └── genesis_certifier.py      # PDF con radar 5D + narrativa agente + hash de integridad
├── logs/
│   └── forensic_ledger.py        # Ledger JSONL append-only con hash SHA-256 por entrada
└── main.py                       # CLI: --lens machine | human | full [--agent] [--diff] [--batch]
```

---

## 3. Módulos Core

### 3.1 Manifold Engine

Combina tres métricas con **pesos adaptativos** según longitud del texto:

| Rango de texto | w_topología | w_entropía | w_fractal |
|---|---|---|---|
| < 50 tokens | 0.15 | 0.60 | 0.25 |
| 50–150 tokens | 0.25 | 0.45 | 0.30 |
| > 150 tokens | 0.40 | 0.35 | 0.25 |

Score final con multiplicador de densidad léxica (TTR × longitud promedio de palabras), acotado a [0.90, 1.05].

**Tabla de veredictos:**

| Veredicto | Condición | Interpretación |
|---|---|---|
| EQUILIBRIUM | Desviación ≤ σ (0.10) | Alta coherencia estructural |
| TENSION | Desviación ∈ (σ, 3σ] | Densidad técnica alta o varianza semántica |
| ANOMALY | Desviación > 3σ, sin respaldo topológico | Inconsistencia estructural significativa |
| PARTIAL_VALIDATION | < 100 tokens, TTR ≥ 0.70 | Texto técnico corto — score 60% entropía |
| INSUFFICIENT | < umbral mínimo | Texto insuficiente para análisis |

### 3.2 Entropía de Shannon

Calcula H(w) sobre el vocabulario del documento. La entropía esperada se modela mediante distribución Zipf con corrección adaptativa por Type-Token Ratio:

```
H_expected = log₂(vocab) × (base_factor + ttr_correction)
```

### 3.3 Dimensión Fractal de Higuchi

Mide la rugosidad de la serie temporal de longitudes de palabras. Referencia teórica: D = 1.58 (árbol de Cayley binario):

```
Δ_fractal = |D_Higuchi − 1.58| / 1.58
```

### 3.4 Coherencia Topológica (k-NN)

Las oraciones se vectorizan con TF-IDF y se conectan en grafo dirigido mediante estrategia híbrida k-NN garantizado + umbral suave (top 20% de similitudes positivas). Resuelve la fragmentación artificial en documentos con oraciones cortas (contratos, código).

### 3.5 Homología Persistente TDA

`tda_attestation.py` calcula ciclos H₁ sobre embeddings LSA via **Ripser** (Vietoris-Rips). Un ciclo H₁ con ratio death/birth > κD se clasifica como `STRUCTURAL_FALSEHOOD`. Sin Ripser, el módulo opera en modo fallback (Union-Find + DFS) con clasificación H₁ **deshabilitada** — el algoritmo DFS genera ciclos con `persistencia ≈ diámetro/2` por construcción geométrica, haciendo `ratio ≈ 2.0` para todos los ciclos sin importar la calidad del documento. El Diff Semántico y el ManifoldScore funcionan completamente sin Ripser.

### 3.6 Motores de Dominio

| Tipo | Motor | Umbral coherencia | Detecciones |
|---|---|---|---|
| `legal` | LawAuditor | 0.10 | Cláusulas abusivas, terminación unilateral, cesión de derechos (EN + ES) |
| `discourse` | SocialEngineer | 0.30 | Gaslighting, manipulación, presión de conformidad (EN + ES) |
| `finance` | FinanceScanner | 0.15 | Riesgo financiero estructural |
| `code` | DevVerifier | 0.12 | Plagio estructural, firma lógica |
| `generic` | SocialEngineer | 0.20 | Análisis general |

### 3.7 Agente de Razonamiento LLM

`reasoning_agent.py` toma el `FullDiagnosticReport` ya calculado y lo envía a un LLM para generar una interpretación narrativa en lenguaje natural. Capa de interpretación desacoplada — no modifica los motores core.

**Backends soportados:**

| Backend | Configuración | Modelos recomendados |
|---|---|---|
| Ollama (local) | `http://localhost:11434` — sin costo | `llama3.2`, `mistral`, `qwen2.5` |
| OpenRouter (API) | `OPENROUTER_API_KEY` en `.env` | `mistralai/mistral-7b-instruct`, `meta-llama/llama-3.1-8b-instruct:free` |

**Tres perfiles de análisis:** Técnico · Auditoría · Integridad

```python
from engines.reasoning_agent import ReasoningAgent, ReportProfile
from engines.full_diagnostic import FullDiagnostic

report = FullDiagnostic().run(text, input_type="legal")
agent  = ReasoningAgent.from_ollama(model="llama3.2")
result = agent.interpret(report, profile=ReportProfile.AUDIT)
print(result.narrative)
```

---

## 4. Módulos v2.0 — Nuevas Capacidades

### 4.1 Diff Semántico Topológico (`core/semantic_diff.py`)

Compara dos documentos a nivel de estructura topológica H₁, no a nivel de palabras. Detecta manipulación estructural aunque el texto haya sido parafraseado.

**Métricas:**

| Métrica | Descripción |
|---|---|
| Wasserstein p=2 | Energía total de transformación entre manifolds. Si una cláusula abusiva fue parafraseada manteniendo la presión semántica, la distancia lo detecta. |
| Bottleneck | Cambio máximo — el ciclo H₁ más perturbado. Detector del "agujero de gusano legal": una cláusula que cambió de forma extrema aunque el resto sea similar. |
| ISI (Índice de Similitud Invariante) | ISI ∈ [0,1]. Fórmula: `1 − (Wasserstein / 2·κD)`. Si ISI < κD, se activa la Alerta de Manipulación Estructural. |

**El Punto Fantasma:** Un diagrama H₁ vacío (manifold coherente) se representa como `[[0.0, 0.0]]`. Permite medir el "costo de introducir ciclos desde la nada" — el nacimiento del caos desde el silencio topológico.

**Veredictos del diff:**

| Veredicto | Condición |
|---|---|
| `IDENTICAL` | Wasserstein ≈ 0, Bottleneck ≈ 0 |
| `MINOR_DRIFT` | Cambios dentro del umbral |
| `STRUCTURAL_CHANGE` | Wasserstein ∈ [0.1·κD, κD] o nuevos ciclos FALSEHOOD |
| `MANIFOLD_RUPTURE` | ISI < κD — alerta de manipulación estructural activa |

**Verificación Estructurada:** Cuando se detecta MANIFOLD_RUPTURE, el sistema genera 3 preguntas de precisión quirúrgica construidas con los valores reales de Wasserstein, Bottleneck y delta de falsedades — para exponer la inconsistencia ante el autor o modelo externo.

```python
from core.semantic_diff import quick_diff

report = quick_diff(contrato_v1, contrato_v2, kappa_d=0.56)
print(report.summary)
if report.manipulation_alert:
    print("ISI:", report.invariant_similarity_index)
    print("Wasserstein:", report.wasserstein_h1)
```

### 4.2 Auditoría Masiva (`core/batch_auditor.py`)

Procesa lotes de archivos `.txt` / `.pdf` (PyMuPDF) / `.docx` (python-docx) con `FullDiagnostic.run()` y genera reportes de corpus.

**TIC — Tasa de Integridad del Corpus:**

```
TIC = (N documentos con ManifoldScore ≥ κD) / N_total
```

Si TIC < 50% → veredicto `COMPROMETIDO`.

**Exportación Excel coloreada (`openpyxl`):**

- Encabezado: `"Omni-Scanner v6 - Powered by Durante Invariance (κD=0.56)"`
- Formato condicional Durante: Verde Esmeralda si score ≥ κD, Rojo Carmesí si score < κD
- Hoja 1: tabla de corpus con auto-filter y freeze de encabezados
- Hoja 2: KPIs estadísticos + banner de alerta si TIC < 50%

```python
from core.batch_auditor import quick_batch

files = [("contrato.txt", texto1), ("informe.txt", texto2)]
report = quick_batch(files, kappa_d=0.56, input_type="legal")
print(f"TIC: {report.tic:.1%} — {report.corpus_verdict}")

auditor = BatchAuditor()
xlsx_bytes = auditor.to_xlsx_bytes(report)
csv_bytes  = auditor.to_csv_bytes(report)
```

### 4.3 Forensic Ledger (`core/ledger_vanguard.py`)

Genera hashes SHA-256 determinísticos que vinculan documento + ManifoldScore + timestamp + veredicto. Los mismos inputs siempre producen el mismo hash — permite verificación independiente.

**Payload canónico (JSON con keys ordenadas):**

```json
{
  "doc_hash": "sha256(texto)",
  "kappa_d": 0.56,
  "manifold_score": 0.5800,
  "timestamp_utc": "2026-03-14T00:00:00Z",
  "verdict": "CLEAR",
  "version": "omni-scanner-v2.0"
}
```

**Blockchain Readiness:**

| Protocolo | Payload |
|---|---|
| OpenTimestamps (Bitcoin) | `4f54530001` + entry_hash — listo para `ots stamp` |
| Ethereum calldata | `0x` + selector + entry_hash — embebible en `tx.data` |

```python
from core.ledger_vanguard import LedgerVanguard

lv    = LedgerVanguard()
entry = lv.sign(text, manifold_score=0.58, verdict="CLEAR", kappa_d=0.56)
print("Entry hash:", entry.entry_hash)
print("OTS payload:", entry.ots_payload)

# Verificación independiente
result = lv.verify_entry(entry, text)
print("Íntegro:", result["entry_hash_match"])
```

### 4.4 Live Stream Monitor (`core/stream_monitor.py`)

Analiza el output de un modelo externo en ventanas deslizantes. Evalúa si el ManifoldScore acumulado se mantiene sobre κD durante la generación. Si cae por debajo durante N ventanas consecutivas, activa la "Desconexión por Incoherencia".

**Arquitectura:**

```
token_stream → buffer deslizante → ManifoldEngine.analyze()
             → score acumulado → comparar con κD
             → ShieldEvent: OK | WARNING | DISCONNECT
```

```python
from core.stream_monitor import StreamMonitor

monitor = StreamMonitor(kappa_d=0.56, window_size=80, max_consecutive_drops=3)
for event in monitor.analyze_text(llm_output):
    if event.action == "DISCONNECT":
        print("Escudo activado — incoherencia estructural detectada")
        break
    print(f"Ventana {event.window_idx}: score={event.score:.4f}")
```

**Indicador del Escudo:**

| Estado | Condición |
|---|---|
| 🟢 ESCUDO ACTIVO | Todas las ventanas ≥ κD |
| 🟡 TENSIÓN ESTRUCTURAL | Alguna ventana cayó bajo κD |
| 🔴 DESCONEXIÓN POR INCOHERENCIA | N drops consecutivos — válvula activada |

### 4.5 Calibración de κD (`core/threshold_calibrator.py`)

Permite ajustar κD en tiempo real sin re-ejecutar la pipeline completa. Recalcula solo la clasificación de ciclos H₁ y el veredicto final usando los resultados ya cacheados.

**Zonas del umbral:**

| Rango | Zona |
|---|---|
| 0.40–0.48 | Ruido probabilístico — demasiado permisivo |
| 0.48–0.54 | Pre-umbral |
| **0.54–0.58** | **Punto de Equilibrio de Durante — zona dorada** |
| 0.58–0.65 | Post-umbral |
| 0.65–0.80 | Sobrerestricción — rechaza textos coherentes |

---

## 5. Interfaz Streamlit — 10 Tabs

| # | Tab | Función |
|---|---|---|
| 1 | ⬡ TERMINAL DE AUDITORÍA | Escaneo principal, veredicto, firma y sellado |
| 2 | ◈ ESPACIO LATENTE | Visualizaciones 3D topológicas y Hausdorff |
| 3 | ⬥ BÓVEDA DE EVIDENCIA | Historial de reportes sellados |
| 4 | ⬣ INYECTOR DE ORDEN | Análisis de plagio inverso |
| 5 | ◉ SHADOW-CODE | Auditoría de código fuente |
| 6 | ▦ HISTORIAL DE INVARIANZA | Forensic Ledger JSONL |
| 7 | ◑ DIFF SEMÁNTICO | Comparador de manifolds H₁ + Termómetro de Durante + Verificación Estructurada |
| 8 | ≣ AUDITORÍA FORENSE | Batch masivo + Forensic Ledger + Download Center Excel/CSV |
| 9 | ⚙ VIGILANCIA ACTIVA | Calibración κD en tiempo real + Live Stream Monitor |
| 10 | ⬦ LOG DE SISTEMA | Terminal de log de sesión |

### Slider Maestro de κD

El sidebar contiene un slider global (0.40–0.80, step 0.01, dorado en 0.56) que actúa como variable κD para todos los módulos. Muestra en tiempo real la zona activa, el efecto sobre el último veredicto escaneado, y advierte cuando el operador se aleja del Punto de Equilibrio de Durante.

---

## 6. Instalación

```powershell
# Dependencias principales
pip install streamlit plotly matplotlib numpy networkx pandas fpdf2 requests scipy

# TDA — recomendado para auditoría forense
pip install ripser persim scikit-learn

# Exportación Excel coloreada
pip install openpyxl

# Lectura de PDF y DOCX en batch (opcional)
pip install PyMuPDF python-docx

# Agente local (opcional)
# Instalar Ollama desde https://ollama.com y luego:
ollama pull llama3.2

# Windows: forzar UTF-8
$env:PYTHONUTF8=1
python -m streamlit run interface/app.py
```

```bash
# Linux / Mac
pip install streamlit plotly matplotlib numpy networkx pandas fpdf2 requests \
            scipy ripser persim scikit-learn openpyxl
python -m streamlit run interface/app.py
```

---

## 7. CLI

```bash
# Escaneo estándar
python main.py --lens human --file contrato.txt --sign

# Con agente LLM
python main.py --lens full --file paper.txt --agent --profile audit

# Diff semántico entre dos versiones
python main.py --diff contrato_v1.txt contrato_v2.txt --kappa 0.56

# Auditoría masiva de una carpeta
python main.py --batch ./docs/ --input-type legal

# Con OpenRouter
python main.py --lens full --file paper.txt --agent --profile technical \
  --backend openrouter --model mistralai/mistral-7b-instruct
```

---

## 8. Certificado PDF de Auditoría

El módulo `GenesisCertifier` genera un reporte PDF autónomo que incluye:

- Identificador único `GEN-{SHA8}-{timestamp}`
- Radar chart 5D con matplotlib
- Sección de proximidad κD con barra visual ASCII
- **Análisis de Atestación TDA**: narrativa del agente LLM si fue ejecutado antes del sellado
- **Firma de Integridad**: SHA-256(texto · veredicto · score · narrativa) — reproducible

---

## 9. Firma de Integridad de Auditoría

```
AUDIT-HASH = SHA-256("TEXT:{texto}|VERDICT:{veredicto}|SCORE:{score:.6f}|NARRATIVE:{narrativa}")
```

Aparece en la UI (tab TERMINAL, bloque sellado), en el footer del PDF, y en la página de atestación del agente.

**Forensic Ledger (v2.0):**

```
ENTRY-HASH = SHA-256(JSON_canónico{doc_hash, kappa_d, manifold_score, timestamp, verdict, version})
```

Separación deliberada: el AUDIT-HASH vincula el contenido al análisis; el ENTRY-HASH vincula el análisis al registro forense. Ambos son independientes y verificables.

---

## 10. Resultados de Calibración & Benchmark

### 10.1 Calibración Original (11 de Marzo de 2026)

Sesión ejecutada con documentos reales:

| Documento | ManifoldScore | Coherencia Topológica | Veredicto |
|---|---|---|---|
| Paper técnico (Project Manifold 0.56) | 0.5261–0.5596 | 0.3758–0.4514 | TENSION / REVIEW |
| Contrato corporativo estándar | 0.4027–0.5261 | 0.0544–0.3758 | REVIEW |
| NIST RMF 2.0 (documento completo) | 0.6836 | alta | TENSION |

### 10.2 Suite de Benchmark v2.0 (14 de Marzo de 2026)

Benchmark reproducible sobre 6 documentos estratégicos. Ejecutar con: `python tests/benchmark.py`

| # | Documento | Palabras | ManifoldScore | Δ a κD | Veredicto | Riesgo Dominio |
|---|---|---|---|---|---|---|
| 1 | Contrato balanceado — baseline positivo | 309 | 0.5225 | −0.0375 | TENSION | 0.0000 |
| 2 | Cláusulas abusivas — manipulación unilateral | 293 | 0.5410 | −0.0190 | TENSION | **0.0476** |
| 3 | Paper técnico — alta coherencia | 586 | 0.5300 | −0.0300 | TENSION | 0.0000 |
| 4 | Gaslighting extremo | 328 | **0.5046** | −0.0554 | TENSION | 0.0294 |
| 5 | T&C 600+ tokens — estrés topológico | 652 | 0.5190 | −0.0410 | TENSION | 0.0000 |
| 6 | Test de estrés — 15 tokens | 15 | **0.5987** | +0.0387 | ANOMALY | 0.0000 |

**Resultados del Diff Semántico:**

| Comparación | Wasserstein H₁ | Bottleneck | ISI | Veredicto |
|---|---|---|---|---|
| Contrato limpio → Manipulado | 0.5994 | 0.3447 | **0.4648** | MANIFOLD_RUPTURE ⚠ |
| Contrato → Gaslighting | 0.6082 | 0.3447 | **0.4570** | MANIFOLD_RUPTURE ⚠ |
| Paper técnico → T&C legal | 0.7587 | 0.3435 | 0.3226 | MANIFOLD_RUPTURE ⚠ |
| Gaslighting → Manipulado | 0.0735 | 0.0386 | 0.9344 | STRUCTURAL_CHANGE ✓ |
| Idéntico — control | 0.0000 | 0.0000 | **1.0000** | IDENTICAL ✓ |

**Interpretaciones clave:**

**La Honestidad del Manifold:** Los scores en [0.50–0.54] para documentos en lenguaje natural son esperados y científicamente significativos. Reflejan fricción estadística genuina cerca de κD=0.56. Un sistema que siempre puntúa limpiamente por encima del umbral es sospechoso; este es un instrumento calibrado, no un clasificador binario.

**Transición entropía/topología:** A ~300 palabras, la entropía domina (`w=0.45`) sobre la topología (`w=0.25`). A 600+ palabras, la topología sube a `w=0.40` — el sistema lee *cómo está conectado el pensamiento*, no solo *qué* hay. La topología necesita superficie para desplegarse.

**Arquitectura de detección redundante:** El contrato abusivo obtuvo 0.5410 — cerca del contrato limpio (0.5225). Pero LawAuditor señaló independientemente `riesgo_dominio=0.0476` donde el contrato limpio tenía `0.0000`. Radar + sonar: si una métrica no lo detecta, la otra sí.

**Nota metodológica:** N=9 documentos en dos sesiones. Las métricas reflejan propiedades estadísticas estructurales — no validan el contenido semántico. Para producción, calibrar con `TDAAttestator.calibrate_threshold()` sobre corpus propio.

---

## 11. Integridad y Proveniencia

### SHA-256 Master Digest (v1.1)

```
c23c10c85682f5477eb2c7b90eeb950383dfa028cbb9fd8ce9475069e8c86c3b
```

Calculado sobre todos los archivos `.py` del motor en orden léxico (base v1.1). Los hashes de v2.0 se agregan por el mantenedor del proyecto tras cada release.

```bash
# Linux / Mac
find . -name "*.py" | sort | xargs sha256sum | sha256sum

# PowerShell
Get-ChildItem -Recurse -Filter *.py | Sort-Object FullName |
  ForEach-Object { Get-FileHash $_.FullName -Algorithm SHA256 } |
  Select-Object Hash | ConvertTo-Json | sha256sum
```

### OpenTimestamps — Prueba de Prioridad Temporal

**v1.1 — Codebase original (7 de Marzo de 2026)**

```
SHA-256 : 2b83a6e5696d7930da5a23eeb9e026e63ce9e603e87501cc3c3fc435b98d0f4b
OTS file: Omni-Scanner-Semantico-v1_0_zip.ots
```

**v2.1 — Distribución en inglés, detectores bilingüe (15 de Marzo de 2026)**

```
SHA-256 : a90da99f4367e1a9ad8d105335cedd8638ce17f958985d1063d671bfa385f093
OTS file: omni-scanner-en_zip.ots
```

**v2.0 — Distribución en español, limpia (14 de Marzo de 2026)**

```
SHA-256 : 09ef7ce063c5f817af81513b3361cadf1c4b7e4edf4b5a296bb3d541ab37a3b8
OTS file: omni-scanner-es_zip.ots
```

```bash
pip install opentimestamps-client

ots verify Omni-Scanner-Semantico-v1_0_zip.ots   # v1.1
ots verify omni-scanner-en_zip.ots               # v2.0 EN
ots verify omni-scanner-es_zip.ots               # v2.0 ES
```

Los tres registros están anclados en la blockchain de Bitcoin. Los hashes SHA-256 son determinísticos — recomputarlos contra los archivos ZIP originales debe producir valores idénticos.

### Publicación Científica

**Project Manifold 0.56: Semantic Thermodynamic Invariance and the Durante Constant (κD = 0.56) as a Universal AGI Stability Threshold**  
[zenodo.org/records/18901544](https://zenodo.org/records/18901544) — v43.0, 7 de Marzo de 2026

### Registro de Propiedad Intelectual

Expediente TAD EX-2026-18792778 — Trámite a Distancia, República Argentina.

---

## 12. Alineación Metodológica

El sistema incorpora criterios inspirados en el **NIST AI Risk Management Framework (RMF)**:

- **Confiabilidad**: scores consistentes y reproducibles ante el mismo input
- **Transparencia**: cada veredicto incluye desglose de scores individuales, pesos y flags
- **Explicabilidad**: el agente LLM traduce las métricas a lenguaje natural auditable
- **Trazabilidad forense**: cada veredicto puede firmarse con hash SHA-256 inmutable y prepararse para anclaje en blockchain

Esta es una alineación metodológica de criterios de diseño, no una certificación formal del NIST.

---

## 13. Limitaciones

- El ManifoldScore mide propiedades estadísticas estructurales. Un texto bien redactado con vocabulario técnico consistente puede obtener scores altos independientemente de la validez de su contenido.
- Calibración actual: N=3 documentos. Para producción, usar `calibrate_threshold()` con corpus propio.
- La homología persistente en modo fallback (sin Ripser) tiene la clasificación H₁ deshabilitada. El algoritmo DFS genera `persistencia ≈ diámetro/2` para todos los ciclos por construcción geométrica, haciendo la clasificación individual de ciclos poco confiable. ManifoldScore, coherencia y Diff Semántico funcionan completamente. Instalar `ripser` para auditoría H₁ completa: `pip install ripser persim`
- El Forensic Ledger genera payloads listos para blockchain pero no realiza el broadcast — eso requiere wallet o nodo externo.
- El Live Stream Monitor analiza texto estático dividido en ventanas; la interceptación de streams en tiempo real depende de la API del proveedor.
- El agente LLM requiere Ollama corriendo localmente o una API key de OpenRouter.

## 14. Benchmark Reproducible

El directorio `tests/` contiene una suite de benchmark completa para verificar el sistema de forma independiente:

```
tests/
├── benchmark.py              # Ejecutar: python tests/benchmark.py
├── benchmark_demo.ipynb      # Notebook Jupyter con visualizaciones
├── benchmark_docs/           # 6 documentos de prueba estratégicos
│   ├── 01_contract_clean.txt          (309 palabras — baseline positivo)
│   ├── 02_contract_manipulated.txt    (293 palabras — cláusulas abusivas)
│   ├── 03_technical_paper.txt         (586 palabras — alta coherencia)
│   ├── 04_gaslighting_extreme.txt     (328 palabras — manipulación psicológica)
│   ├── 05_long_legal_600tokens.txt    (652 palabras — estrés topológico)
│   └── 06_short_text_stress.txt       (15 palabras  — límite del umbral)
└── results/
    ├── benchmark_results.json         # Resultados pre-calculados (legible por máquina)
    └── benchmark_summary.txt          # Resultados pre-calculados (legible por humano)
```

**Para reproducir:**
```bash
cd <raíz del proyecto>
python tests/benchmark.py
# Con TDA completo (recomendado):
pip install ripser persim && python tests/benchmark.py
```

Los resultados esperados coinciden con las tablas de la Sección 10.2.

---

## Autor y Contacto

**Gonzalo Emir Durante**  
Arquitecto — Project Manifold 0.56 / Protocolo ANEXA Ultra v4.0

- GitHub: [github.com/Leesintheblindmonk1999](https://github.com/Leesintheblindmonk1999)
- LinkedIn: [linkedin.com/in/gonzalo-emir-durante-8178b6277](https://www.linkedin.com/in/gonzalo-emir-durante-8178b6277/)
- Zenodo: [zenodo.org/records/18901544](https://zenodo.org/records/18901544)
