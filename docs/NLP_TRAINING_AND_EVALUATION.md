# Local NLP Training and Evaluation

## Purpose

The NLP subsystem proposes three labels for protected Korean free-text responses:

- sentiment: positive, neutral, negative
- primary theme: eight operational/content categories
- improvement need: requested change or no requested change

Predictions remain `AI Suggested` until a reviewer confirms, corrects, or excludes them.

## Dataset

- 3,840 fully synthetic Korean samples
- fixed seed: `20260903`
- train: 2,688
- validation: 576
- locked test: 576
- separate challenge set: 192
- dataset SHA-256: `63eceba6d5aa916c688ac007b4ae55fd4340aebcd771d6e9b4fbc52d1e3512bb`

Template families, exact text, normalized text, and sample identifiers were separated across splits. Real participant responses and the product demo rows were not used for model training or selection.

## Candidate architecture

Each task evaluated four scikit-learn pipelines:

```text
word TF-IDF (1,2)    + Logistic Regression
word TF-IDF (1,2)    + LinearSVC
char_wb TF-IDF (2,5) + Logistic Regression
char_wb TF-IDF (2,5) + LinearSVC
```

Candidates were fitted on the training split. Validation Macro-F1 selected a production candidate, and the locked test was evaluated only after selection.

Selected production models:

| Task | Vectorizer | Classifier | Locked-test Macro-F1 |
|---|---|---|---:|
| Sentiment | word TF-IDF | Logistic Regression | 0.960215 |
| Theme | char_wb TF-IDF | Logistic Regression | 0.953105 |
| Improvement | word TF-IDF | Logistic Regression | 0.986110 |

## Robustness evaluation

A separate seed (`20260905`) generated 624 synthetic samples across 13 perturbations, including typos, spacing errors, short responses, mixed sentiment, multiple themes, negation, colloquial language, repetition, punctuation noise, partial sentences, emoji, English mixing, and abbreviations.

Robustness dataset SHA-256: `9289ea29c1d66ab347f11b5e3894032c1f8d60dd6dbf7931bc52ff57eac753be`.

| Task | Locked-test Macro-F1 | Robustness Macro-F1 |
|---|---:|---:|
| Sentiment | 0.960215 | 0.258476 |
| Theme | 0.953105 | 0.937389 |
| Improvement | 0.986110 | 0.792533 |

The comparison models did not satisfy the promotion policy. The system therefore retained the baseline models and used model disagreement only to prioritize human review.

## Reproduction sequence

```text
generate synthetic dataset
-> verify counts and hashes
-> audit leakage
-> fit candidate pipelines
-> select on validation
-> evaluate locked test
-> analyze errors
-> generate robustness set
-> evaluate promotion policy
-> verify runtime inference
```

## Interpretation boundary

These results characterize synthetic controlled evaluation only. They do not establish performance on real organizations, dialects, accessibility contexts, or field survey language. External, de-identified, human-labelled evaluation is required before making field-accuracy claims.
