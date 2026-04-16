# Drafting Constraints

Use this file to freeze recurrent drafting-behavior constraints that are likely to affect future writing rounds.

This file does not define scientific objects, core terminology, or section ownership.
It exists to stop the same writing failure from reappearing.

This file may use a `single-file / dual-layer` structure:
- `Part I` stores template-default constraints that remain active across projects unless they are explicitly deprecated or overridden.
- `Part II` stores project-specific or domain-specific constraints.
- `Starter Slots` store reserved placeholders for future project-specific additions.

If a project-specific constraint conflicts with a template-default constraint, prefer the project-specific constraint.

Keep `BASE-...` entries unless you intentionally change the template default.
Keep this file focused on active constraints.
For project-specific examples, see `shared/references/drafting_constraints_examples.md`.

## Constraint Entry Interface

Core fields:
- `constraint_id`
- `category`
- `rule`
- `default_action`

Recommended fields:
- `preferred_examples`
- `avoid_examples`
- `exception`
- `check_rule`

Optional fields:
- `scope`
- `notes`

Allowed `status` values:
- `proposed`
- `confirmed`
- `deprecated`
- `reserved`

## Part I. Template Default Constraints

### BASE-DC-01 -- verb precision
- `constraint_id`: BASE-DC-01
- `category`: lexical_precision
- `status`: confirmed
- `rule`: Prefer verbs that are easy to understand and semantically exact. Do not replace a precise common verb with a more ornate but less accurate alternative.
- `default_action`: Replace inflated or prestige-sounding verbs with the simplest verb that preserves the intended meaning.
- `preferred_examples`:
  - `use` over `utilize` when no technical distinction is intended
  - `show` over `demonstrate` when the stronger verb is not evidentially justified
- `avoid_examples`:
  - `leverage`, `facilitate`, `underscore`, or similar prestige verbs when a simpler verb is more exact
- `exception`: Keep the stronger verb only when it adds real semantic content that the simpler verb would lose.
- `check_rule`: If a simpler verb keeps the meaning intact, prefer the simpler verb.
- `scope`: full document
- `notes`: Apply in both Chinese and English. Prefer clarity and semantic precision over rhetorical elevation.

### BASE-DC-02 -- modifier minimization
- `constraint_id`: BASE-DC-02
- `category`: modifier_control
- `status`: confirmed
- `rule`: Do not use adjectives or adverbs unless they add necessary meaning, limitation, degree, or contrast.
- `default_action`: Delete decorative modifiers and keep only modifiers that narrow the claim or prevent ambiguity.
- `preferred_examples`:
  - `The method improves recall.`
  - `The result is consistent across three runs.`
- `avoid_examples`:
  - `The method delivers a remarkably strong improvement.`
  - `The result is very clearly consistent across three carefully designed runs.`
- `exception`: Keep the modifier when removing it would change the proposition, the scope, or the level of certainty.
- `check_rule`: If removing the modifier does not change the actual claim, remove it.
- `scope`: full document
- `notes`: This rule targets decorative emphasis, not legitimate technical qualification.

### BASE-DC-03 -- one sentence, one job
- `constraint_id`: BASE-DC-03
- `category`: sentence_granularity
- `status`: confirmed
- `rule`: Each sentence should carry one primary job. Prefer short, precise, easy-to-follow sentences over long literary ones.
- `default_action`: Split overloaded sentences by logical function and keep the main subject-verb relation easy to recover on first read.
- `preferred_examples`:
  - `We test the model on three benchmarks. The proposed method performs best on two of them.`
  - `The score becomes more stable after temporal smoothing. This reduces alert flicker near the threshold.`
- `avoid_examples`:
  - `one sentence that introduces the setup, reports the result, explains the mechanism, and states the impact`
- `exception`: Dense method definitions and tightly constrained equation-following sentences may remain longer if clarity is preserved.
- `check_rule`: If one sentence is simultaneously defining, explaining, qualifying, and concluding, split it.
- `scope`: full document
- `notes`: Apply in both Chinese and English. Prefer readable short sentences to ornamental long sentences.

### BASE-DC-04 -- research-first narration
- `constraint_id`: BASE-DC-04
- `category`: narration_perspective
- `status`: confirmed
- `rule`: The manuscript body should use the perspective of the research work, not the perspective of document organization or writing management, as the main narrative frame.
- `default_action`: Rewrite meta-writing sentences into direct statements about the experiment, the analysis, or the result.
- `preferred_examples`:
  - `We first measure the single-mode resource.`
  - `We then test the synchronized two-mode readout.`
  - `These measurements show that the platform can program the initial resource.`
- `avoid_examples`:
  - `This section focuses on how the paper presents the result.`
  - `The purpose of this subsection is to explain the writing logic.`
  - `The relation between this section and the later sections is as follows.`
- `exception`: Short roadmap sentences in the Introduction or other explicit overview passages may retain a document-organization perspective when that function is structurally required.
- `check_rule`: If the sentence is mainly about how the paper is written or arranged, rather than about the research itself, rewrite it.
- `scope`: main manuscript body
- `notes`: This rule is adapted from thesis-oriented guidance, but the active form here is paper-oriented.

### BASE-DC-05 -- direct positive statement
- `constraint_id`: BASE-DC-05
- `category`: sentence_pattern
- `status`: confirmed
- `rule`: Avoid contrastive negation templates such as `not ... but ...` when the negative half adds rhetoric but not necessary logic.
- `default_action`: Delete the negative scaffold and state the intended point directly.
- `preferred_examples`:
  - `The key result is the 20,000-mode cluster-state output.`
  - `More specifically, the synchronized readout supports the later parallel measurement.`
  - `Here we focus on the cluster-state output.`
- `avoid_examples`:
  - `The main result is not the single-mode case but the cluster-state case.`
  - `This does not mean X, but rather Y.`
  - `Rather than focusing on A, we focus on B.`
- `exception`: Keep the negative half only when it is needed to rule out a concrete misunderstanding, mark a scope boundary, or distinguish a competing mechanism.
- `check_rule`: If removing the negative half leaves the meaning intact, rewrite the sentence as a direct positive statement.
- `scope`: full document
- `notes`: This rule targets a rhetorical pattern, not one specific phrase.

## Part II. Active Project Constraints

## Starter Slots

Use these reserved entries for project-specific constraints or project-level overrides in `Part II`.

### DC-001
- `constraint_id`: DC-001
- `category`:
- `status`: reserved
- `rule`:
- `default_action`:
- `preferred_examples`:
- `avoid_examples`:
- `exception`:
- `check_rule`:
- `scope`:
- `notes`:

### DC-002
- `constraint_id`: DC-002
- `category`:
- `status`: reserved
- `rule`:
- `default_action`:
- `preferred_examples`:
- `avoid_examples`:
- `exception`:
- `check_rule`:
- `scope`:
- `notes`:
