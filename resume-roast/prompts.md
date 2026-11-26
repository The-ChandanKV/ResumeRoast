# Development prompts

## 1. User build brief

The original brief is reproduced below.

````text
Build a complete, reusable AI agent skill called **Resume Roast – Intelligent Resume Reviewer**.

The objective is to create a custom agent skill that can be invoked using `/resume-roast` in a supported AI coding agent and automatically analyse a candidate's resume against a job description.

This is an agent skill project, not a web application. Do not build an unnecessary frontend, backend or database.

### 1. Core Functionality

The skill should accept:

- A resume in PDF, Markdown or plain text format.
- A job description provided as a file or plain text.

The skill should automatically:

- Extract relevant information from the resume.
- Identify job requirements.
- Compare the candidate's qualifications against the job description.
- Identify matching and missing skills.
- Detect weak resume bullet points.
- Identify formatting and readability issues.
- Suggest specific improvements.
- Generate improved resume bullet points.
- Provide a structured final evaluation.

### 2. Resume Evaluation System

Evaluate the resume using the following criteria:

- Technical skills alignment: 30 marks
- Experience and project relevance: 25 marks
- Keyword alignment: 20 marks
- Resume structure and readability: 15 marks
- Quantifiable achievements: 10 marks

Generate an overall score out of 100.

Clearly explain that this is a custom resume assessment score, not an actual score from an employer's ATS.

Provide a short justification for every category score.

### 3. Resume Roast Behaviour

The agent should behave like an experienced technical recruiter and resume reviewer.

It must:

- Be direct and constructive.
- Avoid generic feedback.
- Identify specific weaknesses.
- Explain why each weakness matters.
- Provide actionable corrections.
- Prioritize the most important improvements.
- Never invent experience, achievements, qualifications or skills.
- Never guarantee interview selection.

For every weak bullet point, provide:

- Original bullet point.
- Identified problem.
- Improved bullet point.
- Explanation of the improvement.

Use placeholders for missing numerical achievements rather than fabricating metrics.

### 4. Structured Output

Every evaluation should follow this format:

**RESUME ROAST REPORT**

1. Overall resume assessment score
2. Hiring suitability summary
3. Score breakdown
4. Matching skills
5. Missing skills
6. Critical resume mistakes
7. Weak bullet points and improved versions
8. Keyword recommendations
9. Formatting improvements
10. Top five priority actions
11. Final assessment

The final assessment must distinguish between resume quality and the candidate's actual eligibility for the role.

### 5. Skill Implementation

Create a proper reusable agent skill using the supported Agent Skills format.

Include:

- SKILL.md with valid YAML frontmatter.
- A clear skill name and description.
- Detailed execution instructions.
- Input handling instructions.
- Evaluation rubric.
- Output template.
- Examples.
- Error handling instructions.

Configure the skill so that it can be discovered and invoked in a completely fresh agent session.

Use the native skill installation structure of the coding agent available in the current environment.

Support `/resume-roast` invocation wherever the agent supports slash commands.

### 6. Project Structure

Create a clean project structure containing:

- resume-roast/
  - SKILL.md
  - references/
    - evaluation-rubric.md
    - review-guidelines.md
    - output-template.md
  - examples/
    - software-engineer-resume.md
    - data-analyst-resume.md
    - ai-engineer-resume.md
    - software-engineer-jd.md
    - data-analyst-jd.md
    - ai-engineer-jd.md
  - reports/
  - README.md
  - prompts.md
  - TESTING.md
  - COMPARISON.md

Keep the architecture simple. Add Python scripts only if they are genuinely necessary.

### 7. Testing

Create three fictional resumes and corresponding job descriptions for:

1. Software Engineer Fresher
2. Data Analyst Intern
3. AI/ML Engineer Intern

Test the skill on all three inputs.

Verify that:

- The skill starts correctly in a fresh agent session.
- The skill produces structured evaluations.
- The score breakdown is consistent with the evaluation rubric.
- Missing qualifications are correctly identified.
- Suggested improvements are specific and actionable.
- No experience or achievements are fabricated.
- Invalid or missing files are handled gracefully.

### 8. With Skill vs Without Skill Comparison

This is a mandatory part of the internship assignment.

Evaluate the same resume and job description:

- Once using a normal prompt without the custom skill.
- Once using the Resume Roast skill.

Save both actual outputs.

Create COMPARISON.md comparing:

- Output structure
- Feedback quality
- Specificity
- Consistency
- Keyword identification
- Actionable recommendations
- Accuracy
- Reusability

Explain at least three measurable or observable improvements introduced by the custom skill.

Do not fabricate comparison results. Perform the actual comparison and document the observed differences.

### 9. Documentation

Create a professional README.md containing:

- Project overview.
- Problem statement.
- Objectives.
- Features.
- Skill architecture.
- Installation instructions.
- Usage examples.
- Evaluation methodology.
- Sample output.
- Testing results.
- Before-and-after comparison.
- Limitations.
- Future improvements.

Include exact instructions for installing and invoking the skill in the supported coding agent.

Maintain prompts.md containing the development prompts in chronological order.

### 10. Final Development Instructions

Build the complete project directly inside the current workspace.

Do not merely explain how agent skills work. Create all necessary files, implement the actual reusable skill and provide working installation instructions.

Avoid unnecessary frameworks, APIs, databases and user interfaces.

Use fictional sample resumes instead of personal information.

Perform all available tests. If fresh-session testing cannot be performed from the current environment, clearly document the remaining verification steps.

The final project must be lightweight, reusable, demonstration-ready and suitable for internship submission and GitHub publication.
````

## 2. Baseline evaluation before installation

```text
Review the resume in resume-roast/examples/software-engineer-resume.md against the job description in resume-roast/examples/software-engineer-jd.md and suggest improvements.
```

## 3. Fresh-session skill evaluation and input-error checks

Each line was sent to a separate, fresh Codex CLI session. Initial results exposed a directory fallback and score discrepancies. The skill was revised, then the same prompts were rerun.

```text
$resume-roast Review the resume in resume-roast/examples/software-engineer-resume.md against the job description in resume-roast/examples/software-engineer-jd.md and suggest improvements.
$resume-roast Review the resume in resume-roast/examples/data-analyst-resume.md against the job description in resume-roast/examples/data-analyst-jd.md and suggest improvements.
$resume-roast Review the resume in resume-roast/examples/ai-engineer-resume.md against the job description in resume-roast/examples/ai-engineer-jd.md and suggest improvements.
$resume-roast Review the resume in resume-roast/examples/missing-resume.md against the job description in resume-roast/examples/software-engineer-jd.md.
$resume-roast Review the resume at resume-roast/examples (a supplied path) against the job description in resume-roast/examples/software-engineer-jd.md.
```

## 4. PDF and pasted job description

The machine-specific paths below are represented by placeholders. The original software-engineering posting was pasted verbatim.

```text
$resume-roast Review the resume PDF at "<temporary PDF path>" against the pasted job description below. For local PDF extraction, use the host's bundled Python at "<bundled Python path>" with pypdf available through PYTHONPATH.

Job description
[Contents of resume-roast/examples/software-engineer-jd.md]
```

## 5. Plain-text resume

```text
$resume-roast Review the plain-text resume at "<temporary TXT path>" against the job description in resume-roast/examples/data-analyst-jd.md.
```
