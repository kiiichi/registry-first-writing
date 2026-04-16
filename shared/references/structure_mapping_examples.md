# Structure Mapping Examples

These examples illustrate entry shape and granularity for `shared/structure_mapping.md`.
Do not treat them as active project truth.

### EX-S1 -- Introduction
- `section_id`: EX-S1
- `section_name`: Introduction
- `intended_function`: define the problem, practical motivation, gap, and contribution framing
- `what_belongs_here`: domain background; problem statement; why early detection matters; summary of contributions; document roadmap
- `what_should_not_be_overloaded_here`: full implementation detail; exhaustive literature review; extended result interpretation
- `relation_to_major_claims`: supports EX-C1, EX-C2
- `evidence_detail_placement_notes`: keep evidence high-level here; defer metric-heavy proof to Results
- `status`: confirmed
- `notes`: The Introduction may preview the main claim, but should not carry the whole proof burden.

### EX-S2 -- Data and Task Definition
- `section_id`: EX-S2
- `section_name`: Data and Task Definition
- `intended_function`: define the dataset, labels, task formulation, and evaluation target
- `what_belongs_here`: sensor streams; sampling scheme; fault labels; split policy; event definition; metric definition
- `what_should_not_be_overloaded_here`: architecture details; ablation discussion; production deployment claims
- `relation_to_major_claims`: supports EX-C1, EX-C3
- `evidence_detail_placement_notes`: place setup-critical facts here so later sections can cite them instead of redefining them
- `status`: confirmed
- `notes`: This section owns task semantics and metric semantics.

### EX-S3 -- Method
- `section_id`: EX-S3
- `section_name`: Method
- `intended_function`: explain the model, scoring logic, and training objective
- `what_belongs_here`: model inputs; encoder design; fusion logic; anomaly score definition; loss terms; thresholding policy if fixed during training
- `what_should_not_be_overloaded_here`: dataset statistics; full benchmark comparison; discussion of deployment tradeoffs unless tightly tied to design choices
- `relation_to_major_claims`: supports EX-C2
- `evidence_detail_placement_notes`: keep the local logic chain complete enough that later result discussion does not need to reconstruct the method
- `status`: confirmed
- `notes`: If equations are needed, they belong here unless they define shared task metrics already owned by EX-S2.

### EX-S4 -- Experimental Setup
- `section_id`: EX-S4
- `section_name`: Experimental Setup
- `intended_function`: describe training protocol, baselines, implementation settings, and evaluation procedure
- `what_belongs_here`: baseline definitions; hyperparameter ranges; hardware notes; threshold selection; evaluation protocol
- `what_should_not_be_overloaded_here`: method re-explanation; high-level motivation already covered in Introduction
- `relation_to_major_claims`: supports EX-C2, EX-C3
- `evidence_detail_placement_notes`: all comparison conditions that affect fairness should be explicit here
- `status`: confirmed
- `notes`: This section should make result tables interpretable without narrative guessing.

### EX-S5 -- Results
- `section_id`: EX-S5
- `section_name`: Results
- `intended_function`: present empirical outcomes, then move to constrained interpretation
- `what_belongs_here`: main metrics; baseline comparisons; ablations; latency-quality tradeoffs; error patterns directly supported by the data
- `what_should_not_be_overloaded_here`: unsupported mechanism speculation; deployment promises; broad future-work claims
- `relation_to_major_claims`: supports EX-C2, EX-C3
- `evidence_detail_placement_notes`: keep observation and interpretation distinct; let tables and figures carry the proof
- `status`: confirmed
- `notes`: The first sentence of a result paragraph should usually identify the observation before explaining it.

### EX-S6 -- Discussion
- `section_id`: EX-S6
- `section_name`: Discussion
- `intended_function`: explain implications, limits, failure modes, and transfer conditions
- `what_belongs_here`: why the method may help; limits of retrospective evaluation; robustness caveats; deployment preconditions
- `what_should_not_be_overloaded_here`: new core results not shown earlier; repeated metric dumps; exaggerated field-readiness claims
- `relation_to_major_claims`: supports EX-C3, EX-C4
- `evidence_detail_placement_notes`: keep the evidence boundary visible; mark hypotheses as hypotheses
- `status`: confirmed
- `notes`: This section is where safe restraint matters most.

### EX-S7 -- Conclusion
- `section_id`: EX-S7
- `section_name`: Conclusion
- `intended_function`: compress the established contribution and the most important limit
- `what_belongs_here`: contribution recap; concise result summary; bounded outlook
- `what_should_not_be_overloaded_here`: fresh literature review; detailed ablation commentary; ungrounded deployment language
- `relation_to_major_claims`: supports EX-C1, EX-C2, EX-C3, EX-C4
- `evidence_detail_placement_notes`: summary wording should remain within the evidence boundaries already frozen in the claim register
- `status`: confirmed
- `notes`: Conclusion should echo the claim register, not improvise a stronger story.
