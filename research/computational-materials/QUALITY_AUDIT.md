# Computational Materials Science Handbook — Content Quality Audit

> **Scope:** 23 canonical English lessons, the main course index, module navigation, repository-local SVG illustrations, and historical forwarding pages.  
> **Audit type:** Source-level and editorial review of content, navigation, mathematics markup, and pedagogy. **Not** a browser-based visual rendering test or a numerical verification of every scientific equation.

## Executive assessment

The handbook covers a strong range of foundational concepts and major computational methods. Its main limitations are **uneven pedagogical depth, repeated definitions, a partly diagram-light visual style, and inconsistent case-study specificity**. The organization is usable after correcting the top-level reading sequence, but it requires a dedicated editing pass before being described as a fully polished textbook.

| Area | Status | Evidence / outstanding concerns |
| --- | --- | --- |
| Curriculum coverage | Substantial | 23 core lessons covering foundations, electronic structure, methods, materials, transport, and MLIPs |
| Prerequisite reading order | Corrected | Main README formerly placed quantum mechanics last and thermodynamics after MD; reordered by dependencies |
| File structure | Usable, with historical clutter | Older category directories remain as forwarding notes to preserve existing links |
| Internal relative links | Corrected in scoped source review | Canonical Markdown pages checked against current repository paths; the Surface → PBC legacy link was repaired |
| Math syntax | Generally consistent | Standalone formulas mostly use fenced `math` blocks; presence/balancing is **not** proof of successful GitHub visual rendering or mathematical correctness |
| Visual explanation | Mixed | Many useful energy profiles and process figures, but some original SVGs use three text cards with arrows rather than depicting geometry or quantities |
| Research generality | Inconsistent | Some modules still contain named-material examples despite the desired material-agnostic editorial standard |
| Uncertainty and limitations | Good emerging coverage | Statistical dependence, OOD behavior, convergence, and NEB-versus-transport limitations are discussed; depth varies by chapter |

## Confirmed fixes made during this audit

1. **Reordered the README's recommended 23-lesson reading list** to introduce mathematical concepts and quantum mechanics before Born–Oppenheimer and DFT, and thermodynamics/statistical mechanics before later statistical applications. Permanent filenames remain unchanged.
2. **Fixed the broken Surface → Periodic Boundary Conditions link** caused by an earlier filename renumbering.

## Editorial Pass A — Partial Completion

The first editorial pass has now been applied to five priority chapters:

- PES: normalized the article title and moved the metastability/landscape discussion ahead of the review section.
- NEB: moved misplaced convergence subsections under practical challenges, reorganized alternate-path material, and generalized the principal case-study heading.
- DFT: placed extended numerical/theoretical discussion before review questions.
- PBC: grouped the advanced periodic and reciprocal-space explanations before exercises.
- MD: moved sampling and integration discussions ahead of pitfalls and review questions.

**Source validation:** The five changed articles have balanced Markdown code fences, and local Markdown links and figure paths were verified against the repository tree; no missing target path was found among these five.

**Important limitation:** This is a structural and editorial pass, **not** full resolution of duplicated physics derivations, scientific line-by-line verification, or live GitHub rendering. Some headings and repeated definitions still need a second pass.

## Priority 1 — Editorial and factual review

### 1. Resolve duplicated introductions and repeated explanatory blocks

Some lessons contain multiple generations of added sections with headings such as *Extended Foundations*, *Additional Foundation*, or *Advanced Practice*. Integrate these into the relevant main sections, and remove duplicate explanations while preserving unique scientific caveats.

**Highest priority:** NEB (long and partly repetitive), PES, PBC, bulk structures, DFT, and MD.

### 2. Make every equation auditable

For each displayed equation:
- Define every symbol and its units where relevant.
- State the ensemble, dimensionality, boundary conditions, and limiting assumptions.
- Show key intermediate steps for the most important derivations.
- Distinguish strict relations from approximations, heuristic estimates, and definitions.
- Verify factors and sign conventions independently (e.g., diffusion dimensionality, stress, reciprocal vectors, defect chemistry, free-energy references, HTST prefactors).
- Include a small worked numerical or symbolic example when it materially aids learning.

An editor should not infer scientific validity merely from LaTeX syntax.

### 3. Remove unexplained material-specific cases

Use simple, general examples (a double well, a cubic crystal, an ion in a generic lattice, a generic binary solid) unless a particular material is essential to illustrate a non-universal phenomenon. Named-material sections remain in several foundations/methods chapters and should be generalized as part of a later wording pass.

## Priority 2 — Improve figure pedagogy

Keep all illustrations in `assets/figures/`, but distinguish **true scientific diagrams** from decorative workflows. Prioritize replacing simple three-card flow illustrations with quantitative or geometrical examples:

| Topic | Stronger figure requirement |
| --- | --- |
| Quantum mechanics | Correctly shaped wavefunction and $|\psi|^2$ curves in a common coordinate frame |
| Linear algebra / gradients | Actual contour gradient vectors and eigenvector transformation |
| Fourier / reciprocal space | Direct lattice and reciprocal lattice with properly labeled vectors and Brillouin zone |
| Crystallography | Accurate 3D Miller plane projections and symmetry operations |
| Thermodynamics | Free-energy versus temperature examples with assumptions identified |
| Statistical mechanics | Boltzmann probability curves at more than one temperature |
| Numerical optimization | Annotated steepest-descent and quasi-Newton paths on the same contour surface |
| MLIPs | Actual local graph, error-stratified parity panels, and OOD scenario comparisons |

Each diagram should have an informative caption, unambiguous axes/units where necessary, accessible contrast, and a *schematic* label if not data-derived.

## Priority 3 — Improve learning experience

1. Add a consistent **Prerequisites → Intuition → Derivation → Worked Example → Computational Practice → Common Pitfalls → Review** hierarchy to each major lesson.
2. Use **one authoritative location for each definition** and link back from later modules instead of re-explaining it in full.
3. Ensure article titles match the scope: foundations versus methodology versus application.
4. Retain subject-folder filenames independent of the global reading order; only the README should establish cross-folder progression.
5. Add specific reference citations for important equations and methods, preferring textbooks, foundational publications, and authoritative code documentation.

## Follow-up validation plan

- [x] Inventory canonical chapters and legacy forwarding directories.
- [x] Correct obvious dependency-order issues in the README.
- [x] Check relative Markdown links across canonical chapter files and module indexes; repair confirmed stale path.
- [x] Inspect Markdown code-fence balance in canonical chapters.
- [ ] Inspect rendered mathematics and images through the GitHub webpage for **every chapter**.
- [ ] Independently verify all advanced mathematical formulas and scientific approximations.
- [ ] Replace oversimplified SVG concept cards with geometry- or data-oriented diagrams.
- [ ] Consolidate repeated sections across long chapters.
- [ ] Replace remaining named-material examples with general teaching examples.
- [ ] Add worked examples and references uniformly.

## Recommended execution order

**Pass A:** Consolidate NEB, PES, DFT, PBC and MD; check equation definitions and terminology.  
**Pass B:** Rebuild higher-value diagrams for reciprocal space, symmetry, quantum mechanics, statistical mechanics and optimization.  
**Pass C:** Generalize examples, add worked exercises, references, and a final GitHub-render review.

The audit is deliberately conservative: it distinguishes issues confirmed from the Markdown source from problems that require mathematical or browser-based review.
