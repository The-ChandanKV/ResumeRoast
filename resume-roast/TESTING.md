# Testing

Tests ran on Windows with Codex CLI `0.171.0-alpha.13`. Inputs were fictional. [prompts.md](prompts.md) records the prompts, and the files in [reports/](reports/) are the final responses saved by the CLI.

## Package validation and fresh discovery

- The skill-creator `quick_validate.py` validator passed using the bundled Python runtime and a temporary PyYAML installation.
- A newly launched Codex app server returned one enabled `resume-roast` entry with repo scope from `skills/list`. It resolved the project junction to this package’s `SKILL.md`.
- The three role checks each started a new `codex exec --ephemeral` session. The JSONL events showed reads of the review guidelines, rubric, and report template. The baseline session ran before installation and did not read those files.

## Three role evaluations

The category order is technical skills, experience and projects, keywords, structure, and quantifiable achievements.

| Role | Scores | Overall | Evidence checked |
| --- | --- | --- | --- |
| [Software Engineer Fresher](reports/software-engineer-with-skill.md) | 22 + 21 + 14 + 12 + 4 | **73/100** | CI is required and unevidenced. The queue simulator supports partial evidence of explaining data structures. Docker and cloud deployment are preferred. The output preserves five tests and the two-person team and avoids overstating API ownership. |
| [Data Analyst Intern](reports/data-analyst-with-skill.md) | 25 + 21 + 13 + 12 + 5 | **76/100** | Missing-value checks and a recommended action for a nontechnical audience are unverified. Basic A/B testing is preferred. The output preserves 12,000 rows before cleaning, 84 responses, and the walkthrough to three classmates. |
| [AI/ML Engineer Intern](reports/ai-engineer-with-skill.md) | 17 + 21 + 13 + 12 + 4 | **67/100** | A held-out test set is documented. Complete split documentation and error analysis are unverified. Preferred deployment, Docker, and experiment tracking are unevidenced. The output preserves the 0.78 and 0.62 macro F1 values and the majority-class baseline. |

Each report had eleven ordered sections, five justified scores, four grounded rewrite records, five ranked actions, and separate conclusions for resume quality and eligibility. The displayed technical and keyword coverage formulas and category totals were checked against the rubric. Proposed work on missing qualifications remained conditional.

## Input handling

| Input | Observed outcome |
| --- | --- |
| [Missing resume path](reports/missing-file.md) | Identified the missing resume and asked for its correct path or text. The response withheld the report and score. |
| [Directory supplied as the resume](reports/invalid-file.md) | Identified the invalid path and asked for a file or pasted text. The response withheld the report and score. |
| [Text-based PDF and pasted job description](reports/pdf-smoke.md) | A temporary PDF made from the software engineering fixture was read using a local Python runtime with `pypdf`. Codex produced the structured review from the PDF and verbatim pasted posting. |
| [Plain-text resume and Markdown job description](reports/plain-text-smoke.md) | Codex reviewed a temporary `.txt` version of the data analyst resume against the original posting and produced the structured report. |

The PDF smoke run scored 73/100. The plain-text smoke run scored 68/100, compared with 76/100 for the Markdown data analyst run. The plain-text run grouped SQL joins and aggregations together and scored missing-value checks separately. It also used different keyword and project relevance judgments. Both runs applied their stated weights correctly. These runs verify input handling and show that classification and scoring can vary across reviews.

The first directory check incorrectly selected a sample file. The first role checks also exposed score explanations that did not consistently account for partial coverage. The skill now rejects directory paths explicitly and requires reproducible coverage math. The role and input-error results above come from fresh reruns after those changes.

## Reproduce

Install the package as described in the [README](README.md). From the workspace root, run each request in a new session. For example:

```powershell
$question = '$resume-roast Review the resume in resume-roast/examples/software-engineer-resume.md against the job description in resume-roast/examples/software-engineer-jd.md and suggest improvements.'
$question | codex exec --ephemeral --skip-git-repo-check --output-last-message review.md -
```

The retained runs used `--ignore-user-config` and the workspace’s existing unrestricted execution profile because the local Windows CLI blocked even `Get-Content` under its restricted profiles. To rerun the baseline, use a clean checkout before installing the project junction and remove the skill mention from the prompt. Use the same inputs and host settings for both runs. See [COMPARISON.md](COMPARISON.md) for the observed differences.

## Remaining verification

Claude Code was unavailable on this machine. To verify its native `/resume-roast` command, follow the Claude Code installation in the [README](README.md), launch a fresh session, and run the listed slash example. The PDF test covered a readable text layer. Scanned PDFs and complex page layouts still need representative fixtures to verify OCR and reading order.
