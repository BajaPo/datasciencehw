# Workstream 001 — README section documenting DataScienceEcosystem.ipynb

## Task

Append a new section to `README.md` that documents what `DataScienceEcosystem.ipynb` covers, grounded in the notebook's actual content.

## Context

All items below are `Observed` unless marked otherwise.

**Repository state (Observed)**
- Repo root `/home/user/datasciencehw` contains: `DataScienceEcosystem.ipynb`, `README.md`, `PROJECT.md`, `MEMORY.md`, `.claude/`, `.workstream/`.
- Current branch: `workstream/001-readme-notebook-section`, created off `origin/main`.
- `README.md` is 3 lines (2 content lines + trailing newline), in full:
  ```
  # datasciencehw
  Homework from Jupyter Notebooks
  ```
- `PROJECT.md` is the unfilled template — every field reads `TBD`. There is no project-specific style guide, README convention, or documentation standard to follow. Ordinary good Markdown practice applies.
- `MEMORY.md` is the unfilled template — "None established." throughout. No prior decisions constrain this task.
- There is no test framework, no `tests/` directory, no CI config, no linter config, and no `package.json`/`pyproject.toml`/`requirements.txt` anywhere in the repo. `.claude/` contains only agent definitions and the root-protocol skill.

**Notebook state (Observed)**
`DataScienceEcosystem.ipynb` is nbformat 4.4, 11 cells, kernelspec display name `Python (Pyodide)`, `language_info.version` `3.8`. Cell-by-cell inventory:

| # | Type | Content |
|---|---|---|
| 0 | markdown | `# Data Science Tools and Ecosystem` |
| 1 | markdown | "In this notebook, Data Science Tools and Ecosystem are summarized." |
| 2 | markdown | `**Objectives:**` followed by bullets: List popular languages for Data Science; Commonly used libraries; Data Science Tools; Evaluating Expressions |
| 3 | markdown | "Some of the popular languages that Data Scientists use are:" — numbered list: Python, R, SQL, C++ |
| 4 | markdown | "Some of the commonly used libraries used by Data Scientists include:" — numbered list: `NumbPy`, `PyTorch`, `Pandas`, `SciKit` (spellings verbatim from the notebook; see Open questions) |
| 5 | markdown | A single-column Markdown table titled `Data Science Tools` with rows: RStudio, Apache Spark, TensorFlow |
| 6 | markdown | `### Below are a few examples of evaluating arithmetic expressions in Python` |
| 7 | code | `# This a simple arithmetic expression to mutiply then add integers` / `(3*4)+5` — stored output `17` |
| 8 | code | `# This will convert 200 minutes to hours by diving by 60` / `minutes = 200` / `hours = minutes/60` / `print(hours)` — stored output `3.3333333333333335` |
| 9 | markdown | `## Author` / `Baja Poawui` |
| 10 | code | empty, no outputs |

- The notebook imports nothing and runs nothing beyond plain Python arithmetic. The libraries and tools it names (NumPy, PyTorch, pandas, scikit-learn, RStudio, Apache Spark, TensorFlow) appear only as list/table text — they are **not** dependencies of the notebook.
- `Inferred`: this is a standard IBM/Coursera "Data Science Tools and Ecosystem" course exercise notebook. Do not state this in the README — it is not observable from the file itself and is not needed.

## Affected files

| Path | Action |
|---|---|
| `/home/user/datasciencehw/README.md` | `MODIFY` — append one new section at end of file |

No `CREATE`. No `DELETE`. No other file may be modified.

## Test locations

This repo has no test framework and no test directory, and the change is prose-only Markdown with no executable behavior. **No automated tests are to be added for this workstream.** The Coder must not introduce a test framework, a `tests/` directory, or any dependency manifest.

Verification for the Tester stage is manual and consists of:
1. `git diff` on `README.md` shows only additions, all after the existing line 2 — the first two lines are byte-identical to before.
2. `git status --short` shows `README.md` as the only modified path (plus the untracked/added `.workstream/001-readme-notebook-section/` contents).
3. Every factual claim in the new section maps to a specific notebook cell in the inventory table above.
4. The Markdown renders correctly (headings resolve, list is a list, no broken table syntax).

## Interface

Not applicable — this change adds Markdown prose only. No functions, classes, signatures, or types are introduced or altered.

## Behavior

Exact placement and shape of the edit:

1. Leave `README.md` lines 1–2 (`# datasciencehw` and `Homework from Jupyter Notebooks`) **exactly as they are**. Do not reword, retitle, or reformat them.
2. Append to the end of the file, separated from the existing description by one blank line:
   - An `##`-level heading reading exactly: `## DataScienceEcosystem.ipynb`
   - One or two sentences of intro prose stating that the notebook is a summary of the data science tools and ecosystem, and that it is a Python notebook whose code cells only demonstrate simple arithmetic.
   - An `###`-level subheading `### Objectives` (or an inline "The notebook's stated objectives are:" lead-in — Coder's choice, but be consistent) followed by a bullet list reproducing the four objectives from cell 2: listing popular Data Science languages, commonly used libraries, Data Science tools, and evaluating expressions.
   - An `###`-level subheading `### Contents` followed by a bullet list covering, at minimum:
     - **Popular languages** — Python, R, SQL, C++
     - **Commonly used libraries** — NumPy, PyTorch, pandas, scikit-learn
     - **Data Science tools** — RStudio, Apache Spark, TensorFlow
     - **Arithmetic examples** — two Python code cells: one multiplying and adding integers (`(3*4)+5`), one converting 200 minutes to hours
     - **Author** — an author cell naming Baja Poawui
3. Preserve a trailing newline at end of file.

Format expectations:
- Section heading is `##`; any sub-headings inside it are `###`. Do not introduce a second `#`-level heading — `# datasciencehw` remains the only H1.
- Mix of short prose and bullet lists as described above. Do not write a wall of prose, and do not reduce the whole section to a single flat bullet list with no context sentence.
- Use backticks for the filename `DataScienceEcosystem.ipynb` in body prose (the heading itself may be plain).
- Standard library/tool casing in README prose: `NumPy`, `PyTorch`, `pandas`, `scikit-learn`, `RStudio`, `Apache Spark`, `TensorFlow`, `Python`, `R`, `SQL`, `C++`.
- Plain Markdown only. No HTML, no badges, no images, no emoji, no tables required (a table for the tools list is acceptable if the Coder prefers, but bullets are the default).
- Target length: roughly 15–30 lines of Markdown. This is a small notebook; a long README section would misrepresent it.

## Edge cases

Enumerated for the Tester — each should be checked:

1. **Existing content untouched.** Lines 1–2 of `README.md` must be byte-identical after the change. A diff showing modification to either line is a failure.
2. **Blank-line separation.** Exactly one blank line between the existing description and the new `##` heading. No missing separator (which would fold the heading into the paragraph in some renderers) and no double blank lines.
3. **Trailing newline.** The file ends with exactly one newline character; no trailing blank lines beyond that.
4. **Heading hierarchy.** Exactly one `#` heading in the file (the pre-existing `# datasciencehw`). New section is `##`; sub-headings are `###`. No skipped or duplicated levels.
5. **Library-name spelling.** README uses corrected, conventional spellings (`NumPy`, `scikit-learn`) — see Open questions item 1. The notebook's own `NumbPy` / `SciKit` spellings must **not** be copied into the README, and must **not** be fixed in the notebook.
6. **No invented content.** The README must not claim the notebook does anything it does not: no data loading, no plotting, no model training, no dataset, no exercises beyond the two arithmetic cells. Every claim traces to a cell in the inventory table.
7. **No dependency claims.** The README must not present NumPy/PyTorch/pandas/scikit-learn/TensorFlow/Spark as requirements, prerequisites, or an install list. They are content the notebook *names*, not software it *uses*.
8. **No run instructions unless accurate.** Do not add "how to run" / setup / `pip install` instructions. The notebook's kernelspec is `Python (Pyodide)` and no environment file exists; any setup instructions would be invented.
9. **Empty final cell.** Cell 10 is empty. Do not document it as content, and do not describe the notebook as incomplete on account of it.
10. **Author attribution.** Naming Baja Poawui as the notebook's author is in scope (it is a cell in the notebook). Do not add contact details, email, links, or a licence statement — none exist in the repo.
11. **Stored outputs.** The notebook has stored outputs (`17`, `3.3333333333333335`). Quoting them in the README is optional; if quoted they must match exactly. Do not recompute or "clean up" `3.3333333333333335`.
12. **Only one file changed.** `git status` must not show changes to `DataScienceEcosystem.ipynb`, `PROJECT.md`, `MEMORY.md`, or anything under `.claude/`. Opening the notebook in a tool that rewrites JSON on save is a common accidental failure here — inspect the notebook diff explicitly.
13. **Markdown validity.** No unclosed code fences, no broken list indentation, renders cleanly on GitHub.

## Out of scope

The Coder must not:

- Modify `DataScienceEcosystem.ipynb` in any way — not the typos (`NumbPy`, `SciKit`, `mutiply`, `diving`, "This a simple"), not the empty trailing cell, not the outputs, not the metadata. The notebook is homework and is treated as immutable in this workstream.
- Restructure, retitle, reword, or reformat the existing two lines of `README.md`.
- Add any other README section: no Installation, Usage, Requirements, Setup, Licence, Contributing, Table of Contents, badges, or repo-description rewrite.
- Fill in `PROJECT.md` or `MEMORY.md`.
- Add, remove, or edit anything under `.claude/`.
- Create dependency manifests (`requirements.txt`, `environment.yml`, `pyproject.toml`), CI config, `.gitignore`, or a test framework.
- Rename or move any file.
- Commit to, merge into, or push to `main`. Work stays on `workstream/001-readme-notebook-section`.
- Run `jupyter`, execute the notebook, or clear its outputs.

## Open questions

1. **Notebook library-name typos (non-blocking; resolved by this spec).** The notebook lists `NumbPy` and `SciKit`. This spec directs the README to use the conventional spellings `NumPy` and `scikit-learn`, on the basis that the README documents the notebook's *subject matter* and reproducing a typo into new documentation would be a defect. The notebook itself stays untouched. If the user would rather the README quote the notebook verbatim, that is a one-word change the Coder can make on request — it does not block implementation.
2. **Whether to quote code-cell outputs (non-blocking).** Left to the Coder's discretion per Edge case 11; either choice satisfies the spec.

**Nothing in this section blocks implementation.** The notebook's content is short, fully readable, and unambiguous; the spec can be handed to the Coder as-is.
