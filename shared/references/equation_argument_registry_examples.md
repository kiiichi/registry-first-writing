# Equation Argument Registry Examples

These examples illustrate active equation-registry shape and appendix granularity for `shared/equation_argument_registry.md`.
Do not treat them as active project truth.

For default equation policies, see the active `shared/equation_argument_registry.md`.

## EX-DOC-OVERVIEW
- `status`: `confirmed`
- `source_basis`:
  - `notes/method_sketch.md`
  - `experiments/metrics.md`
  - `slides/model_review_2026_01.pdf`
- `document_function`: `rewrite model notes and experiments into a controlled technical manuscript`
- `equation_strategy`: `preserve only the equations needed to define the task, the model output, and the training objective`

### Local Equation Policies

#### EX-EQ-LOC-1
- `status`: `confirmed`
- `topic`: `notation_stability`
- `rule`: Use one symbol system consistently for input window, hidden representation, anomaly score, and objective. Do not rename the same object across sections.
- `why`: Symbol drift is one of the fastest ways to make technical writing feel unreliable.

#### EX-EQ-LOC-2
- `status`: `confirmed`
- `topic`: `metric_vs_model_boundary`
- `rule`: Keep task-definition equations with the task and metric setup, and keep model-internal equations with the Method section.
- `why`: This prevents the method section from swallowing the entire document logic.

### Source Maps

#### EX-EQ-SRC-1
- `status`: `confirmed`
- `source_file`: `notes/method_sketch.md`
- `source_equations`:
  - `window_definition`
  - `encoder_output`
  - `anomaly_score`

#### EX-EQ-SRC-2
- `status`: `confirmed`
- `source_file`: `experiments/metrics.md`
- `source_equations`:
  - `training_objective`

### Equation Blocks

#### EX-EQ-BLOCK-1
- `status`: `confirmed`
- `name`: `task_and_representation_subsection`
- `function`: `define the input window and the learned fused representation`
- `equation_order`:
  - `EX-EQ-01`
  - `EX-EQ-02`

#### EX-EQ-BLOCK-2
- `status`: `confirmed`
- `name`: `scoring_and_training_subsection`
- `function`: `define the anomaly score and the final training objective`
- `equation_order`:
  - `EX-EQ-03`
  - `EX-EQ-04`

### Equation Entries

#### EX-EQ-01
- `status`: `confirmed`
- `source_file`: `notes/method_sketch.md`
- `source_label`: `window_definition`
- `short_name`: `input_window_definition`
- `formula_role`: `define the local time window used for model input`
- `mechanism`: `Collect the recent multichannel observations into one ordered input block.`
- `symbol_notes`: `Use x_t for the observation at time t, w for window length, and X_t for the stacked window.`
- `placement_intent`: `opening equation of the task_and_representation_subsection`
- `source_appendix_id`: `EX-EQ-01-SRC`

#### EX-EQ-02
- `status`: `confirmed`
- `source_file`: `notes/method_sketch.md`
- `source_label`: `encoder_output`
- `short_name`: `fused_representation`
- `formula_role`: `define the hidden representation produced by the encoder`
- `mechanism`: `Map the multisensor input window into a fused latent state used by downstream scoring.`
- `symbol_notes`: `Use h_t for the latent state and f_theta for the learned encoder.`
- `placement_intent`: `after EX-EQ-01`
- `source_appendix_id`: `EX-EQ-02-SRC`

#### EX-EQ-03
- `status`: `confirmed`
- `source_file`: `notes/method_sketch.md`
- `source_label`: `anomaly_score`
- `short_name`: `anomaly_score_definition`
- `formula_role`: `define the scalar score used for alert generation`
- `mechanism`: `Project the hidden representation into a bounded anomaly score.`
- `symbol_notes`: `Use s_t for the score and keep the threshold definition in prose unless the threshold is fixed by the model design.`
- `placement_intent`: `opening equation of the scoring_and_training_subsection`
- `source_appendix_id`: `EX-EQ-03-SRC`

#### EX-EQ-04
- `status`: `confirmed`
- `source_file`: `experiments/metrics.md`
- `source_label`: `training_objective`
- `short_name`: `training_objective`
- `formula_role`: `state the optimization target used during training`
- `mechanism`: `Combine classification quality with temporal smoothness so the score is useful for both accuracy and stable early warning.`
- `symbol_notes`: `Use L_cls for classification loss, L_smooth for temporal smoothness, and lambda for the balancing weight.`
- `placement_intent`: `after EX-EQ-03`
- `source_appendix_id`: `EX-EQ-04-SRC`

## Example Source Appendix

### EX-EQ-01-SRC
- `status`: `confirmed`
- `for_registry_id`: `EX-EQ-01`
- `formula`:
$$
X_t = [x_{t-w+1}, x_{t-w+2}, \ldots, x_t]
$$

### EX-EQ-02-SRC
- `status`: `confirmed`
- `for_registry_id`: `EX-EQ-02`
- `formula`:
$$
h_t = f_{\theta}(X_t)
$$

### EX-EQ-03-SRC
- `status`: `confirmed`
- `for_registry_id`: `EX-EQ-03`
- `formula`:
$$
s_t = \sigma(w_s^{\mathsf T} h_t + b_s)
$$

### EX-EQ-04-SRC
- `status`: `confirmed`
- `for_registry_id`: `EX-EQ-04`
- `formula`:
$$
L = L_{\mathrm{cls}} + \lambda L_{\mathrm{smooth}}
$$
