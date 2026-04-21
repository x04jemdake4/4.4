# Project Plan

This document outlines the plan for both maintaining this repository and for completing HW 4.3: Reproducible Data Analysis.

## Repository Maintenance Plan

### Branching Strategy
- `main` is the stable branch and holds only reviewed, merged work.
- All changes are developed on short-lived feature branches named after the task (e.g., `add-plan`, `update-readme`, `upload-hw-files`).
- Feature branches are merged back into `main` through pull requests, never by direct push.

### Commit Conventions
- Commit messages describe what changed and why in a single clear sentence (e.g., "Add project plan covering repo workflow and HW 4.3 deliverables").
- Commits reference related issues using GitHub's closing syntax (`closes #N`) so merged PRs auto-close the tracking issue.
- Commits are scoped to one logical change — no mixed bundles of unrelated edits.

### Issue Tracking
- Each unit of work is opened as a GitHub Issue before the branch for it is created.
- Issues carry a short description of the goal and the definition of done.
- Issues are closed via PR merge rather than manually, to preserve the link between task and implementation.

### Pull Request Workflow
1. Open an issue describing the change.
2. Create a feature branch from `main`.
3. Make commits on the branch.
4. Push the branch and open a pull request into `main`.
5. Review the diff, confirm the PR description references the issue, merge, and delete the branch.

## HW 4.3 Plan

HW 4.3 is a reproducible Quarto document that ports the HW 3.4 deliverables into a single rendered PDF and adds new sections on plan-based GenAI prompting and reflection. The finished work produces two artifacts that live in this repo: the `.qmd` source and the rendered `.pdf`.

### Section 1 — Busiest Airports
- Compile passenger counts for the top six airports worldwide for each year from 2020 through 2025.
- Build a tidy data frame in R and render it as a formatted table using `kableExtra`.
- Produce a line plot with `ggplot2` showing passenger traffic over time for every airport that appeared in any yearly top six, with narrative around the pandemic drop and the post-2020 recovery.

### Section 2 — Monte Carlo Integration
- Implement a reusable `mcSimulation()` function that samples random points inside a bounding rectangle.
- Apply it to the standard normal PDF over the interval [-4, 4] with y bounds [0, 0.4].
- Build a small multiple at n = 10, 100, 1,000, and 10,000 using `patchwork` to combine four individual `ggplot` objects.
- Discuss convergence toward the true integral value (~0.99994) and connect the pattern to the law of large numbers.

### Section 3 — Planning and Prompting GenAI Tools
- Work with `calcium.csv`, a non-tidy longitudinal dataset with duplicate column names encoding treatment group by column position.
- Write a six-step plan for reading the data, adding subject IDs, splitting and tagging the two groups, stacking, pivoting longer, and plotting trajectories with group means.
- Submit the plan to an LLM, capture the response, and compare it against a generic-prompt response to evaluate the effect of prompt specificity.

### Section 4 — Reflection
- Reflect on tidy data, the `ggplot2` grammar of graphics, Monte Carlo reasoning, and the Quarto workflow, with concrete examples tying course material to prior and current work.

### Rendering and Reproducibility
- The Quarto document sets `echo: false` globally and ends with a code appendix chunk using `ref.label = knitr::all_labels()` so the body reads cleanly while all code remains reproducible at the end.
- References are managed through a `.bib` file and rendered into a References section.
- Re-rendering the full document before submission verifies that every chunk runs end-to-end in a clean environment.

### Deliverables in This Repo
- `HW4-3.qmd` — Quarto source file.
- `HW4-3.pdf` — Rendered PDF submitted for HW 4.3.
- `README.md` — Repo overview and contents.
- `PLAN.md` — This document.