# Proposed Public File List

## Included in this documentation-first candidate

```text
README.md
PUBLIC_FILE_MANIFEST.md
VALIDATION_REPORT.md
docs/
  AI_ASSISTANCE.md
  ARCHITECTURE.md
  CONTRIBUTIONS.md
  DEVELOPMENT_WORKFLOW.md
  LIMITATIONS.md
  NLP_TRAINING_AND_EVALUATION.md
  PUBLICATION_SCOPE.md
```

## Proposed after publication approval

```text
.env.example
.gitignore
LICENSE                         # owner decision required
README.md
backend/
  alembic.ini
  alembic/
  app/
  pytest.ini
  requirements.txt
  tests/
frontend/
  index.html
  package.json
  pnpm-lock.yaml
  pnpm-workspace.yaml
  src/
  tsconfig*.json
  vite.config.ts
scripts/
  README.md
  calculate_ground_truth.py
  generate_demo_data.py
  generate_qualitative_training_data.py
  generate_qualitative_robustness.py
  qualitative_ai_common.py
  train_qualitative_models.py
  evaluate_qualitative_models.py
  evaluate_qualitative_ensemble.py
  analyze_qualitative_errors.py
  audit_qualitative_dataset_leakage.py
  verify_demo_dataset.py
  verify_qualitative_training_data.py
  verify_qualitative_runtime.py
docs/
  [selected product and engineering documentation]
data/sample/
  [synthetic demo data only, after data-license decision]
evaluation/
  metrics.json                   # sanitized aggregate results
  dataset_manifest.json
```

## Deliberately excluded

```text
.git/
.env
.venv/
node_modules/
.pnpm-store/
data/local/
data/private/
data/generated/
uploads/
exports/reports/
tmp/
artifacts/ui_stage15b/
submission/
docs/prompt-pack/
models/**/*.joblib
artifacts/**/misclassified_samples.csv
official competition source files
```

Model binaries, screenshots, full evaluation artifacts, and synthetic text datasets require separate approval rather than automatic inclusion.
