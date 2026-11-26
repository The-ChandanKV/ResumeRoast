# RESUME ROAST REPORT

## 1. Overall resume assessment score

**73/100.** This is a custom resume assessment score. The employer’s applicant tracking system (ATS) uses its own process.

## 2. Hiring suitability summary

The resume shows a solid project-based fit for this entry-level backend role. The Campus Lost-and-Found API combines Python, Flask, PostgreSQL, five pytest unit tests, and teammate code review. Most of that evidence is buried in **Project notes**, while the project bullets lead with “Worked on” and “Used.” CI pipeline familiarity is the clearest gap in the required qualifications.

## 3. Score breakdown

| Category | Score | Calculation and evidence |
|---|---:|---|
| Technical skills alignment | 22/30 | Required coverage is **6.5/8 × 24 = 19.5**. Python, SQL, Git, REST APIs, unit tests, and code review each earn 1. Explaining data structures earns 0.5. CI earns 0. Preferred coverage is **1/3 × 6 = 2**. Flask earns 1. Docker and cloud deployment each earn 0. The combined 21.5 rounds to 22. |
| Experience and project relevance | 21/25 | **10/10** for relevance to backend development and testing, **6/8** for ownership and scope because the SQL, testing, and review contributions are clear but ownership of specific API features is unclear, and **5/7** for execution and validation through SQL filters and five tests covering normal and invalid inputs. |
| Keyword alignment | 14/20 | **7/10 × 20 = 14**. Computer science degree, Python, Git, unit tests, and Flask each earn 1 in standard resume sections. SQL, REST API, data structures, and code review each earn 0.5 because the wording is indirect or the evidence is in Project notes. CI pipelines earn 0. |
| Resume structure and readability | 12/15 | **4/5** for recognizable sections with project details split across two places, **5/5** for consistent and legible formatting on the rendered page, and **3/5** for hierarchy because headings and body text have similar visual weight and key evidence sits in a closing paragraph. |
| Quantifiable achievements | 4/10 | **4/5** for relevant scope and coverage through five tests and a two-person team. **0/5** for measured outcomes or evaluation results. The simulator mentions a comparison without reporting its findings. |
| **Total** | **73/100** | **22 + 21 + 14 + 12 + 4** |

## 4. Matching skills

| Posting requirement | Resume evidence | Match |
|---|---|---|
| In-progress or completed computer science or related degree | Education lists a B.Tech. in Computer Science, expected May 2027. | Direct |
| Python and REST API development | The Campus Lost-and-Found project uses Python and Flask. Project notes describe a REST API for creating and searching lost-item listings, with a specific SQL contribution. | Direct |
| SQL | Project notes say the candidate wrote PostgreSQL queries to filter listings by category and date. | Direct |
| Git and teammate code review | Project notes describe reviewing a teammate’s changes through Git pull requests on a two-person team. | Direct |
| Unit tests | The API project lists five pytest unit tests for item creation, search, and invalid inputs. | Direct |
| Explain basic data structures | The Course Queue Simulator compared FIFO and priority queues on sample inputs. The resume gives no explanation of their behavior or trade-offs. | Partial |
| Flask or a comparable framework | Flask is named in the API project and Skills. | Direct, preferred |

## 5. Missing skills

- **Required — CI pipeline familiarity.** The resume documents pytest tests. CI use or familiarity is unverified.
- **Required — explaining data structures.** The simulator shows applied queue work. Add a specific observation about processing order if the candidate can verify and explain it.
- **Preferred — Docker and cloud deployment.** Both are unverified. The posting accepts coursework and personal projects, and the in-progress degree meets its stated academic condition.

## 6. Critical resume mistakes

- **The project notes carry the strongest evidence.** Move the REST API, PostgreSQL filtering, and pull-request review details into the Campus Lost-and-Found API entry. A reader scanning the current bullets sees tools without seeing what the candidate did with them.
- **The lead API bullet obscures the candidate’s contribution.** Name the API’s purpose and the candidate’s verified work. If the candidate personally built or maintained specific endpoints, identify those endpoints. The current resume establishes participation and specific SQL and testing contributions.

## 7. Weak bullet points and improved versions

| Original | Problem | Improved | Why it works |
|---|---|---|---|
| “Worked on a backend project using Python and Flask.” | “Worked on” leaves the deliverable and contribution unclear. | Contributed to a Python and Flask REST API that lets students create and search lost-item listings. | Identifies the deliverable and its user-facing functions while preserving the scope of the candidate’s contribution. |
| “Used a database.” | Omits the database, the candidate’s action, and the purpose of the queries. | Wrote SQL queries in PostgreSQL to filter lost-item listings by category and date. | Shows applied SQL and gives the reader a concrete example. |
| “Used Git.” | Names a tool but leaves out the code review evidence. | Reviewed a teammate’s code changes through Git pull requests on a two-person team. | Shows collaboration, the review workflow, and team size. |
| “Made a queue thing for class.” | Informal wording hides the coursework’s technical substance. | Built a course simulator that compared first-in, first-out (FIFO) and priority queues on sample inputs. | Names the data structures and explains what the simulator did without inventing results. |

Keep the existing pytest bullet. It already gives the test count, tool, and scenarios covered.

## 8. Keyword recommendations

- Use **Python**, **Flask**, and **REST API** in the lead API project bullet. Put **SQL** and **PostgreSQL** together in the query bullet.
- Put **Git**, **code review**, and **pull requests** in the collaboration bullet. Keep **unit tests** and **pytest** in the testing bullet.
- Use **queue data structures**, **FIFO**, and **priority queue** in the simulator entry where they describe the work.
- Add **CI pipelines**, **Docker**, or **cloud deployment** only when the candidate can describe real experience with each term.

## 9. Formatting improvements

The rendered PDF is a legible, single-column page with consistent dates and spacing. Give section headings and project names more visual weight so the reader can scan them quickly. Fold **Project notes** into the individual entries and remove the generic objective, “Hardworking student looking for a challenging opportunity.” Keep the degree and expected graduation date near the top.

## 10. Top five priority actions

1. Move the verified REST API, SQL, and pull-request review evidence into the API project bullets.
2. Address the CI gap. If the candidate has used a pipeline, describe what it ran. Otherwise, configure the existing pytest suite to run in CI and document it once it works.
3. Make individual API ownership explicit wherever the candidate can verify which features or endpoints they built or maintained.
4. Rewrite the simulator bullet and add a verified observation about how FIFO and priority ordering differed on the sample inputs.
5. Remove the generic objective and distinguish section headings and project names visually.

## 11. Final assessment

**Resume quality** — The candidate’s best evidence is already in the document. Moving it into the project entries would make the resume more persuasive by showing concrete backend work, testing, and collaboration where a reviewer expects to find them.

**Actual role eligibility** — The in-progress computer science degree meets the stated academic condition, and the projects substantiate most required technical skills. CI familiarity remains unverified, and the ability to explain basic data structures is only partially evidenced. Flask meets one preference. Docker and cloud deployment remain unverified.