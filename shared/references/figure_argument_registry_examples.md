# Figure Argument Registry Examples

These examples illustrate active figure-registry shape and grouping granularity for `shared/figure_argument_registry.md`.
Do not treat them as active project truth.

For default figure policies, see the active `shared/figure_argument_registry.md`.

## EX-DOC-OVERVIEW
- `status`: `confirmed`
- `source_basis`:
  - `figures/system_pipeline.svg`
  - `figures/sensor_layout.png`
  - `notebooks/results_overview.ipynb`
- `document_function`: `rewrite project materials into a controlled technical manuscript`
- `current_policy`: `reuse existing figures where possible; add new figures only when the current set cannot support the argument`

### Example Figure Entries

#### EX-FIG-1
- `status`: `confirmed`
- `source_file`: `figures/system_pipeline.svg`
- `source_label`: `Figure 1`
- `source_subfigure`: `whole`
- `placeholder`: `[FIG_SYSTEM_PIPELINE]`
- `recommended_argument_role`: `concept anchor`
- `recommended_section`: `Method / System Overview`
- `recommended_position`: `after the task definition and before architecture details`
- `supports`: `how sensor streams, encoder, anomaly score, and alert generation connect in one pipeline`
- `drafting_rule`: `insert as placeholder + source caption, not final layout markup`

#### EX-FIG-2
- `status`: `confirmed`
- `source_file`: `figures/sensor_layout.png`
- `source_label`: `Figure 2`
- `source_subfigure`: `whole`
- `placeholder`: `[FIG_SENSOR_LAYOUT]`
- `recommended_argument_role`: `measurement context`
- `recommended_section`: `Data and Task Definition`
- `recommended_position`: `near the data-collection description`
- `supports`: `which sensors are used and how their signals map to the monitored equipment`
- `drafting_rule`: `insert as placeholder + source caption, not final layout markup`

#### EX-FIG-3
- `status`: `confirmed`
- `source_file`: `notebooks/results_overview.ipynb`
- `source_label`: `results_tradeoff_curve`
- `source_subfigure`: `whole`
- `placeholder`: `[FIG_LATENCY_QUALITY_TRADEOFF]`
- `recommended_argument_role`: `main empirical evidence`
- `recommended_section`: `Results`
- `recommended_position`: `after the first benchmark table and before error analysis`
- `supports`: `how the proposed system trades off event-level F1 against alert latency relative to baselines`
- `drafting_rule`: `insert as placeholder + source caption, not final layout markup`

### Example Regrouping

#### EX-GROUP-1
- `status`: `confirmed`
- `title_function`: `problem setup and system overview`
- `components`:
  - `EX-FIG-1`
  - `EX-FIG-2`
- `recommended_section`: `Introduction to Method transition`

#### EX-GROUP-2
- `status`: `confirmed`
- `title_function`: `main quality-latency result block`
- `components`:
  - `EX-FIG-3`
- `recommended_section`: `Results`
