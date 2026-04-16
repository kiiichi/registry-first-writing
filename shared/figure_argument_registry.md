# Figure Argument Registry

## Scope

This registry controls figure placement, figure argumentative role, regrouping, placeholder policy, and source traceability.

It does not store equation planning or mathematical logic. Those belong in `shared/equation_argument_registry.md`.

This registry may use a `single-file / dual-layer` structure:
- `Part I` stores template-default figure policies.
- `Part II` stores the active project figure registry.

This registry is a current-truth registry, not a patch log.
Keep only active project truth and a small number of reserved starter slots here.
For format examples, see `shared/references/figure_argument_registry_examples.md`.

---

## Entry Guide

### Project overview block

Recommended fields:
- `status`
- `source_basis`
- `document_function`
- `current_policy`
- `notes`

### Figure entry fields

Recommended fields:
- `status`
- `source_file`
- `source_label`
- `source_subfigure`
- `placeholder`
- `recommended_argument_role`
- `recommended_section`
- `recommended_position`
- `supports`
- `drafting_rule`
- `notes`

### Figure group entry fields

Recommended fields:
- `status`
- `title_function`
- `components`
- `recommended_section`
- `notes`

Allowed `status` values:
- `proposed`
- `confirmed`
- `deprecated`
- `reserved`

---

# Part I. Template Default Policies

## BASE-FIG-POL-1
- `status`: `confirmed`
- `topic`: `figure_placeholder_policy`
- `rule`: During drafting, figures should be inserted as `placeholder + source trace + argument role + caption note`, not as final layout markup.
- `why`: Early drafting should preserve argumentative position and traceability before final layout is frozen.
- `format_rule`:
  1. `[FIG_...]`
  2. `Source: <file>, <label/subfigure>`
  3. `Argument role: <what this figure supports>`
  4. `Caption note: <source caption or source-derived note>`

## BASE-FIG-POL-2
- `status`: `confirmed`
- `topic`: `source_traceability_policy`
- `rule`: Every registered figure must record its source as `which file + which label + which subfigure`, not just local numbering.
- `why`: Traceability is required for revision-heavy writing and later regrouping.

## BASE-FIG-POL-3
- `status`: `confirmed`
- `topic`: `regrouping_policy`
- `rule`: Figures may be regrouped for document logic; original paper or slide ordering does not need to remain the final chapter or section ordering.
- `why`: Source-material layout and final document logic are often different.

## BASE-FIG-POL-4
- `status`: `confirmed`
- `topic`: `figure_text_anchoring_policy`
- `rule`: Inserted figures should not remain standalone placeholders without textual anchoring. The surrounding prose should integrate each figure into the local argument rather than treating it as an isolated figure-comment block.
- `why`: A figure only helps if the prose clearly tells the reader why it matters.
- `priority_rules`:
  1. state the object-level claim in prose first
  2. cite the figure close to the supporting sentence
  3. keep figure analysis within registered support boundaries
  4. if figure meaning is uncertain, mark the uncertainty instead of guessing

---

# Part II. Active Project Figure Registry

## FIG-OVERVIEW
- `status`: `reserved`
- `source_basis`:
- `document_function`:
- `current_policy`:
- `notes`:

### Figure Entries

#### FIG-001
- `status`: `reserved`
- `source_file`:
- `source_label`:
- `source_subfigure`:
- `placeholder`:
- `recommended_argument_role`:
- `recommended_section`:
- `recommended_position`:
- `supports`:
- `drafting_rule`:
- `notes`:

#### FIG-002
- `status`: `reserved`
- `source_file`:
- `source_label`:
- `source_subfigure`:
- `placeholder`:
- `recommended_argument_role`:
- `recommended_section`:
- `recommended_position`:
- `supports`:
- `drafting_rule`:
- `notes`:

### Figure Groups

#### GROUP-001
- `status`: `reserved`
- `title_function`:
- `components`:
- `recommended_section`:
- `notes`:
