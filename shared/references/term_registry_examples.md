# Term Registry Examples

These examples illustrate entry shape and granularity for `shared/term_registry.md`.
Do not treat them as active project truth.

### EX-T1 -- core system term
- `term_id`: EX-T1
- `concept`: full project object
- `preferred_term`: multisensor fault detection pipeline
- `abbreviation`: none
- `discouraged_variants`: monitoring framework; maintenance engine; diagnostic platform
- `definition_notes`: Use this term when referring to the end-to-end system that ingests multiple sensor streams and produces fault alerts.
- `first_definition_target_location`: Introduction
- `status`: confirmed
- `notes`: Keep this broader than the model alone.

### EX-T2 -- model term
- `term_id`: EX-T2
- `concept`: main model component
- `preferred_term`: multisensor temporal encoder
- `abbreviation`: MTE
- `discouraged_variants`: fusion backbone; temporal extractor; multimodal encoder
- `definition_notes`: Use this term for the learned representation module that fuses vibration, temperature, and pressure inputs over time.
- `first_definition_target_location`: Method
- `status`: confirmed
- `notes`: If you define `MTE`, keep the long form nearby at first use.

### EX-T3 -- output score term
- `term_id`: EX-T3
- `concept`: scalar model output
- `preferred_term`: anomaly score
- `abbreviation`: none
- `discouraged_variants`: risk value; health score; alarm score
- `definition_notes`: Use this term for the model output before thresholding and alert generation.
- `first_definition_target_location`: Method
- `status`: confirmed
- `notes`: Keep score terminology separate from binary alert terminology.

### EX-T4 -- timing metric term
- `term_id`: EX-T4
- `concept`: early warning metric
- `preferred_term`: early-warning lead time
- `abbreviation`: none
- `discouraged_variants`: warning horizon; prediction window; anticipation time
- `definition_notes`: Use this term for how much time remains between the first valid alert and the labeled fault event.
- `first_definition_target_location`: Experimental Setup or Metrics subsection
- `status`: confirmed
- `notes`: Define measurement rules once and reuse the same wording everywhere.

### EX-T5 -- evaluation metric term
- `term_id`: EX-T5
- `concept`: primary detection metric
- `preferred_term`: event-level F1
- `abbreviation`: none
- `discouraged_variants`: F1 score; detection F1; overall F1
- `definition_notes`: Use this term when the metric is computed at the event level rather than per timestamp.
- `first_definition_target_location`: Metrics subsection
- `status`: confirmed
- `notes`: Prevent drift between event-level and frame-level evaluation wording.
