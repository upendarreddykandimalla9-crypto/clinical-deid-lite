# Clinical De‑ID Lite — Regex‑first PHI Redaction

A lightweight, easily auditable PHI redaction tool for clinical text.
Focuses on common identifiers (names, dates, phones, emails, MRNs) using robust regex
and simple dictionaries. Ships with tests.

> For production, complement with manual review and policy controls.

## Quickstart
```bash
python -m venv .venv && . .venv/bin/activate
pip install -r requirements.txt
python deid.py --input examples/sample.txt --output artifacts/redacted.txt
pytest -q
```

## What it catches
- Names (given/surnames dictionaries & capitalized tokens)
- Dates (multiple formats)
- Phones, emails
- Medical Record Numbers (MRN) patterns

Outputs both redacted text and a JSON audit log of spans replaced.
