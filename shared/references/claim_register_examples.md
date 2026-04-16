# Claim Register Examples

These examples illustrate entry shape and granularity for `shared/claim_register.md`.
Do not treat them as active project truth.

### EX-C1 -- project scope
- `claim_id`: EX-C1
- `status`: confirmed
- `claim_text`: This document studies real-time multisensor fault detection for industrial pumps, focusing on early warning from vibration, temperature, and pressure streams rather than on full root-cause diagnosis.
- `scope_notes`: document-level framing claim
- `quantitative_anchors`: event-level F1; alert latency under 200 ms; early-warning lead time
- `evidence_basis`: confirmed project charter and benchmark definition
- `target_locations`: Title, Abstract, Introduction, Conclusion
- `forbidden_drift`: Do not reframe the project as full predictive maintenance automation. Do not claim causal diagnosis or repair recommendation.
- `notes`: This entry defines what the project is actually about.

### EX-C2 -- core contribution wording
- `claim_id`: EX-C2
- `status`: confirmed
- `claim_text`: The main contribution is a multisensor temporal encoder and alerting pipeline that improves early fault detection quality while preserving low inference latency.
- `scope_notes`: contribution wording control
- `quantitative_anchors`: compare against single-sensor and late-fusion baselines
- `evidence_basis`: benchmark results table and ablation study
- `target_locations`: Abstract, Introduction, Results, Conclusion
- `forbidden_drift`: Do not describe the method as universally optimal, domain-agnostic, or deployment-proven without supporting evidence.
- `notes`: Use this entry to stabilize contribution wording across sections.

### EX-C3 -- evidence boundary
- `claim_id`: EX-C3
- `status`: confirmed
- `claim_text`: The present evidence supports retrospective benchmark improvement on the available dataset, but does not by itself establish long-term field reliability in live industrial deployment.
- `scope_notes`: evidence-boundary control
- `quantitative_anchors`: retrospective evaluation only
- `evidence_basis`: experimental setup and data-collection scope
- `target_locations`: Results, Discussion, Conclusion
- `forbidden_drift`: Do not convert offline benchmark success into operational reliability claims.
- `notes`: This entry prevents common overclaiming during summary writing.

### EX-C4 -- acceptable deployment wording
- `claim_id`: EX-C4
- `status`: confirmed
- `claim_text`: Deployment-facing wording may describe the system as deployment-oriented or deployment-compatible, but not as production-validated unless such validation is explicitly documented.
- `scope_notes`: wording-band control
- `quantitative_anchors`: none
- `evidence_basis`: current project maturity
- `target_locations`: Abstract, Discussion, Executive Summary, Conclusion
- `forbidden_drift`: Avoid production-ready, field-proven, fully robust, and similar maturity inflation.
- `notes`: Useful for marketing-pressure scenarios.
