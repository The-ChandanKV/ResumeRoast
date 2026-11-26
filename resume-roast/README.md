# Resume Roast – Intelligent Resume Reviewer

Resume Roast is a reusable Agent Skills package that reviews a candidate’s resume against one job description. It accepts PDF, Markdown, and plain-text resumes and a job description supplied as a file or pasted text.

## Problem and objectives

Generic resume feedback can overlook a specific job requirement or suggest wording that overstates the candidate’s experience. Resume Roast maps the posting to the submitted evidence, scores how well the resume presents that evidence, and gives the candidate a prioritized revision plan. Its rewrites preserve the original facts and use labeled placeholders when a number needs verification.

## Features

- Required and preferred qualifications mapped to direct evidence, partial evidence, or gaps.
- Five evidence-based scores, with a justification for each category.
- An exact quote, diagnosis, revision, and explanation for every weak bullet.
- Supported keywords with placement suggestions, formatting fixes, and up to five ranked actions.
- Separate conclusions about resume quality and actual eligibility.
- Clarification and recovery instructions for missing, invalid, or unreadable inputs.

## Architecture

| Path | Purpose |
| --- | --- |
| [SKILL.md](SKILL.md) | Agent Skills manifest, input handling, review workflow, and invocation examples |
| [references/](references/) | Scoring rubric, evidence and rewrite rules, and the report template |
| [examples/](examples/) | Fictional software engineering, data analysis, and AI/ML resume and posting pairs |
| [reports/](reports/) | Captured test responses |
| [TESTING.md](TESTING.md) | Test commands, observed results, and remaining verification |
| [COMPARISON.md](COMPARISON.md) | Side-by-side analysis of actual with-skill and baseline runs |
| [prompts.md](prompts.md) | Chronological development and test prompts |

The host agent handles the analysis. Text reviews require no skill-specific dependencies. For PDF input, the host needs a PDF reader or a local extractor.

## Install in Codex

From the workspace root containing the `resume-roast/` folder, run in PowerShell:

```powershell
New-Item -ItemType Directory -Force .agents/skills | Out-Null
New-Item -ItemType Junction -Path .agents/skills/resume-roast -Target (Resolve-Path resume-roast).Path
```

This workspace already has that project-scoped junction. For another checkout, run the commands once. If junctions are unavailable, use `Copy-Item -Recurse resume-roast .agents/skills/resume-roast` with an absent destination. Refresh the copy after updating the source. On macOS or Linux, run `mkdir -p .agents/skills` and `ln -s ../../resume-roast .agents/skills/resume-roast`. For user-wide installation, copy the skill folder to `~/.agents/skills/resume-roast`.

Open a fresh Codex session from the workspace root. In the CLI, enter `/skills` and select `resume-roast`, or type the skill mention directly. Use `codex --skip-git-repo-check` if launching the CLI from this folder before it is initialized as a Git repository. See [Codex skill documentation](https://developers.openai.com/codex/skills).

```text
$resume-roast Review resume-roast/examples/software-engineer-resume.md against resume-roast/examples/software-engineer-jd.md.
```

For noninteractive mode, use single quotes in PowerShell so the shell preserves the dollar sign:

```powershell
codex exec --skip-git-repo-check '$resume-roast Compare resume-roast/examples/data-analyst-resume.md with resume-roast/examples/data-analyst-jd.md.'
```

## Use the slash invocation in Claude Code

From the workspace root, copy the same package to Claude Code’s project skill directory. Run once with an absent destination:

```powershell
New-Item -ItemType Directory -Force .claude/skills | Out-Null
Copy-Item -Recurse resume-roast .claude/skills/resume-roast
```

Start Claude Code in the workspace and use its native slash command. The installation follows the [Claude Code skill documentation](https://code.claude.com/docs/en/skills).

```text
/resume-roast Compare resume-roast/examples/ai-engineer-resume.md with resume-roast/examples/ai-engineer-jd.md.
```

## Review your own inputs

Supply paths, attach the documents where supported, or paste text with clear labels. For PDF reviews in a terminal, make `pdftotext` available on PATH or provide an available Python runtime with `pypdf` installed. Scanned PDFs need working OCR or a readable text export.

```text
$resume-roast Compare "./My Resume.pdf" with "./role.txt".
```

```text
$resume-roast Review the following.

Resume
[Paste resume here]

Job description
[Paste job description here]
```

The report appears in the session. To save it, add a request such as “Save the report to `./my-review.md`.”

## Evaluation methodology

| Category | Points |
| --- | ---: |
| Technical skills alignment | 30 |
| Experience and project relevance | 25 |
| Keyword alignment | 20 |
| Resume structure and readability | 15 |
| Quantifiable achievements | 10 |
| **Total** | **100** |

The [rubric](references/evaluation-rubric.md) defines coverage values, weighting, and rounding. The resulting number is a custom resume assessment score. Employer ATS scores and hiring decisions use their own criteria.

## Sample output

The Software Engineer Fresher review scored **73/100** and identified CI pipeline familiarity as the most material gap. One rewrite demonstrates how the skill uses evidence already present in the resume.

- **Original** — “Used a database.”
- **Problem** — Leaves out the database engine and the work Alex performed.
- **Improved** — Wrote SQL queries in PostgreSQL to filter lost-item listings by category and date.
- **Why it works** — Shows applied SQL and the specific filters Alex worked on.

Read the complete [Software Engineer Fresher report](reports/software-engineer-with-skill.md) for the eleven-section format and two-part final assessment.

## Testing and comparison

[Testing results](TESTING.md) cover fresh Codex sessions, output structure, calculations, evidence checks, and input errors. The [before-and-after comparison](COMPARISON.md) links both unedited Software Engineer Fresher outputs and evaluates them against the same resume and job description.

## Limitations and future improvements

Results depend on the completeness of the resume and posting, and model judgments may vary between runs. The report can evaluate documented eligibility conditions. Real-world eligibility and hiring outcomes remain decisions for the candidate and employer to verify. Text extraction can lose page-layout details, especially in image-only and multi-column PDFs.

Possible future work includes more role fixtures, a repeat-run consistency study, and scanned and multi-column PDF regression fixtures.
