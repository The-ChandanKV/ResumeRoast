# With and without Resume Roast

## Method

Two fresh Codex CLI sessions reviewed the same [fictional resume](examples/software-engineer-resume.md) and [job description](examples/software-engineer-jd.md). The normal prompt ran before project installation. The second prompt added the explicit `$resume-roast` mention after installation. The review request and input files were otherwise identical. The reports are verbatim final messages from `codex exec --output-last-message`. Review the original [baseline response](reports/software-engineer-without-skill.md) and [skill response](reports/software-engineer-with-skill.md).

The baseline response contains machine-specific source links emitted by Codex. Use the fixture links above from another checkout.

## Observed differences

| Criterion | Normal prompt | Resume Roast |
| --- | --- | --- |
| Output structure | An opening assessment and two named sections for suggested bullets and other edits. | Eleven numbered sections, including separate findings for role fit, scoring, gaps, rewrites, and final eligibility. |
| Feedback quality | Identified CI as the primary requirement gap and proposed a workflow that runs the existing pytest tests. | Retained the CI suggestion, identified the separate partial match on explaining data structures, and connected buried evidence to how a recruiter scans the resume. |
| Specificity | Offered five project bullets, including a restatement of the existing strong pytest bullet. | Quoted all four weak bullets and gave a diagnosis, rewrite, and explanation for each. Called out the pytest bullet as worth keeping. |
| Consistency | Used useful free-form advice. The response did not expose repeatable scoring rules. | Used the five rubric categories and showed calculations totaling 73/100. The same headings and weights appeared in the other two fixture reports. Numeric repeatability across repeated identical runs was outside this comparison. |
| Keyword identification | Suggested a skills list and explicitly called for SQL. Recognized CI, Docker, and cloud deployment gaps. | Scored ten named posting terms, gave placement guidance for supported terms, and marked CI, Docker, and cloud deployment as conditional additions. |
| Actionable recommendations | Four numbered edits, including removing the objective and bringing project details into the main bullets. | Five ranked actions, plus concrete placement for SQL, REST APIs, and code review and a next step for strengthening the queue example. |
| Accuracy | Core technologies, examples, and counts were grounded in the resume. “Built a Flask REST API in a two-person team” puts more weight on individual ownership than the source’s “Worked on” wording. | Used “Contributed to” for the API, preserved the five tests and team size, and separated documented project evidence from unverified qualifications. |
| Reusability | A concise general-purpose prompt with no specified scoring or report contract. | The installed skill supplies input handling, a rubric, and an output template when invoked with a different resume and posting. |

## Measurable and observable improvements

1. **11 specified report sections versus 2 named sections.** A reviewer can locate the same information across roles.
2. **5 justified category scores versus 0.** A reader can reproduce the skill report’s 73/100 total from 22 + 21 + 14 + 12 + 4 and inspect the evidence behind each category.
3. **4 complete rewrite records versus 0.** Each skill record includes the exact source bullet, its problem, the rewrite, and why it works. The baseline supplied five replacement bullets without those paired records.
4. **10 terms evaluated under a keyword rule versus 0 scored terms.** Both responses identified keywords, while the skill made visible, buried or indirect, and absent coverage auditable.

This is a single-pair qualitative comparison with one retained output per condition. The normal prompt already produced useful, mostly grounded edits. The measured differences concern what these two outputs contain. Scores are custom resume assessments and do not estimate interview selection or employer ATS results.
