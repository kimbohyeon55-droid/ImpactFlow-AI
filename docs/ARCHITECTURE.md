# Architecture

## System boundary

```text
Browser
  -> Vue 3 / Vite frontend
  -> FastAPI HTTP API
  -> application services
  -> SQLAlchemy repositories
  -> SQLite
```

The MVP runs locally without Docker, paid APIs, cloud services, or a separately installed database.

## Backend domains

- **Ingestion:** parses CSV/XLSX and creates immutable dataset versions.
- **Validation:** applies deterministic schema and value rules and calculates a quality score.
- **Privacy:** detects configured PII categories and creates masked analysis rows.
- **Mapping:** maps survey questions to an analysis schema and records human confirmation.
- **Analytics:** computes deterministic metrics and their operands.
- **Qualitative AI:** loads hash-validated local classifiers and stores suggestions separately from human decisions.
- **Insights:** applies deterministic rules to verified metrics.
- **Evidence:** connects conclusions, metrics, calculations, questions, and protected row keys.
- **Impact:** maps inputs, activities, outputs, and outcomes while preserving evidence level.
- **Reports:** assembles supported claims and blocks integrity conflicts.

## Trust boundary

Raw rows are limited to ingestion, validation, privacy processing, and an explicitly authorized preview. Analytics, NLP, dashboards, evidence, and reports use the protected normalized representation. Evidence APIs expose row keys and contribution roles rather than raw source values.

## Data lifecycle

```text
Original file
  -> immutable dataset version
  -> validation findings
  -> privacy findings without matched raw text
  -> protected dataset snapshot
  -> confirmed analysis schema
  -> analysis run and metrics
  -> evidence records
  -> insights / impact claims
  -> report snapshot
```

## Design decisions

- SQLite is appropriate for a single-user local MVP; multi-tenant authorization is outside the current scope.
- SQLAlchemy and Alembic isolate persistence concerns and preserve a future PostgreSQL migration path.
- Quantitative analysis remains deterministic.
- Model suggestions cannot become verified evidence without an explicit human-review state.
- Report generation consumes supported claims; it does not recalculate statistics or access raw rows.

## Known architectural limits

The MVP has no production authentication, tenant isolation, cloud deployment, real-time collaboration, billing, government API integration, or formal compliance certification.
