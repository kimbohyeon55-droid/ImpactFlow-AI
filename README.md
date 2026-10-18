# ImpactFlow AI

**Measure. Prove. Improve.**  
Turn field-program records into traceable evidence and reviewable impact reports.

ImpactFlow AI is a local-first MVP for program managers who need to validate survey files, protect personal information, calculate reproducible metrics, review qualitative classifications, trace conclusions to protected source rows, map outcomes, and assemble evidence-backed reports.

> Portfolio status: documentation-first publication candidate. Source code, datasets, model binaries, and full evaluation artifacts remain excluded until ownership, licensing, competition, and privacy checks are approved.

## Why this project exists

Program evaluation often spans spreadsheets, manual cleaning, separate privacy steps, statistical calculations, qualitative review, and report editing. That fragmentation makes it difficult to answer a basic review question: **where did this conclusion come from?**

ImpactFlow AI connects the workflow:

```text
CSV/XLSX
  -> data validation
  -> privacy protection
  -> deterministic analytics
  -> local NLP suggestions
  -> human confirmation
  -> evidence trace
  -> impact mapping
  -> report assembly
```

## Implemented MVP

- CSV/XLSX ingestion and versioned datasets
- Deterministic data-quality findings and scoring
- Privacy Guard with a protected analysis dataset
- Human-confirmed question mapping
- Reproducible quantitative metrics with provenance
- Local qualitative classifiers for sentiment, theme, and improvement need
- Risk- and disagreement-based human-review priority
- Evidence Trace from conclusion to calculation, question, and protected row key
- Impact Map with explicit evidence levels
- Evidence-backed report generation and export
- Responsive Vue workspace with a reusable Evidence Drawer

## Engineering principles

- **Numbers by code:** quantitative results come from deterministic services.
- **Language by AI:** local NLP proposes labels; it does not establish verified facts.
- **Final meaning by humans:** reviewers can confirm, correct, or exclude suggestions.
- **Evidence before prose:** reports assemble supported claims instead of inventing analysis.
- **Local first:** the MVP requires no paid API, cloud service, Docker runtime, or external database.

## Technical stack

| Layer | Technology |
|---|---|
| Frontend | Vue 3, TypeScript, Vite, Pinia, Vue Router, ECharts |
| Backend | FastAPI, Pydantic, SQLAlchemy, Alembic |
| Storage | SQLite for the local MVP; SQLAlchemy keeps a migration path open |
| Data | pandas, openpyxl |
| NLP | scikit-learn TF-IDF, Logistic Regression, LinearSVC, joblib |
| Reports | ReportLab, pypdf |
| Testing | pytest, Vitest, Vue Test Utils |

## Controlled evaluation snapshot

All figures below come from synthetic controlled datasets. They are not field-accuracy, customer-impact, or causal claims.

| Area | Repository evidence |
|---|---:|
| Dirty demo dataset | 180 rows × 18 columns |
| Analytical records | 176 |
| Data-quality findings | 37 |
| Data-quality score | 97.1 |
| Synthetic PII detections | 720 |
| Deterministic metrics | 104; all 104 trace records verified |
| Synthetic NLP dataset | 3,840 samples plus a 192-sample challenge set |
| Locked-test Macro-F1 | sentiment 0.9602; theme 0.9531; improvement 0.9861 |
| Robustness Macro-F1 | sentiment 0.2585; theme 0.9374; improvement 0.7925 |
| Report integrity | 116 supported claims; 0 unsupported |

The sharp sentiment robustness drop is intentionally reported. The production baseline was retained because the evaluated replacement policy did not meet the promotion rule.

## Architecture and documentation

- [Architecture](docs/ARCHITECTURE.md)
- [Development workflow](docs/DEVELOPMENT_WORKFLOW.md)
- [NLP training and evaluation](docs/NLP_TRAINING_AND_EVALUATION.md)
- [Contributions](docs/CONTRIBUTIONS.md)
- [AI assistance](docs/AI_ASSISTANCE.md)
- [Limitations](docs/LIMITATIONS.md)
- [Publication scope](docs/PUBLICATION_SCOPE.md)
- [Proposed public file list](PUBLIC_FILE_MANIFEST.md)
- [Validation report](VALIDATION_REPORT.md)

## Current status

The local MVP implements the end-to-end synthetic demo workflow. The next validation stage is external: observe real user workflows, test authorized de-identified data, evaluate with independently human-labelled text, identify the buyer and procurement path, and validate repeat use and pricing.

## Author

Project owner: **Bohyeon Kim** (`kimbohyeon55-droid`).  
Contribution attribution is currently based on local project documentation because the workspace has no Git commit history yet.

## License

No public license has been selected. Until the owner explicitly chooses one, this candidate grants no reuse rights and source publication remains on hold.
