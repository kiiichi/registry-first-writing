# Equation Argument Registry

## Scope

This registry controls equation source mapping, equation block structure, formula role, mechanism notes, symbol-scope notes, placement intent, and section-specific equation planning.

This file uses a `single-file / dual-layer` structure:
- `Part I` stores template-default policies,
- `Part II` stores the active project equation registry,
- `Part III` stores the active `Equation Source Appendix`.

The appendix improves readability and formula-level traceability, but the primary control layer remains `Part II`.

This registry is a current-truth registry, not a patch log.
Keep only active project truth and a small number of reserved starter slots here.
For format examples, see `shared/references/equation_argument_registry_examples.md`.

---

## Entry Guide

### Project overview block

Recommended fields:
- `status`
- `source_basis`
- `document_function`
- `equation_strategy`
- `notes`

### Local policy fields

Recommended fields:
- `status`
- `topic`
- `rule`
- `why`

### Source map fields

Recommended fields:
- `status`
- `source_file`
- `source_equations`

### Equation block fields

Recommended fields:
- `status`
- `name`
- `function`
- `equation_order`

### Equation entry fields

Recommended fields:
- `status`
- `source_file`
- `source_label`
- `short_name`
- `formula_role`
- `mechanism`
- `symbol_notes`
- `placement_intent`
- `source_appendix_id`

### Appendix entry fields

Recommended fields:
- `status`
- `for_registry_id`
- `formula`

Allowed `status` values:
- `proposed`
- `confirmed`
- `deprecated`
- `reserved`

---

# Part I. Template Default Policies

## BASE-EQ-POL-1
- `status`: `confirmed`
- `topic`: `equation_figure_separation_policy`
- `rule`: Mathematical meaning, derivation structure, and symbol logic belong in the equation layer and text logic layer, not in figure entries.
- `why`: Figure registry controls placement and argument role; equation registry controls formal structure.

## BASE-EQ-POL-2
- `status`: `confirmed`
- `topic`: `equation_chain_completeness_policy`
- `rule`: Keep only the equations needed to close the local logic chain. If a bridge equation is required for understanding, include it. If a formula is merely background and already defined elsewhere, do not duplicate it.
- `why`: Good long-form writing keeps the local derivation readable without becoming a full textbook.

## BASE-EQ-POL-3
- `status`: `confirmed`
- `topic`: `appendix_reading_priority`
- `rule`: By default, read `Part I` and `Part II` first. Read `Part III` only when the task depends on exact formula content, symbol detail, derivation inspection, or source-level verification.
- `why`: Most drafting and review tasks depend on control information, not on full formula text.

## BASE-EQ-POL-4
- `status`: `confirmed`
- `topic`: `appendix_truth_policy`
- `rule`: `Equation Source Appendix` entries must follow `entry-as-truth`. If a formula changes, overwrite the existing appendix entry in place rather than creating patch-style child entries.
- `why`: Source visibility should not recreate patch-log sprawl.

---

# Part II. Active Project Equation Registry

## EQ-OVERVIEW
- `status`: `reserved`
- `source_basis`:
- `document_function`:
- `equation_strategy`:
- `notes`:

### Local Equation Policies

#### EQ-LOC-001
- `status`: `reserved`
- `topic`:
- `rule`:
- `why`:

### Source Maps

#### EQ-SRC-001
- `status`: `reserved`
- `source_file`:
- `source_equations`:

### Equation Blocks

#### EQ-BLOCK-001
- `status`: `reserved`
- `name`:
- `function`:
- `equation_order`:

### Equation Entries

#### EQ-001
- `status`: `reserved`
- `source_file`:
- `source_label`:
- `short_name`:
- `formula_role`:
- `mechanism`:
- `symbol_notes`:
- `placement_intent`:
- `source_appendix_id`: `EQ-001-SRC`

---

# Part III. Equation Source Appendix

## Usage rule

This appendix stores the current valid formula text for the equation objects defined in `Part II`.

Default reading order:
1. read `Part I` and `Part II` first,
2. enter `Part III` only when formula form, symbol details, derivation inspection, or source-level verification is needed.

Each appendix entry must remain aligned with its `for_registry_id`.

## EQ-001-SRC
- `status`: `reserved`
- `for_registry_id`: `EQ-001`
- `formula`:
