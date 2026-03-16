# CHANGELOG

All notable changes to Omni-Scanner are documented here.  
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [2.0] — 2026-03-14

### Added
- **`core/semantic_diff.py`** — Topological Semantic Diff engine
  - Wasserstein p=2 distance over H₁ persistence diagrams
  - Bottleneck distance (maximum perturbation — "legal wormhole" detector)
  - Invariant Similarity Index (ISI): if ISI < κD=0.56, triggers Structural Manipulation Alert
  - Ghost Point `[0.0, 0.0]` for comparing against empty diagrams (birth of chaos from nothing)
  - `compare_manifolds()`, `compare_series()`, `score_series()`, `quick_diff()`
- **`core/batch_auditor.py`** — Bulk Audit Engine
  - Batch processing of `.txt` / `.pdf` (PyMuPDF) / `.docx` (python-docx)
  - CIR (Corpus Integrity Rate): fraction of documents passing κD
  - Professional Excel export with Durante conditional formatting (green/red by score)
  - CSV export with UTF-8 BOM for Windows compatibility
- **`core/ledger_vanguard.py`** — Forensic Ledger
  - SHA-256 over canonical JSON payload (doc_hash + score + timestamp + verdict)
  - Blockchain Readiness: OpenTimestamps payload + Ethereum calldata
  - Independent verification via `verify_entry()`
- **`core/stream_monitor.py`** — Live Stream Monitor / Invariance Shield
  - Sliding window analysis over LLM output text
  - Shield states: OK / WARNING / INCOHERENCE DISCONNECTION
  - N consecutive drops below κD triggers the mathematical safety valve
- **`core/threshold_calibrator.py`** — Dynamic κD Calibration
  - Real-time κD adjustment without re-running full pipeline
  - Threshold zones: Noise / Pre-threshold / Durante Equilibrium Point / Post-threshold / Over-restriction
- **`interface/app.py`** — 3 new tabs (total: 10)
  - `◑ SEMANTIC DIFF` — Durante Thermometer (ISI bar), Structured Verification generator
  - `≣ FORENSIC AUDIT` — Bulk batch + Forensic Ledger signing + Download Center
  - `⚙ ACTIVE SURVEILLANCE` — κD slider + Live Stream Monitor
  - Global κD Master Slider in sidebar (affects all modules)
- **`tests/`** — Reproducible benchmark suite
  - 6 strategic documents (balanced contract, abusive contract, technical paper, gaslighting, T&C 600+ tokens, 15-token stress)
  - `tests/benchmark.py` — standalone reproducible script
  - `tests/benchmark_demo.ipynb` — Jupyter notebook with visualizations
  - Pre-computed results in `tests/results/`
- `requirements.txt`, `.gitignore`, `.env.example`, `CHANGELOG.md`
- `LICENSE.md` (BUSL-1.1), `SECURITY.md`

### Fixed
- **`core/tda_attestation.py`** — H₁ classification disabled in fallback mode (without Ripser)
  - Root cause: DFS fallback generates `persistence ≈ diameter/2` for all cycles by construction (`death = max(entry_d, dist)`), making `ratio ≈ 2.0` regardless of document quality
  - Fix: H₁ classification only runs with Ripser. Fallback reports `TOPOLOGICALLY_SIMPLE` honestly
  - ManifoldScore, coherence, and Semantic Diff unaffected
- **`core/semantic_diff.py`** — Diff now uses raw persistence diagrams directly
  - Previously extracted H₁ pairs from `report.h1_pairs` (empty in fallback)
  - Fix: `_get_raw_diagrams()` computes diagrams from embeddings, bypassing the classifier

### Changed
- Semantic Diff `_build_summary()` messages translated to English in EN distribution
- `batch_auditor.py`: TIC renamed to CIR (Corpus Integrity Rate) in EN distribution
- Benchmark documents rewritten with stronger structural contrast for reliable diff results

### OTS Records
| Version | SHA-256 | OTS File |
|---|---|---|
| v1.1 original | `2b83a6e5696d7930da5a23eeb9e026e63ce9e603e87501cc3c3fc435b98d0f4b` | `Omni-Scanner-Semantico-v1_0_zip.ots` |
| v2.0 EN | `a90da99f4367e1a9ad8d105335cedd8638ce17f958985d1063d671bfa385f093` | `omni-scanner-en_zip.ots` |
| v2.0 ES | `09ef7ce063c5f817af81513b3361cadf1c4b7e4edf4b5a296bb3d541ab37a3b8` | `omni-scanner-es_zip.ots` |

---

## [1.1] — 2026-03-13

### Added
- **`engines/reasoning_agent.py`** — LLM Reasoning Agent
  - Backends: Ollama (local) + OpenRouter (API)
  - Profiles: Technical / Audit / Integrity
- **`interface/app.py`** — Tab `◎ AGENTE IA`
- **`reports/generators/genesis_certifier.py`** — Audit Integrity Hash (SHA-256)
  - `SHA-256("TEXT:{text}|VERDICT:{verdict}|SCORE:{score:.6f}|NARRATIVE:{narrative}")`
  - PDF page: Security Attestation Analysis

### Changed
- App updated from v5.5 to v1.1 with 8 tabs

---

## [1.0] — 2026-03-11

### Added
- Initial public release
- `core/`: ManifoldEngine, EntropyAnalyzer, MultifractalProcessor, TopologyMapper, TDAAttestator
- `engines/`: FullDiagnostic, LawAuditor, SocialEngineer, DevVerifier, FinanceScanner
- `interface/app.py` — 7-tab Streamlit interface (Dark-Amber theme)
- `reports/generators/genesis_certifier.py` — PDF with 5D radar chart
- `logs/forensic_ledger.py` — append-only JSONL ledger
- `protocols/` — ANEXA Ultra v4.0 configuration
- `main.py` — CLI with `--lens`, `--file`, `--sign`, `--agent`

### Calibration
- Durante Constant κD = 0.56 validated across 3 document types
- Paper: ManifoldScore 0.5261–0.5596 (TENSION/REVIEW)
- Contract: 0.4027–0.5261 (REVIEW)
- NIST RMF 2.0: 0.6836 (TENSION)

### Scientific publication
- DOI: [10.5281/zenodo.18901544](https://zenodo.org/records/18901544) — v43.0
- IP Registry: EX-2026-18792778 (Argentina)
