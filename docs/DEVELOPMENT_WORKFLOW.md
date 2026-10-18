# Development Workflow

## Evidence-first stage model

Development was organized as sequential gates rather than feature-first prototyping:

1. Local repository and architecture baseline
2. Scope and customer-discovery framework
3. Evidence-first data model
4. Synthetic ground-truth dataset
5. CSV/XLSX ingestion and versioning
6. Data-quality engine
7. Privacy Guard and protected dataset
8. Human-confirmed question mapping
9. Deterministic analytics and provenance
10. Evidence Trace
11. Deterministic insights
12. Impact mapping
13. Local qualitative AI and human review
14. Evidence-grounded reporting
15. Robustness evaluation and product UX

Each stage added documentation, an architectural decision record, implementation, and regression tests. Scope rules prioritized privacy, reproducibility, and provenance over feature breadth.

## Reproducibility controls

- Fixed seeds for synthetic data and robustness generation
- Dataset manifests with SHA-256 hashes
- Disjoint template families across train, validation, and locked test splits
- Locked test excluded from model selection
- Model metadata containing library versions, split sizes, dataset hash, and metrics
- Deterministic analytics and idempotent evidence generation
- Regression tests for privacy, metrics, evidence, reports, and model integration

## Local verification commands

The original workspace documents these commands:

```powershell
cd backend
.\.venv\Scripts\python.exe -m pytest

cd ..\frontend
npm run test
npm run build
```

The portfolio package does not include the local virtual environment, Node modules, databases, uploads, generated reports, or private runtime state.
