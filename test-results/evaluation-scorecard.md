# Application Evaluation Scorecard
## Truck Trip Planner – Software Quality Assurance Assessment

### 1. Purpose

This scorecard provides a consistent method for evaluating the 20 Truck Trip Planner applications against the five assessment categories defined in the QA Test Plan.

Each category is scored from **1 to 5**, giving a maximum of **25 points** per application. The same criteria should be applied to every submission.

> **Evidence rule:** Enter scores only when supported by observations from the assessment. Do not invent scores, defects, or results. If a category could not be evaluated, mark it **NT (Not Tested)** and leave the total and percentage pending until the missing evaluation is resolved.

### 2. Assessment Scenario

| Item | Standard test data |
|---|---|
| Pickup location | Dallas, Texas |
| Stop / intermediate destination | Houston, Texas |
| Final drop-off | Los Angeles, California |
| Initial cycle hours | 20 hours |
| Applications assessed | 20 |

Use the same scenario and equivalent input values for each application wherever the application permits.

### 3. Scoring Scale

| Score | Rating | General interpretation |
|---:|---|---|
| 1 | Poor / Blocked | Core behaviour is unavailable, blocked, or substantially incorrect based on observed evidence. |
| 2 | Below Average | Major gaps or repeated errors are present; only limited expected behaviour works correctly. |
| 3 | Average | Main behaviour is partially or generally correct, but notable issues or omissions remain. |
| 4 | Good | Behaviour is largely correct and reliable, with only minor issues. |
| 5 | Excellent | Behaviour is complete, accurate, consistent, and works as expected with no significant observed issues. |

A score of **1** is a performance rating, not a substitute for an execution status. If the application or feature could not be accessed and no meaningful behaviour could be evaluated, record **NT** rather than assuming a score of 1.

### 4. Category-Specific Scoring Rubric

#### 4.1 ELD Accuracy (Maximum: 5)

Evaluate the correctness, completeness, and consistency of generated Electronic Logging Device (ELD) information.

| Score | Evaluation guidance |
|---:|---|
| 1 | ELD output is unavailable or substantially incorrect; major duty-status or time calculations fail. |
| 2 | Multiple significant errors exist in driving limits, duty windows, breaks, resets, cycle-hour calculations, or daily logs. |
| 3 | Some ELD calculations and logs are correct, but notable inaccuracies or missing information remain. |
| 4 | ELD calculations and logs are largely accurate and complete, with only minor discrepancies. |
| 5 | ELD calculations, duty-status sequencing, cycle-hour treatment, and daily logs are accurate, complete, and consistent with the assessment criteria. |

Review, where applicable:
- 11-hour driving limit.
- 14-hour duty window.
- Required 30-minute break.
- 10-hour off-duty reset.
- Initial cycle hours and remaining cycle-hour calculations.
- Complete 24-hour daily logs.
- Consistency between ELD entries, trip schedule, and summary.

#### 4.2 Other Functional Requirements (Maximum: 5)

Evaluate whether the application accepts inputs and performs the trip-planning functions beyond ELD calculations.

| Score | Evaluation guidance |
|---:|---|
| 1 | Core trip-planning workflow cannot be completed or produces fundamentally incorrect output. |
| 2 | Several major functional requirements fail, including input handling, route generation, stop scheduling, or trip continuity. |
| 3 | Core workflow works in part, but there are noticeable functional gaps or incorrect outputs. |
| 4 | Most functional requirements work correctly, with only minor issues. |
| 5 | Inputs, route generation, pickup/drop-off handling, stop scheduling, trip continuity, and relevant exports work correctly and consistently. |

Review, where applicable:
- Input acceptance and validation.
- Correct pickup, intermediate stop, and drop-off locations.
- Route generation and trip continuity.
- Rest-break and fuel-stop placement.
- Whether submitted inputs are reflected in generated results.
- Consistency of trip summaries and PDF exports.

#### 4.3 UI Aesthetics (Maximum: 5)

Evaluate the visual presentation and consistency of the user interface.

| Score | Evaluation guidance |
|---:|---|
| 1 | Interface is visually broken, severely inconsistent, or difficult to read. |
| 2 | Significant layout, readability, alignment, or visual consistency problems are present. |
| 3 | Interface is usable but has noticeable visual inconsistencies or presentation weaknesses. |
| 4 | Clean and consistent visual design with minor presentation issues. |
| 5 | Polished, coherent, readable, and visually consistent interface with effective information hierarchy. |

Consider:
- Layout and spacing.
- Typography and readability.
- Alignment and consistency.
- Visual hierarchy and presentation of trip/ELD information.
- Responsive behaviour where it was assessed.

#### 4.4 UX Intuitiveness (Maximum: 5)

Evaluate how easily a user can understand, navigate, and complete the main workflow.

| Score | Evaluation guidance |
|---:|---|
| 1 | Main workflow is confusing or unusable; users cannot reasonably complete key tasks. |
| 2 | Navigation and task completion require substantial effort or repeated guesswork. |
| 3 | Main workflow is understandable but contains noticeable friction or unclear interactions. |
| 4 | Workflow is straightforward, with only minor usability issues. |
| 5 | Navigation and task completion are intuitive, efficient, and provide clear feedback throughout. |

Consider:
- Clarity of labels and instructions.
- Ease of entering trip details.
- Navigation between workflow steps.
- Visibility and understanding of generated results.
- Helpful validation and error messages.
- Feedback when actions are submitted or completed.

#### 4.5 Bugs and Functionality (Maximum: 5)

This category evaluates observed application stability and the impact/frequency of defects. **Higher scores mean fewer or less severe observed defects and more reliable behaviour.**

| Score | Evaluation guidance |
|---:|---|
| 1 | Critical failures or blockers prevent meaningful use of core functionality. |
| 2 | Multiple major defects or recurring failures significantly affect use. |
| 3 | Application is partly reliable, but several moderate defects or intermittent failures remain. |
| 4 | Generally stable, with only minor or isolated defects. |
| 5 | Stable during the assessed workflow, with no significant defects observed. |

Consider:
- Crashes, blank screens, or inaccessible workflows.
- API, backend, or integration errors visible during testing.
- Incorrect or inconsistent outputs.
- Broken controls or failed actions.
- Error handling and recovery behaviour.

Do not count an unverified feature as a confirmed defect. Record observed defects in `bug-reports/bug-reports.md` and reference the relevant defect ID in the notes.

### 5. Score Calculation

Each category contributes equally to the overall score.

**Total score:**

`ELD Accuracy + Other Functional Requirements + UI Aesthetics + UX Intuitiveness + Bugs and Functionality`

**Maximum score:** 25

**Percentage:**

`(Total Score ÷ 25) × 100`

Example only: a hypothetical application scoring 4, 4, 3, 5, and 4 receives 20/25 = 80%.

Do not use this example as an actual assessment result.

### 6. Evaluation Register – 20 Applications

Enter the actual application identifier used in the assessment. Keep candidate names and confidential submission details out of this public case study.

| Application ID | ELD Accuracy /5 | Other Functional /5 | UI Aesthetics /5 | UX Intuitiveness /5 | Bugs & Functionality /5 | Total /25 | Percentage | Evaluation status |
|---|---:|---:|---:|---:|---:|---:|---:|---|
| Application 01 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 02 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 03 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 04 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 05 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 06 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 07 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 08 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 09 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 10 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 11 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 12 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 13 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 14 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 15 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 16 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 17 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 18 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 19 | — | — | — | — | — | Pending | Pending | Not recorded |
| Application 20 | — | — | — | — | — | Pending | Pending | Not recorded |

**Register instructions**
1. Replace each dash with a score from 1 to 5 only when evidence supports that score.
2. If a category was not assessed, enter **NT** and keep the total and percentage as **Pending**.
3. Calculate the total only when all five category scores are available.
4. Calculate the percentage using the formula above.
5. Set evaluation status to **Complete**, **Partially Evaluated**, or **Blocked**, as appropriate.
6. Keep supporting observations and defect references in the notes section below or in the linked defect report.

### 7. Application Evaluation Notes

Duplicate this section for each application as the assessment records are completed.

#### Application [ID]

| Field | Record |
|---|---|
| Application ID | Application [ID] |
| Date evaluated | [Enter date, if available] |
| Evaluation status | [Complete / Partially Evaluated / Blocked] |
| ELD Accuracy | [Score 1–5 or NT] |
| Other Functional Requirements | [Score 1–5 or NT] |
| UI Aesthetics | [Score 1–5 or NT] |
| UX Intuitiveness | [Score 1–5 or NT] |
| Bugs and Functionality | [Score 1–5 or NT] |
| Total score | [Pending until all five scores are available] |
| Percentage | [Pending until all five scores are available] |

**Observed strengths**
- [Record evidence-based observations.]

**Observed weaknesses**
- [Record evidence-based observations.]

**Defect references**
- [Add defect IDs from the defect register, or write “None recorded” if no defects were observed.]

**Testing limitations / unverified areas**
- [Record any inaccessible or untested functionality.]

**Evidence reference**
- [Add a non-confidential screenshot, test record, or other permitted evidence reference.]

### 8. Evaluation Status Definitions

| Status | Meaning |
|---|---|
| Complete | All five categories were evaluated and scored. |
| Partially Evaluated | Some categories were evaluated, but one or more remain untested. |
| Blocked | Access or a blocking issue prevented meaningful evaluation of the application. |

A blocked or partially evaluated application must not be presented as though all functionality was tested. Explain what could and could not be verified.

### 9. Ranking Preparation

Once the evaluation register contains complete, evidence-supported scores:
- Rank applications by total score, from highest to lowest.
- Use percentage as the equivalent normalised score.
- If applications have equal totals, report a tie unless a separately documented tie-break rule is agreed.
- Do not rank incomplete evaluations alongside fully evaluated applications without clearly labelling the limitation.
- Keep the application identifiers consistent with the later application-ranking document.

### 10. Assessment Limitations

Scores represent observed behaviour in the assessment environment and are not a source-code audit, security assessment, or formal regulatory certification. UI and UX scores are evaluative judgements and should be supported by concise observations. ELD/HOS scores reflect the criteria in the test plan.

### 11. Conclusion

This scorecard establishes a repeatable, equally weighted framework for comparing the 20 Truck Trip Planner applications. It supports transparent scoring, evidence-based findings, and consistent preparation of the final application ranking and QA report.
