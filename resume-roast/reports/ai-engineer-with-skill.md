# RESUME ROAST REPORT

## 1. Overall resume assessment score

**67/100.** This is a custom resume assessment score. The employer’s ATS uses its own process.

## 2. Hiring suitability summary

Jordan shows **partial alignment** with the AI/ML Engineer Intern role. The strongest evidence is the recycling image classifier, which achieved **0.78 macro F1 on a held-out test set**, compared with **0.62 for a majority-class baseline**. That result is buried in Project notes while the main bullet says “Got good results.” The most material required gaps are validation split documentation and error analysis.

## 3. Score breakdown

| Category | Score | Calculation and evidence |
|---|---:|---|
| Technical skills alignment | 17/30 | Required coverage is **5/7 × 24**. Git, PyTorch, baseline comparison, and classification metrics each earn 1. Python and split documentation each earn 0.5. Error analysis earns 0. Preferred coverage is **0/3 × 6** for deployment, Docker, and experiment tracking. The combined result rounds to 17. |
| Experience and project relevance | 21/25 | **10/10** for relevance to training and evaluating prototypes, **6/8** for ownership and scope because the notes clarify the candidate’s work but give little dataset scope, and **5/7** for execution and validation because the held-out comparison is documented while validation and error analysis are missing. |
| Keyword alignment | 13/20 | **6/9 × 20**, rounded. Related degree, Python, Git, and PyTorch each earn 1 for visibility. Model training, data splits, baseline comparison, and classification metrics each earn 0.5 because the supporting wording is buried in notes. Error analysis earns 0. Python earns full visibility credit here and partial applied-use credit under technical alignment. |
| Resume structure and readability | 12/15 | **4/5** for recognizable sections with evidence split across Projects and Project notes, **5/5** for consistent headings, dates, and bullets, and **3/5** for scannability because the main project entries omit the most informative details. |
| Quantifiable achievements | 4/10 | **0/5** for scope because dataset and test-set sizes are absent, and **4/5** for outcomes because the recycling classifier has a quantified baseline comparison while the ticket classifier has no reported evaluation result. |
| **Total** | **67/100** | **17 + 21 + 13 + 12 + 4** |

## 4. Matching skills

| Posting requirement or responsibility | Resume evidence |
|---|---|
| Current enrollment in a related field | **Partially evidenced.** Education lists a B.Eng. in Computer Engineering expected May 2027. The degree field matches, and the expected date suggests current enrollment. |
| Python, Git, and PyTorch or TensorFlow | **Direct evidence for Git and PyTorch.** Project notes describe training the recycling classifier in PyTorch and tracking ticket preprocessing and training scripts in Git. **Partial evidence for Python**, which appears in Skills without explicit project attribution. |
| Document train, validation, and test splits and compare with a baseline | **Direct evidence for baseline comparison.** The recycling notes give both macro F1 scores. **Partial evidence for split documentation.** The notes mention training and a held-out test set, with no validation set or split procedure described. |
| Use classification metrics and perform error analysis | **Direct evidence for classification metrics.** The recycling notes report macro F1. **Error analysis is not evidenced.** |
| Train and evaluate prototype models | **Direct evidence.** The recycling project covers training and held-out evaluation. The ticket project describes a comparison of logistic regression and a linear SVM using TF-IDF features. |

## 5. Missing skills

- **Required evidence.** Document how training, validation, and test data were separated if all three were used. Error analysis is not evidenced. If it was performed, describe which classes or examples were misclassified and what you learned. Tie Python to a specific project task if you can confirm its use.
- **Preferred evidence.** Deployment with FastAPI or a similar framework, Docker, and experiment tracking with MLflow or Weights & Biases are not evidenced. Git supports version control for scripts. Experiment tracking would need its own evidence, such as logged runs and metrics.
- **Eligibility.** The degree field matches. State that you are currently enrolled if accurate, since the posting explicitly requires it.

## 6. Critical resume mistakes

- **The project bullets bury the strongest evidence.** “Got good results” gives reviewers no way to assess model performance. Move the held-out macro F1 scores and majority-class baseline into the recycling project itself.
- **The recycling entry leaves two required evaluation practices unclear.** The held-out test set establishes part of the evaluation setup. Add the actual split procedure and a concrete error-analysis finding if that work exists. If you still need to do the work, describe it after completion.

## 7. Weak bullet points and improved versions

| Original | Problem | Improved | Why it works |
|---|---|---|---|
| “Built a machine learning model.” | Omits the framework, task, and data. | Trained a PyTorch image classifier on labeled recycling images. | Makes the model training and applied PyTorch experience visible. |
| “Got good results.” | Gives no metric, test context, or benchmark. | Evaluated the classifier on a held-out test set, achieving 0.78 macro F1 versus 0.62 for a majority-class baseline. | Shows how performance was measured and provides a comparison. |
| “Tried a few text models.” | Hides the models, features, and comparison. | Compared logistic regression and a linear support vector machine in scikit-learn for support ticket classification using TF-IDF features. | Identifies the task and methods without inventing a result. |
| “Used Git for the project.” | Gives no indication of what Git was used for. | Tracked preprocessing and model training scripts in Git. | Shows how Git supported the project workflow. |

## 8. Keyword recommendations

- **Recycling project.** Use **PyTorch**, **image classification**, **held-out test set**, **macro F1**, and **majority-class baseline** in the project bullets.
- **Support ticket project.** Use **scikit-learn**, **logistic regression**, **linear support vector machine**, **TF-IDF**, and **Git**. Add **Python** to a project bullet if you can name the work you did with it.
- **Conditional additions.** Use **validation split**, **error analysis**, **FastAPI** or the framework used, **Docker**, and **MLflow** or **Weights & Biases** only where you can describe actual work.

## 9. Formatting improvements

Keep Education near the top so reviewers can find the degree and expected graduation date. Keep the reverse-chronological project order, place the evaluation result directly under the recycling project, and fold the relevant notes into the two project entries. The review covers the Markdown structure. Rendered page layout, margins, and typography were unavailable for inspection.

## 10. Top five priority actions

1. Document the actual train, validation, and test setup, and add a concrete error-analysis finding if available. Complete the missing evaluation work before claiming it.
2. Put the **0.78 versus 0.62 macro F1** comparison directly in the recycling project.
3. State current enrollment explicitly if accurate.
4. Replace the generic ticket classifier bullets with the model comparison, TF-IDF features, and Git workflow.
5. Add verified scope or results where available, such as the number of test images or the ticket models’ evaluation scores. Replace or remove any drafting placeholders before submitting.

## 11. Final assessment

**Resume quality** — The projects fit the internship, but the main bullets understate the work. The recycling benchmark and the ticket model comparison are already documented and can make the resume stronger immediately.

**Actual role eligibility** — The resume shows a matching degree field and relevant model training and evaluation. Current enrollment is suggested by the expected graduation date. Full coverage of the required evaluation practices remains unverified because validation split documentation and error analysis are absent. Deployment, Docker, and experiment tracking are preferred qualifications.