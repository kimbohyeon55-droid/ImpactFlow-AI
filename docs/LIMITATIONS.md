# Limitations

## Product validation

- No completed customer interviews, paid pilots, contracts, revenue, or pricing validation are documented.
- The buyer, procurement path, channel, and willingness to pay remain hypotheses.
- The current workflow has been demonstrated with synthetic controlled data rather than authorized external operational data.

## Model evaluation

- Training, locked-test, challenge, and robustness text are synthetic.
- High locked-test scores may reflect controlled templates and vocabulary.
- Sentiment robustness Macro-F1 falls to 0.258476 on the perturbation set.
- The models have not been evaluated on representative external Korean field data.
- Human review priority is an ordering mechanism, not a probability, confidence score, or measured workload reduction.

## Privacy and security

- The local operator and operating-system account can access selected raw files.
- The MVP is single-user and has no production authentication, authorization, tenant isolation, encryption-key management, or compliance certification.
- Privacy Guard is a deterministic product safeguard, not a legal-compliance guarantee.

## Evidence interpretation

- `VERIFIED` means reproducible and traceable within the stored calculation and protected source references.
- It does not prove external truth, causality, statistical significance, program impact, or field validity.

## Deployment

- The project is a local MVP, not a production SaaS deployment.
- Performance has not been benchmarked beyond the intended small-file development scope.
