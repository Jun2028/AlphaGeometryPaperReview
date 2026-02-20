# Report

## Task
Create `AlphaGeometry.md` based on the paper in `docs/s41586-023-06747-5.pdf` for a PhD-level AI group meeting audience, including appendix-referenced details and visuals/tables where helpful.

## Changes Made

1. Created full content in `AlphaGeometry.md` from scratch.
2. Covered required sections:
   - Succinct overview/background.
   - Euclidean geometry environment description.
   - Detailed synthetic data generation pipeline.
   - Directed acyclic graph (DAG) and traceback role.
   - DD + AR integration and traceback for both.
   - Model structure/training with `(P, N, G(N))`.
   - What the model learns and core challenge.
   - Results/findings/contributions.
   - Limitations.
   - Direct answers to the three specific user questions.
3. Included diagrams/tables from extracted PDF assets where useful.
4. Added one explicit placeholder for the fragmented main-paper Fig. 3 composite extraction.

## Assets Prepared and Referenced

Created `docs/assets/` and copied selected extracted images for stable references:

- `docs/assets/fig1_simple_problem.png`
- `docs/assets/fig1_with_aux_point.png`
- `docs/assets/fig1_imo2015_solution.png`
- `docs/assets/fig5_generalized_theorem.jpg`
- `docs/assets/ext_fig1_parallelism.jpg`
- `docs/assets/ext_fig6_ablations.png`
- `docs/assets/ext_table1_construction_actions.jpg`
- `docs/assets/ext_table2_ar_examples.png`
- `docs/assets/ext_table3_aux_other_domains.png`
- `docs/assets/ext_table4_geometry_vs_inequality.png`

## Notes

- PDF text extraction was done locally using `pypdf`.
- Image extraction required installing `pypdf` and `pillow`.
- Main paper Table 1 was reconstructed as a markdown table for readability.
## Follow-up Update

Date: 2026-02-19

Requested adjustments were applied to `AlphaGeometry.md`:

1. Added main-paper Fig. 3 directly into the synthetic-data section using a cropped render from the PDF:
   - `docs/assets/fig3_synthetic_data_generation.png`
2. Replaced the earlier Fig. 3 placeholder with the actual embedded figure.
3. Resized oversized simple diagrams by switching to fixed-width HTML image tags:
   - `docs/assets/fig1_simple_problem.png` set to width 280
   - `docs/assets/fig1_with_aux_point.png` set to width 280
   - `docs/assets/fig1_imo2015_solution.png` set to width 480

Auxiliary artifact created for extraction support:

- `docs/page_renders/page_03.png` (rendered PDF page used to crop Fig. 3)
## Follow-up Update

Date: 2026-02-19 (second follow-up)

Adjusted image sizing in `AlphaGeometry.md` to prevent full-width rendering and improve readability:

1. Converted all remaining Markdown image embeds (`![](...)`) to fixed-width HTML `<img>` tags.
2. Specifically reduced the section 6.2 illustration size:
   - `docs/assets/fig5_generalized_theorem.jpg` now width `420`.
3. Standardized larger appendix visuals/tables to width `760` to avoid page-filling behavior while preserving legibility.

This change addresses the issue of simple illustrations occupying the full page width.
## Follow-up Update

Date: 2026-02-19 (third follow-up)

Updated `AlphaGeometry.md` section **Q3** to include explicit compute and cost comparison against AlphaProof/TTRL:

1. Added a compact compute table for AlphaGeometry vs AlphaProof.
2. Included your provided AlphaProof numbers: 100,000 TPU-days (training) + 80,000 TPU-days (TTRL) = 180,000 TPU-days.
3. Added direct money conclusion: AlphaProof+TTRL is more expensive in practice.
4. Kept the conceptual explanation that this is about domain setup/symbolic leverage, not Euclidean geometry being "easy".
## Follow-up Update

Date: 2026-02-19 (fourth follow-up)

Corrected `AlphaGeometry.md` section **Q3** to restore prior rationale content that was removed in the previous edit.

1. Reinstated the 4 rationale points (DD+AR leverage, narrower domain structure, not because geometry is easy, and why TTRL-style compute fits broader formal search).
2. Kept the newly added compute table and money comparison.
3. Added a short note clarifying the rationale comparison is an inference from system design and reported behavior.
## Follow-up Update

Date: 2026-02-19 (fifth follow-up)

Refined `AlphaGeometry.md` section **Q1** to remove vague wording and add mechanism-level detail from the paper.

1. Replaced the prior short generic statement with explicit verification mechanics:
   - Specialized geometry language/environment.
   - Logical + numerical step checks.
   - DD as Horn-clause deductive closure.
   - AR as linear-equation reasoning via Gaussian elimination.
   - DD/AR alternating to fixed point + traceback extraction.
2. Added explicit comparison against Lean-style kernels:
   - no small foundational trusted kernel,
   - no independent kernel re-check of proof terms,
   - narrow Euclidean domain scope.
## Follow-up Update

Date: 2026-02-19 (sixth follow-up)

Updated `AlphaGeometry.md` to make the paper reference a clickable hyperlink to the Nature page:

- https://www.nature.com/articles/s41586-023-06747-5
## Follow-up Update

Date: 2026-02-19 (seventh follow-up)

Updated the **Limitations** section in `AlphaGeometry.md` to clarify what "geometric inequalities/combinatorial geometry are outside scope" means.

1. Added a concrete geometric-inequality example:
   - triangle inequality-style target: `a^2(b+c-a)+b^2(c+a-b)+c^2(a+b-c) <= 3abc`.
2. Added a concrete combinatorial-geometry example:
   - circle packing / maximizing non-overlapping circles in a region.
3. For each example, added explicit reasons AlphaGeometry cannot currently address it:
   - DD+AR is mainly geometric-rule + equality deduction, not full inequality-tool reasoning.
   - current framework is not a discrete counting/optimization engine over combinatorial configurations.
4. Kept the rest of the limitations list and renumbered for consistency.
## Follow-up Update

Date: 2026-02-19 (eighth follow-up)

Fixed context for the hard-problem diagram near Section 2 in `AlphaGeometry.md`.

1. Replaced the vague line "Example of a much harder solved problem state" with an explicit "how to read this figure" block.
2. Clarified that the figure is an **auxiliary-construction stage** for IMO 2015 P3, not the original problem diagram.
3. Explicitly stated where auxiliary constructions appear in the shown zoom (`D` and `E`), and noted the paper reports three auxiliary points in the full solution.
4. Replaced the previous image with a more informative annotated zoom:
   - `docs/assets/fig1_imo2015_aux_zoom.jpg`
## Follow-up Update

Date: 2026-02-19 (ninth follow-up)

Improved the Fig. 3 section in `AlphaGeometry.md` based on feedback.

1. Re-cropped `docs/assets/fig3_synthetic_data_generation.png` to remove lower-page body paragraphs/margins and keep only the relevant figure region.
2. Reduced display width from 760 to 620 so it no longer dominates page layout.
3. Added explicit context under "Main-paper Fig. 3":
   - panel a = premise sampling,
   - panel b = DAG-style symbolic closure,
   - traceback from target node (example `HA ⟂ BC`) to minimal dependency subgraph,
   - panel c = extraction of `(P, N, G(N))`,
   - where auxiliary constructions (e.g., `E`, `D`) come from.

This addresses both context and readability concerns for what is arguably the core figure.
## Follow-up Update

Date: 2026-02-19 (tenth follow-up)

Expanded Section **3.5 Step E: prune proof graphs to minimal forms** in `AlphaGeometry.md`.

1. Replaced the single condensed sentence with an explicit step-by-step pruning workflow.
2. Defined what "reachability" means operationally: whether DD+AR can still deduce the target conclusion after removing auxiliary subsets.
3. Clarified the paper's "exhaustive trial-and-error" behavior over auxiliary-point subsets.
4. Added why pruning matters (remove vacuous constructions, improve training signal, also used after successful test-time proofs).
## Follow-up Update

Date: 2026-02-19 (eleventh follow-up)

Adjusted wording in the hard-problem figure context (Section 2) in `AlphaGeometry.md`.

1. Replaced "create extra constraints" with paper-aligned phrasing.
2. New wording now states that auxiliary constructions provide **new inputs** and let DD+AR **expand deduction closure**.
3. This avoids the incorrect implication that the setting becomes stricter in a restrictive sense.
## Follow-up Update

Date: 2026-02-19 (twelfth follow-up)

Clarified the "Cross-domain framing" block in `AlphaGeometry.md` (Section 6.3).

1. Replaced the contextless one-line lead with explicit purpose statements for Extended Data Tables 3 and 4.
2. Explained why those tables are included: conceptual support for the reusable "auxiliary construction + symbolic closure" pattern, not new benchmark performance claims.
3. Added guidance that this part is secondary for readers focused only on IMO-AG-30 numbers.
4. Fixed formatting artifacts from the initial edit.
## Follow-up Update

Date: 2026-02-19 (thirteenth follow-up)

Expanded Section **3.4 Step D: DD + AR integration** in `AlphaGeometry.md` to make it self-contained.

1. Clarified DD vs AR roles in plain language.
2. Added explicit explanation of Horn-clause rules (`Q <- P1,...,Pk`) and what that means operationally.
3. Added concrete definition of "geometry equality" with paper-aligned examples:
   - angle equality mapping,
   - ratio equality mapping.
4. Expanded the DD<->AR alternation loop step-by-step (how facts/equalities flow between engines).
5. Kept traceback explanation but made it clearer which part is DD-side vs AR-side.
## Follow-up Update

Date: 2026-02-19 (fourteenth follow-up)

Clarified the term "target object set" in `AlphaGeometry.md` (Fig. 3 explanation and Step C sentence).

1. Added inline bracket definition:
   - object set = objects explicitly present/mentioned in the theorem goal (conclusion `N`).
2. Updated both nearby sentences to avoid undefined jargon.
## Follow-up Update

Date: 2026-02-19 (fifteenth follow-up)

Updated first occurrence of "geometric rule closure" in `AlphaGeometry.md` with an inline bracket definition:

- "(repeatedly apply geometry rules until no new fact can be deduced)"

This was added exactly at first appearance, as requested.
## Follow-up Update

Date: 2026-02-19 (sixteenth follow-up)

Expanded Section 4 in `AlphaGeometry.md` to explicitly define `(P, N, G(N))` next to the serialization line.

1. Added concrete definitions:
   - `N` = target conclusion node,
   - `P` = minimal needed premises after traceback,
   - `G(N)` = dependency proof subgraph for `N` from `P`.
2. Added an explicit mapping from serialized sequence fields to symbols:
   - `<premises>` = `P`, `<conclusion>` = `N`, `<proof>` = `G(N)`.

This addresses the missing self-contained explanation.
## Follow-up Update

Date: 2026-02-19 (seventeenth follow-up)

Expanded the "infinite branching" explanation in `AlphaGeometry.md` (Section 3.3).

1. Added a short toy-intuition block that explains why auxiliary construction introduces infinite branching.
2. Clarified that there are many construction families for a new point and infinitely many placements within some families.
3. Added the practical resolution: LM proposes likely constructions; DD+AR verifies and expands closure.
4. Per instruction, re-read the full `AlphaGeometry.md` after edit.
## Follow-up Update

Date: 2026-02-19 (eighteenth follow-up)

Added an inline bracket explanation for the DD rule template in `AlphaGeometry.md`:

- `Q(x) <- P1(x), ..., Pk(x)` now includes a plain-language readout of what it means operationally.
## Follow-up Update

Date: 2026-02-19 (nineteenth follow-up)

Reworked the Section 2 figure block in `AlphaGeometry.md` per feedback.

1. Removed the previous "before/after" and separate hard-example images that lacked clear context.
2. Replaced with a single Fig. 1(a-d) focus block centered on model loop understanding, especially panels `b/c`.
3. Added panel-by-panel explanation of the symbolic-engine <-> LM construction loop and how `d` shows mixed proof steps.
4. Added new figure asset:
   - `docs/assets/fig1_toprow_abcd.png`
5. Per instruction, re-read the full `AlphaGeometry.md` after edit.
## Follow-up Update

Date: 2026-02-19 (twentieth follow-up)

Updated Section **3.1 Step A** in `AlphaGeometry.md`.

1. Added the paper's scale detail: nearly **1 billion** sampled random premises.
2. Replaced the vague label "Reference:" with explicit context.
3. Clarified that the included table (`Extended Data Table 1`) shows example construction actions used to generate those premises.
4. Per instruction, re-read the full `AlphaGeometry.md` after edit.
## Follow-up Update

Date: 2026-02-19 (twenty-first follow-up)

Moved Fig. 1(a-d) model-loop block in `AlphaGeometry.md` to improve section alignment.

1. Removed the Fig. 1 loop diagram/explanation from Section 2 (environment section).
2. Inserted the same Fig. 1 block at the top of Section 4 (model structure/training section), where it belongs conceptually.
3. Kept the existing panel-by-panel context (a/b/c/d), with focus on model loop behavior.
4. Per instruction, re-read the full `AlphaGeometry.md` after edit.
## Follow-up Update

Date: 2026-02-19 (twenty-second follow-up)

Updated Q3 compute comparison in `AlphaGeometry.md` to include a rough AlphaGeometry transformer-training estimate.

1. Added back-of-envelope estimate: **~100-500 TPUv3 chip-days** (peak-equivalent) for AG transformer training.
2. Added equivalent wall-clock on one 4x4 TPUv3 slice: **~6-31 days** (peak-equivalent).
3. Added explicit order-of-magnitude comparison vs AlphaProof+TTRL (`180,000 TPU-days`), noting AG LM training is still hundreds of times lower.
4. Kept caveat that this is rough and depends on utilization/hardware-generation details.
5. Per instruction, re-read the full `AlphaGeometry.md` after edit.
## Follow-up Update

Date: 2026-02-19 (twenty-third follow-up)

Refined traceback explanation in `AlphaGeometry.md` for general AI audience.

1. Replaced the terse two-line traceback block with explicit **what / why / how** framing.
2. Kept technical mechanism at one-line level only:
   - DD side via minimal dependency chains in graph/hypergraph structures.
   - AR side via minimal parent-equation subset (MILP in the paper).
3. Emphasized why it matters for ML: cleaner training signal and pruning feasibility.
4. Per instruction, re-read the full `AlphaGeometry.md` after edit.
## Follow-up Update

Date: 2026-02-19 (twenty-fourth follow-up)

Moved the Fig. 1(a-d) model-loop block in `AlphaGeometry.md` to match narrative flow.

1. Relocated the Fig. 1(a-d) explanation and image from Section 4 to the intro (Section 1), right after the main headline result.
2. Removed the duplicate block from Section 4.
3. This places model-loop context earlier for readers before deeper technical sections.
4. Per instruction, re-read the full `AlphaGeometry.md` after edit.
## Follow-up Update

Date: 2026-02-19 (twenty-fifth follow-up)

Rewrote the Section 6.3 appendix-table block in `AlphaGeometry.md`.

1. Replaced informal/conversational tone with presentation-style phrasing.
2. Explicitly labeled table roles:
   - Extended Data Table 3 = cross-domain auxiliary-construction pattern.
   - Extended Data Table 4 = geometry-inequality template mapping.
3. Added explicit figure labels before each embedded table image:
   - "Table 3: auxiliary constructions across domains"
   - "Table 4: geometry vs inequality under the same framework"
4. Kept the core takeaway: reusable "auxiliary construction + symbolic closure" pattern.
5. Per instruction, re-read the full `AlphaGeometry.md` after edit.
## Follow-up Update

Date: 2026-02-19 (twenty-sixth follow-up)

Fixed Table 3/Table 4 visual alignment block in `AlphaGeometry.md`.

1. Replaced plain text labels with consistent bold labels:
   - `Table 3. ...`
   - `Table 4. ...`
2. Wrapped each image in its own paragraph block for stable separation.
3. Standardized both table image widths to `700` for consistent alignment.
4. Per instruction, re-read the full `AlphaGeometry.md` after edit.
