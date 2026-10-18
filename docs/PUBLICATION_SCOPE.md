# Publication Scope

## Safe in the current documentation-first candidate

- English portfolio README
- architecture and workflow descriptions
- synthetic-only aggregate metrics with explicit caveats
- model architecture, split design, hashes, and evaluation methodology
- limitations and AI-assistance disclosure
- proposed file manifest

## Hold until owner approval and rights confirmation

- backend and frontend source code
- Alembic migrations and test suite
- data-generation, training, and evaluation scripts
- synthetic CSV/XLSX files and generated text splits
- model binaries (`.joblib`)
- detailed evaluation JSON, confusion matrices, and misclassified samples
- product screenshots and presentation files
- prompt pack and internal stage instructions

## Exclude from any public repository

- `.env` files or credentials
- local SQLite databases
- uploads and raw/private datasets
- logs, temporary files, caches, virtual environments, and Node modules
- generated reports that may contain row-level or organization-specific content
- private interview notes, consent records, personal identifiers, or contact details
- official competition forms and copied notice text unless redistribution rights are confirmed
- absolute local filesystem paths and machine-specific metadata

## Required publication decisions

1. Confirm that the owner may publish the implementation and generated assets.
2. Select a repository license or explicitly retain all rights.
3. Confirm competition rules and submission status do not restrict pre-result publication.
4. Decide whether synthetic datasets receive a separate data license.
5. Decide whether model binaries will be released and under what terms.
6. Rebuild sanitized artifacts that contain local absolute paths.
7. Run secret, PII, binary, and dependency-license scans on the exact release tree.

No GitHub repository should be created until these decisions are recorded.
