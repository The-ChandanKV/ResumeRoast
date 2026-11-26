# RESUME ROAST REPORT

## 1. Overall resume assessment score

**73/100.** This is a custom resume assessment score. The employer’s applicant tracking system uses its own process.

## 2. Hiring suitability summary

Alex Rowan shows good alignment with the entry-level backend work at Example Product Studio. The Campus Lost-and-Found API demonstrates Python, Flask, REST API work, SQL, Git-based code review, and unit testing. Several of those qualifications appear only in the project notes, where a recruiter can easily miss them.

**CI pipeline familiarity is the most material gap.** The posting requires it, and the resume provides no evidence of it. The queue simulator shows practical use of data structures and gives Alex an example to build on when explaining how they work.

## 3. Score breakdown

| Category | Score | How it was calculated |
| --- | ---: | --- |
| Technical skills alignment | 22/30 | Required weight **24**. Python, SQL, Git, REST APIs, unit tests, and code review each earn 1. Explaining data structures earns 0.5. CI earns 0. Coverage is **6.5/8 × 24 = 19.5**. Preferred weight **6**. Flask earns 1, Docker earns 0, and cloud deployment earns 0. Coverage is **1/3 × 6 = 2**. Combined **21.5**, rounded to **22**. |
| Experience and project relevance | 21/25 | **10/10** for directly relevant backend and testing work, **6/8** for identifiable contributions with limited detail on ownership of the API features, and **5/7** for concrete SQL and testing work with limited evaluation detail. |
| Keyword alignment | 14/20 | **1 each** for the computer science degree, Python, Git, unit tests, and Flask. **0.5 each** for SQL, REST API, data structures, and code review because the evidence is indirect or in the project notes. **0** for CI pipelines. Coverage is **7/10 × 20 = 14**. |
| Resume structure and readability | 12/15 | **4/5** for recognizable sections with evidence split between Projects and Project Notes, **5/5** for consistent Markdown headings, bullets, and dates, and **3/5** for scannability because generic bullets obscure the most relevant work. |
| Quantifiable achievements | 4/10 | **4/5** for scope, supported by five tests and a two-person team. **0/5** for measured outcomes or evaluation results. |
| **Total** | **73/100** | **22 + 21 + 14 + 12 + 4** |

For the component scores, substantial evidence earns 75% of the available points, with halves rounded up. The scannability score uses the 50% anchor, rounded from 2.5 to 3.

## 4. Matching skills

| Posting requirement | Resume evidence |
| --- | --- |
| **Required** · Completed or in-progress CS or related degree | Education lists a B.Tech. in Computer Science, expected May 2027. The posting accepts an in-progress degree. |
| **Required** · Python and SQL | The Lost-and-Found project lists Python. Its notes describe SQL queries against PostgreSQL to filter listings by category and date. |
| **Required** · Git and collaboration through code review | The project notes say Alex reviewed a teammate’s changes through Git pull requests on a two-person team. |
| **Required** · REST APIs and unit tests | The API lets students create and search lost-item listings. The project bullet documents five pytest unit tests covering item creation, search, and invalid inputs. |
| **Required** · Explain basic data structures | **Partial.** The Course Queue Simulator compared FIFO and priority queues on sample inputs. The resume gives no explanation of their behavior or tradeoffs. |
| **Preferred** · Flask or comparable framework | The Lost-and-Found API was built with Flask. |
| **Core responsibility** · Build and test backend features | The API, PostgreSQL filtering, and pytest coverage are relevant examples. The posting explicitly accepts coursework and personal projects as experience. |

## 5. Missing skills

- **Required, not evidenced · CI pipeline familiarity.** The five pytest tests establish unit testing experience. The resume gives no example of configuring or using a pipeline to run them.
- **Required, partially evidenced · Explaining data structures.** The simulator demonstrates practical work with two queue types. If Alex can explain how each selects the next item and why that matters, that would strengthen the example.
- **Preferred, not evidenced · Docker and a cloud deployment project.** The resume supplies no evidence for either.

## 6. Critical resume mistakes

- **The main project bullets hide Alex’s strongest qualifications.** “Used a database” and “Used Git” are too generic to show SQL work or code review. Move the specific PostgreSQL queries and pull request reviews from Project Notes into the project entry.
- **The backend project’s first bullet omits what the API does.** A recruiter scanning Projects sees Python and Flask but has to read the notes to discover the REST API and its create and search features. Put those features in the first bullet.
- **The simulator bullet obscures the data structures work.** “Made a queue thing for class” leaves out both queue types and the comparison. Name the structures and describe the exercise.

## 7. Weak bullet points and improved versions

| Original | Problem | Improved | Why it works |
| --- | --- | --- | --- |
| “Worked on a backend project using Python and Flask.” | “Worked on” leaves the purpose and scope unclear. | Contributed to a Python and Flask REST API that lets students create and search lost-item listings. | Names the technology and user-facing features while preserving the stated level of ownership. |
| “Used a database.” | Leaves out the database engine and the work Alex performed. | Wrote SQL queries in PostgreSQL to filter lost-item listings by category and date. | Shows applied SQL and the specific filters Alex worked on. |
| “Used Git.” | Gives no evidence of how Alex collaborated. | Reviewed a teammate’s changes through Git pull requests on a two-person project team. | Makes the code review contribution and team scope concrete. |
| “Made a queue thing for class.” | Informal wording hides the structures and the comparison. | Built a course simulator that compared first-in, first-out (FIFO) and priority queues on sample inputs. | Gives the recruiter a concrete example of data structures work and explains the acronym. |

Keep the existing pytest bullet. It already gives the test count, framework, and behaviors covered.

## 8. Keyword recommendations

- Put **Python**, **Flask**, and **REST API** in the first Lost-and-Found bullet. Use **SQL** and **PostgreSQL** together in the filtering bullet.
- Use **code review** in the collaboration bullet if you want the posting’s exact wording. Keep **Git** and **pull requests** to show how the review happened.
- Keep **unit tests** and **pytest** together in the existing test bullet. Use **FIFO** and **priority queues** in the simulator entry.
- Add **CI pipelines**, **Docker**, or **cloud deployment** only after you can describe what you actually did with each.

## 9. Formatting improvements

- Remove the generic objective. Place Education first, followed by Projects and Skills.
- Fold the Project Notes into the relevant project bullets, then remove the separate notes section once the details are accounted for.
- Keep the consistent project dates and short bullets. In Skills, consider writing **SQL (PostgreSQL)** so the language is visible during a quick scan.

The Markdown supports a review of section order, wording, dates, and bullet structure. Font, margins, and pagination remain unverified.

## 10. Top five priority actions

1. **Address the CI gap.** If you already have hands-on CI experience, document what you configured or used. Otherwise, set up a pipeline to run the existing pytest suite and describe it after it works.
2. **Rewrite the Lost-and-Found entry around the REST API, SQL queries, and pull request reviews.** Keep the five-test bullet.
3. **Rewrite the simulator bullet.** If you can substantiate a specific difference observed on the sample inputs, add it.
4. **Remove the generic objective and consolidate Project Notes into Projects.** Keep the in-progress CS degree easy to find.
5. **Treat Docker and cloud deployment as secondary.** If you later containerize and deploy the API, describe the work once you can verify it.

## 11. Final assessment

**Resume quality** — The projects contain credible backend evidence for a fresher role. The biggest writing improvement is to put specific work in the bullets recruiters will scan first. The SQL and code review rewrites make the application stronger using facts already in the resume.

**Actual role eligibility** — The in-progress computer science degree satisfies the stated education condition, and the posting accepts the type of project experience shown. CI pipeline familiarity remains unverified, and the simulator provides partial evidence of the ability to explain basic data structures. Docker and cloud deployment are preferred qualifications.