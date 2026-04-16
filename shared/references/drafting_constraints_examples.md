# Drafting Constraints Examples

These examples illustrate project-specific constraint shape and granularity for `shared/drafting_constraints.md`.
Do not treat them as active project truth.

### EX-DC1 -- no claim inflation
- `constraint_id`: EX-DC1
- `category`: claim_strength
- `status`: confirmed
- `rule`: Do not upgrade benchmark improvement into broad real-world superiority unless the evidence explicitly supports that stronger claim.
- `default_action`: Rewrite broad superiority language into evidence-bounded wording tied to the actual evaluation setup.
- `preferred_examples`:
  - `improves event-level F1 on the evaluated benchmark`
  - `shows stronger early-warning performance under the present retrospective protocol`
- `avoid_examples`:
  - `outperforms existing systems in real deployments`
  - `solves industrial fault detection`
- `exception`: Stronger wording is allowed only if the evidence basis and claim register explicitly freeze it.
- `check_rule`: If the sentence says more than the benchmark actually proves, weaken it.
- `scope`: summaries; abstracts; conclusions
- `notes`: This is one of the highest-value default constraints in technical writing.

### EX-DC2 -- term stability
- `constraint_id`: EX-DC2
- `category`: terminology
- `status`: confirmed
- `rule`: Once a core term is frozen in `shared/term_registry.md`, do not rotate to near-synonyms for stylistic variety.
- `default_action`: Replace near-synonyms with the registered preferred term.
- `preferred_examples`:
  - `multisensor temporal encoder`
  - `anomaly score`
  - `event-level F1`
- `avoid_examples`:
  - `fusion backbone` for `multisensor temporal encoder`
  - `risk score` for `anomaly score`
  - `overall F1` when `event-level F1` is intended
- `exception`: A local synonym may appear only when the term registry explicitly allows it or when quoting a source verbatim.
- `check_rule`: If the wording change adds no new meaning and only changes surface form, revert to the registered term.
- `scope`: full document
- `notes`: This prevents the document from sounding inconsistent even when the facts are correct.

### EX-DC3 -- one paragraph, one primary job
- `constraint_id`: EX-DC3
- `category`: local_logic
- `status`: confirmed
- `rule`: Each paragraph should have one primary function. Do not merge setup, result, interpretation, limitation, and contribution framing into one block unless the section function explicitly requires compression.
- `default_action`: Split overloaded paragraphs by logical job and make the local sequence explicit.
- `preferred_examples`:
  - `Paragraph 1: setup`
  - `Paragraph 2: observation`
  - `Paragraph 3: interpretation or limitation`
- `avoid_examples`:
  - `one paragraph that introduces the experiment, reports the result, explains the mechanism, and states the impact`
- `exception`: Executive summaries and abstracts may compress more aggressively, but should still preserve clear sentence-level separation.
- `check_rule`: If deleting one sentence would change the paragraph's main function, the paragraph probably has more than one job.
- `scope`: body prose
- `notes`: This rule dramatically improves reviewability.

### EX-DC4 -- separate observation from interpretation
- `constraint_id`: EX-DC4
- `category`: evidence_boundary
- `status`: confirmed
- `rule`: Present the observed result before offering explanation or implication. Do not present interpretation as if it were the observation itself.
- `default_action`: Move the raw observation into the first sentence and place explanation after it.
- `preferred_examples`:
  - `The proposed model improves event-level F1 by 4.2 points over the best baseline. This suggests that cross-sensor timing information is useful under the present benchmark.`
- `avoid_examples`:
  - `Because the model captures cross-sensor timing information, it clearly delivers better early warning.`
- `exception`: In tightly compressed summary sentences, observation and interpretation may remain adjacent if the evidence boundary stays explicit.
- `check_rule`: Ask whether the sentence would still be true if the explanation were wrong. If yes, separate them.
- `scope`: Results; Abstract; Conclusion
- `notes`: This is especially important when the author knows the project too well and writes one step ahead of the evidence.

### EX-DC5 -- figure anchoring
- `constraint_id`: EX-DC5
- `category`: figure_text_integration
- `status`: confirmed
- `rule`: A figure inserted into the draft must be explicitly cited and integrated into the local argument. Do not drop a placeholder without surrounding prose.
- `default_action`: Add an object-level sentence, cite the figure near that sentence, and add at most 1-2 sentences of bounded explanation.
- `preferred_examples`:
  - `The end-to-end signal path is summarized in [FIG_SYSTEM_PIPELINE].`
  - `The latency-quality tradeoff remains favorable relative to the baselines, as shown in [FIG_LATENCY_QUALITY_TRADEOFF].`
- `avoid_examples`:
  - `standalone figure placeholder with no nearby explanation`
  - `figure commentary that explains workflow logic instead of research content`
- `exception`: Pure planning notes inside the registry itself may remain placeholder-only.
- `check_rule`: If the reader could delete the figure without changing the paragraph meaning, the figure is probably not anchored tightly enough.
- `scope`: sections with figures
- `notes`: Figure anchoring matters more than figure count.
