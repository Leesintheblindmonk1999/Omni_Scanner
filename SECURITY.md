# SECURITY.md — Omni-Scanner Semántico v2.0
## Security Policy, Intellectual Property Notice & Usage Constraints

**Maintainer:** Gonzalo Emir Durante  
**Contact:** [LinkedIn](https://www.linkedin.com/in/gonzalo-emir-durante-8178b6277/) · [GitHub](https://github.com/Leesintheblindmonk1999)  
**Last updated:** March 2026  
**Version:** 2.0 — Protocolo ANEXA Ultra v4.0

---

## 1. Intellectual Property Notice

### 1.1 Registered Authorship

The theoretical framework, algorithmic methodology, and software implementation contained in this repository constitute original intellectual work authored by **Gonzalo Emir Durante** ("the Author"), protected under the following registrations:

| Record | Identifier |
|---|---|
| Argentine IP Registry (TAD) | Expediente EX-2026-18792778 |
| Scientific Publication (Zenodo) | DOI [10.5281/zenodo.18901544](https://zenodo.org/records/18901544) — v43.0, March 7, 2026 |
| Blockchain timestamp (Base v1.1)(OTS) | `c23c10c85682f5477eb2c7b90eeb950383dfa028cbb9fd8ce9475069e8c86c3b` | 
| Master Digest (SHA-256, v2.0-en) | `a90da99f4367e1a9ad8d105335cedd8638ce17f958985d1063d671bfa385f093` | 
| Master Digest (SHA-256, v2.0-es) | `09ef7ce063c5f817af81513b3361cadf1c4b7e4edf4b5a296bb3d541ab37a3b8` |
**By downloading, cloning, forking, or otherwise accessing this repository, you acknowledge that you have been notified of the above intellectual property claims and the constraints described in this document.**

### 1.2 The Durante Constant (κD = 0.56)

The value `κD = 0.56` as a semantic stability threshold, and its derivation from five independent mathematical convergences (Statistical Thermodynamics, Percolation Theory, Rate-Distortion Theory, Lyapunov Stability, and the Golden Ratio), constitute a **named theoretical contribution** of the Author as documented in the scientific publication cited above.

This specific application of κD = 0.56 to semantic manifold analysis, topological integrity scoring, and the Invariant Similarity Index (ISI) computation is **not in the public domain**. Any software, model, or system that:

- uses κD = 0.56 as a semantic stability threshold,
- implements the ManifoldScore pipeline as described in this repository, or
- derives a substantially similar threshold through reformulation of the Author's methodology,

without explicit written license from the Author, may constitute infringement of the Author's intellectual property rights.

### 1.3 Patent and Derivative Work Notice

No third party may file patent applications, trademark registrations, or equivalent IP claims on:

- the Durante Constant (κD = 0.56) or any reformulation thereof,
- the Topological Invariance methodology as described herein,
- the Semantic Diff algorithm (Wasserstein + Bottleneck over H₁ persistence diagrams applied to NLP),
- the Corpus Integrity Rate (TIC) metric,
- or any derivative work that reproduces the core algorithmic logic of this repository,

without prior written authorization from the Author. The prior publication date established by the Zenodo DOI and the OpenTimestamps blockchain record constitutes evidence of authorship priority.

---

## 2. Usage Constraints

### 2.1 Permitted Uses

The following uses are permitted without requiring explicit license:

- **Academic and research use:** analysis, citation, reproduction in papers, and non-commercial experimentation.
- **Personal and educational use:** learning, auditing documents for personal purposes, and non-commercial evaluation.
- **Open-source integration:** incorporation into non-commercial open-source projects, provided authorship is attributed per Section 2.3.

### 2.2 Restricted Uses — License Required

The following uses require a **separate written license agreement** with the Author:

- **Commercial deployment:** any use of this software or its methodology in a product or service offered to third parties for compensation, directly or indirectly.
- **SaaS and API services:** offering Omni-Scanner capabilities as a hosted service, API endpoint, or subscription product.
- **Training data and model training:** use of this software's outputs — including ManifoldScore values, TDA reports, Semantic Diff results, or any structured output — as training data for machine learning models, language models, or AI systems, whether commercial or non-commercial.
- **Government and regulatory applications:** use in official legal proceedings, regulatory filings, or governmental decision-making processes without explicit written authorization.
- **Rebranding:** distribution of this software or derivatives under a different name without clear attribution to the original Author and methodology.

To inquire about licensing, contact the Author via the channels listed at the top of this document.

### 2.3 Attribution Requirements

Any permitted use must include the following attribution in documentation, user interfaces, and academic citations:

```
Omni-Scanner Semántico — based on the Durante Semantic Stability Framework
Author: Gonzalo Emir Durante
Publication: DOI 10.5281/zenodo.18901544
Repository: github.com/Leesintheblindmonk1999
```

---

## 3. Algorithmic Integrity Disclaimer

### 3.1 Nature of the Scores

The ManifoldScore, coherence index, entropy score, fractal dimension, and all derived metrics produced by this software are **statistical measures of structural properties** of text. Specifically:

- A ManifoldScore ≥ κD (0.56) indicates that the document's lexical and topological structure is consistent with the reference stability model. **It does not certify the factual accuracy, legal validity, financial soundness, or ethical correctness of the document's content.**
- A ManifoldScore < κD indicates structural anomalies in the text. **It does not prove fraud, deception, or malicious intent** — anomalies may arise from legitimate causes including technical vocabulary density, translation artifacts, document fragmentation, or genre-specific writing conventions.
- The Semantic Diff ISI score measures topological distance between two document versions. **It does not establish legal authorship, plagiarism, or intent to deceive** — it identifies structural divergence that warrants human review.

### 3.2 "As-Is" Provision — Reinforced

This software is provided **"as is"**, without warranty of any kind, express or implied. The Author expressly disclaims:

- any warranty that the software is free from errors, vulnerabilities, or inaccuracies;
- any warranty of fitness for a particular purpose, including but not limited to legal analysis, financial decision-making, medical assessment, or security auditing;
- any liability for decisions made by users or third parties based on the software's outputs.

**The software is a decision-support tool.** Any consequential decision — legal, financial, contractual, organizational — remains entirely the responsibility of the human operator who reviews the software's output. The Author bears no liability for such decisions.

### 3.3 Jurisdictional Limitation

The Author makes no representation that this software complies with the laws or regulations of any jurisdiction other than the Argentine Republic. Users are responsible for ensuring that their use of this software complies with applicable local law.

---

## 4. Forensic Validity

### 4.1 Certified Reports

A Forensic Ledger entry generated by this software carries evidentiary weight only under the following conditions:

1. The `entry_hash` in the LedgerEntry can be independently recomputed from the `canonical_json` payload and matches the stored value.
2. The `doc_hash` can be independently verified against the original document text.
3. The software version used to generate the report matches a tagged release whose SHA-256 Master Digest has been published by the Author.
4. The report has not been modified after generation — any post-generation modification invalidates the hash chain.

### 4.2 Author-Certified Releases

Only releases whose Master Digest (SHA-256 over all `.py` files in lexical order) has been published by the Author — either in the Zenodo record, the GitHub release notes, or a timestamped OTS proof — carry the Author's certification for use in formal evidentiary contexts.

Users who generate Forensic Ledger entries from modified or unverified builds do so without the Author's certification and assume full responsibility for the evidentiary claims made.

### 4.3 Verification Procedure

To verify the integrity of a release:

```bash
# Linux / Mac
find . -name "*.py" | sort | xargs sha256sum | sha256sum

# PowerShell
Get-ChildItem -Recurse -Filter *.py | Sort-Object FullName |
  ForEach-Object { Get-FileHash $_.FullName -Algorithm SHA256 } |
  Select-Object Hash | ConvertTo-Json | sha256sum
```

Compare the output against the Master Digest published in the corresponding release.

---

## 5. Reserved Standard & Certification Mark

### 5.1 "Durante Invariance Certification" — Reserved Designation

The following terms, seals, and designations are **exclusively reserved** for use by the Author and officially licensed parties:

- **"Certificación de Invarianza Durante"** / **"Durante Invariance Certification"**
- **"Powered by Durante Invariance (κD = 0.56)"**
- **"Omni-Scanner Certified"** or any equivalent formulation
- The **κD = 0.56 seal** as an indicator of algorithmic compliance with the Author's methodology
- Any badge, mark, or label that implies official certification under the Durante Semantic Stability Framework

**Unauthorized use of these designations constitutes misrepresentation** of the origin and certification status of a report or system, and may constitute trademark infringement and/or unfair commercial practices under applicable law.

### 5.2 Conditions for Authorized Use

Only the following parties may issue reports or products bearing the above designations:

1. **The Author** — Gonzalo Emir Durante, directly or through entities he controls.
2. **Licensed parties** — organizations or individuals holding a current, valid commercial license agreement signed by the Author, explicitly granting the right to use the Durante Invariance certification mark.

A licensed party must, at minimum:

- use an unmodified or Author-approved build of the software,
- generate reports whose `entry_hash` is verifiable against the Author-published Master Digest,
- include the attribution string specified in Section 2.3 of this document.

Reports generated from forked, modified, or unlicensed builds of this software **may not** claim Durante Invariance Certification, regardless of whether they produce numerically similar scores.

### 5.3 Prohibition on Training and Knowledge Distillation

The following uses are **explicitly prohibited** without a prior written commercial contract with the Author:

- **Model training:** using this software's source code, algorithmic logic, outputs (ManifoldScores, TDA reports, ISI values, Semantic Diff results, Forensic Ledger entries, or any structured or unstructured output), or any derivative thereof, as training data, fine-tuning data, or alignment data for machine learning models, language models, neural networks, or AI systems of any kind.
- **Knowledge distillation:** training a separate model, system, or algorithm to replicate, approximate, or emulate the behavior of the Durante Semantic Stability Framework — including the ManifoldScore pipeline, the Topological Diff methodology, or the κD = 0.56 threshold — through exposure to this software's outputs, whether or not the source code is directly used.
- **Benchmark contamination:** including this software's outputs in evaluation benchmarks, leaderboard datasets, or model capability assessments in ways that would commercially advantage a third party without compensation to the Author.
- **Prompt engineering for replication:** using structured interactions with this software to extract its algorithmic logic for the purpose of reimplementing it in a competing system.

These prohibitions apply regardless of whether the resulting model or system is released publicly, kept proprietary, or used internally. The commercial/non-commercial distinction does not create an exception — **academic training use also requires prior written authorization** given the potential for academic-to-commercial pipeline transfer.

---

## 6. Vulnerability Disclosure Policy (VDP)

### 5.1 Scope

This policy applies to security vulnerabilities in the Omni-Scanner Semántico codebase, including but not limited to:

- hash collision vulnerabilities in the Forensic Ledger or audit integrity modules,
- algorithmic manipulation — inputs that cause systematically incorrect scores in a predictable and exploitable way,
- dependency vulnerabilities in `ripser`, `persim`, `scipy`, `openpyxl`, or `streamlit` as used in this project,
- data exfiltration risks in the Streamlit interface or API connector modules.

The following are **out of scope**: general vulnerabilities in upstream libraries unrelated to this project's specific use, theoretical attacks that require unrealistic computational resources, and stylistic or performance issues.

### 5.2 Responsible Disclosure Process

If you discover a vulnerability, follow this process:

1. **Do not disclose publicly** — do not open a GitHub Issue, post on social media, or share with third parties before the Author has had the opportunity to respond.
2. **Contact the Author privately** via LinkedIn direct message or email (available on the LinkedIn profile). Include:
   - a clear description of the vulnerability,
   - steps to reproduce,
   - the potential impact,
   - your suggested fix if available.
3. **Wait for acknowledgment** — the Author will acknowledge receipt within **5 business days** and provide an estimated timeline for resolution.
4. **Coordinated disclosure** — once a fix is available and deployed, the Author will publicly acknowledge the contribution (with the reporter's consent) and the vulnerability will be documented in the release notes.

### 5.3 Good Faith

The Author commits to:

- not pursuing legal action against researchers who discover and responsibly disclose vulnerabilities in good faith,
- acknowledging contributions in release notes and documentation,
- treating disclosed vulnerabilities with priority proportional to their severity.

Researchers who disclose vulnerabilities publicly before following this process, or who exploit vulnerabilities beyond what is necessary for proof-of-concept, are not covered by these good-faith commitments.

---

## 7. Third-Party Dependencies

This software incorporates third-party open-source libraries. Each dependency retains its own license and security policy. Users are responsible for reviewing the licenses of:

| Dependency | License | Purpose |
|---|---|---|
| `streamlit` | Apache 2.0 | Web interface |
| `plotly` | MIT | Visualizations |
| `numpy` / `scipy` | BSD | Numerical computation |
| `scikit-learn` | BSD | TF-IDF embeddings |
| `ripser` | MIT / Apache | Persistent homology |
| `persim` | MIT | Persistence diagram metrics |
| `openpyxl` | MIT | Excel export |
| `fpdf2` | LGPL | PDF generation |
| `networkx` | BSD | Graph analysis |

The Author makes no warranty regarding the security or correctness of these dependencies.

---

## 8. Changes to This Policy

The Author reserves the right to update this document at any time. Material changes will be reflected in the "Last updated" field and documented in the repository's commit history. Continued use of the software after a policy update constitutes acceptance of the updated terms.

---

*This document does not constitute legal advice. For formal legal matters, consult a licensed attorney in your jurisdiction.*
