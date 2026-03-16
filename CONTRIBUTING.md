# Contributing to Omni-Scanner Semantic

Thank you for your interest in contributing. Before submitting anything, read this document and the [LICENSE](LICENSE.md) and [SECURITY](SECURITY.md) files.

## What contributions are welcome

- Bug reports with reproducible steps
- Documentation improvements (typos, clarity, translations)
- Benchmark additions (new test documents with known properties)
- Performance improvements that do not alter algorithmic behavior
- Compatibility fixes for newer Python / library versions

## What requires prior discussion

- Changes to the ManifoldScore pipeline, entropy weights, or κD threshold logic — these affect the Durante Constant's behavior and require author approval
- New domain engines (`engines/`) that claim Durante Invariance certification
- Any change to `core/tda_attestation.py` that modifies H₁ classification logic

Contact the author before opening a PR for any of the above.

## How to report a bug

1. Check existing issues first
2. Open an issue with: Python version, OS, exact error message, minimal reproducible example
3. For security vulnerabilities, follow the [Vulnerability Disclosure Policy](SECURITY.md#5-vulnerability-disclosure-policy-vdp) — **do not open a public issue**

## Development setup

```bash
git clone https://github.com/Leesintheblindmonk1999/omni-scanner
cd omni-scanner
pip install -r requirements.txt
pip install ripser persim          # recommended for full TDA
python tests/benchmark.py          # verify everything works
python -m streamlit run interface/app.py
```

## Running the benchmark

```bash
python tests/benchmark.py
```

Expected output: scores in [0.5046, 0.5987], ISI=0.4648 for clean→manipulated diff. If your output differs significantly, something in the pipeline changed.

## Code style

- Python 3.10+
- No external formatter required — match the style of the file you're editing
- Docstrings in the language of the file (ES for Spanish distribution, EN for English)
- No hardcoded API keys — use `.env` via `python-dotenv` or environment variables

## Attribution

All contributions must preserve the authorship notices, Zenodo DOI, and IP registry references in the source files. See Section 5.1 of [LICENSE.md](LICENSE.md).
And Donations Here: https://buymeacoffee.com/thaliondris