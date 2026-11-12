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

### 6. Recorded Evaluation Results — 20 Applications

The following scores have been transcribed from the original **Truck Trip Planner QA Assessment** workbook (Master Assessment and Individual QA Analysis sheets). Application identifiers are anonymised to preserve candidate privacy. The category order is ELD Accuracy, Other Functional Requirements, UI Aesthetics, UX Intuitiveness, and Bugs & Functionality.

| Application ID | ELD /5 | Other Functional /5 | UI /5 | UX /5 | Bugs /5 | Total /25 | Percentage | Evaluation status |
|---|---:|---:|---:|---:|---:|---:|---:|---|
| Application 01 | 3 | 3 | 3 | 3 | 3 | 15 | 60% | Complete |
| Application 02 | 4 | 4 | 2 | 3 | 4 | 17 | 68% | Complete |
| Application 03 | 2 | 2 | 3 | 3 | 1 | 11 | 44% | Complete |
| Application 04 | 3 | 4 | 4 | 3 | 2 | 16 | 64% | Complete |
| Application 05 | 1 | 2 | 2 | 1 | 1 | 7 | 28% | Complete |
| Application 06 | 1 | 1 | 2 | 1 | 1 | 6 | 24% | Blocked |
| Application 07 | 1 | 1 | 3 | 1 | 1 | 7 | 28% | Blocked |
| Application 08 | 1 | 2 | 1 | 1 | 1 | 6 | 24% | Partially Evaluated |
| Application 09 | 1 | 1 | 1 | 1 | 1 | 5 | 20% | Blocked |
| Application 10 | 1 | 1 | 1 | 1 | 1 | 5 | 20% | Blocked |
| Application 11 | 1 | 1 | 4 | 2 | 1 | 9 | 36% | Blocked |
| Application 12 | 2 | 2 | 4 | 3 | 1 | 12 | 48% | Complete |
| Application 13 | 1 | 1 | 3 | 1 | 1 | 7 | 28% | Blocked |
| Application 14 | 1 | 1 | 4 | 1 | 1 | 8 | 32% | Blocked |
| Application 15 | 4 | 4 | 4 | 4 | 3 | 19 | 76% | Complete |
| Application 16 | 4 | 3 | 4 | 4 | 2 | 17 | 68% | Complete |
| Application 17 | 1 | 1 | 2 | 1 | 1 | 6 | 24% | Partially Evaluated |
| Application 18 | 1 | 3 | 4 | 3 | 1 | 12 | 48% | Complete |
| Application 19 | 1 | 1 | 4 | 2 | 1 | 9 | 36% | Blocked |
| Application 20 | 1 | 1 | 2 | 1 | 1 | 6 | 24% | Blocked |

**Important scoring-method clarification:** The original assessment workbook assigned a minimum score of 1 in each category when the 1–5 rubric was applied, including cases where access or a backend/API problem prevented the core workflow from being exercised. Those historical scores are preserved exactly rather than silently changed to NT. For applications marked **Blocked**, the low functional/ELD scores must not be interpreted as proof that inaccessible calculations or logs were defective. The recorded observation explains what was and was not verifiable. The UI score, where separately assessed, reflects only the visible interface.

**Status summary:** 9 Complete; 2 Partially Evaluated; 9 Blocked. All 20 rows have historical numeric scores in the source workbook, but not all 20 applications had a fully testable core workflow.

### 7. Application Evaluation Notes

#### Application 01

- **Scores:** ELD 3/5; Other Functional 3/5; UI 3/5; UX 3/5; Bugs & Functionality 3/5.
- **Total:** 15/25 (60%).
- **Evaluation status:** Complete.
- **Recorded assessment observations:** Functional foundation; required inputs and basic ELD logs/map present. Missing rest breaks, fuel stops and pickup/drop-off activities; difficult map use; weak validation and guidance.

#### Application 02

- **Scores:** ELD 4/5; Other Functional 4/5; UI 2/5; UX 3/5; Bugs & Functionality 4/5.
- **Total:** 17/25 (68%).
- **Evaluation status:** Complete.
- **Recorded assessment observations:** Broad functional coverage: four inputs, optional start time, stops/timings, breaks, fuel, pickup/drop-off, row totals and daily miles. Weak presentation; blank hours/remarks/header fields, unnamed stops, truncated text and nested scrolling.

#### Application 03

- **Scores:** ELD 2/5; Other Functional 2/5; UI 3/5; UX 3/5; Bugs & Functionality 1/5.
- **Total:** 11/25 (44%).
- **Evaluation status:** Complete.
- **Recorded assessment observations:** Generated schedule appeared HOS-compliant but did not correspond to submitted trip. Inputs not reflected; no stop markers, stops list or start date.

#### Application 04

- **Scores:** ELD 3/5; Other Functional 4/5; UI 4/5; UX 3/5; Bugs & Functionality 2/5.
- **Total:** 16/25 (64%).
- **Evaluation status:** Complete.
- **Recorded assessment observations:** Professional paper-style 24-hour logs, route continuity, stop events and PDF export. Selected 20-hour cycle not reflected in recap/availability; mileage varied between comparable runs; generation took about 30 seconds.

#### Application 05

- **Scores:** ELD 1/5; Other Functional 2/5; UI 2/5; UX 1/5; Bugs & Functionality 1/5.
- **Total:** 7/25 (28%).
- **Evaluation status:** Complete.
- **Recorded assessment observations:** Critical ELD concerns: incomplete 24-hour accounting, driving-limit and break violations, ignored cycle input, incomplete trip, PDF/on-screen inconsistency, impossible recap values and manual coordinates.

#### Application 06

- **Scores:** ELD 1/5; Other Functional 1/5; UI 2/5; UX 1/5; Bugs & Functionality 1/5.
- **Total:** 6/25 (24%).
- **Evaluation status:** Blocked.
- **Recorded assessment observations:** Backend API hostname DNS failure. U.S. locations could not be used; primary action and login/register controls did not work; no route, map, stops or ELD output. Core workflow unverified.

#### Application 07

- **Scores:** ELD 1/5; Other Functional 1/5; UI 3/5; UX 1/5; Bugs & Functionality 1/5.
- **Total:** 7/25 (28%).
- **Evaluation status:** Blocked.
- **Recorded assessment observations:** Backend reachable, but deployed frontend requests blocked by CORS/preflight failure. No route, map, itinerary or ELD logs. UI received a separate visual score; core workflow unverified.

#### Application 08

- **Scores:** ELD 1/5; Other Functional 2/5; UI 1/5; UX 1/5; Bugs & Functionality 1/5.
- **Total:** 6/25 (24%).
- **Evaluation status:** Partially Evaluated.
- **Recorded assessment observations:** Initially geocoding returned HTTP 429 and trip API HTTP 500; logs generated after cache clear. Days 1 and 2 accounted for only 23 and 22 hours; break/reset/14-hour compliance and recap could not be verified; sleeper-berth status unclear.

#### Application 09

- **Scores:** ELD 1/5; Other Functional 1/5; UI 1/5; UX 1/5; Bugs & Functionality 1/5.
- **Total:** 5/25 (20%).
- **Evaluation status:** Blocked.
- **Recorded assessment observations:** Registration blocked because Clerk development instance reached its 100-user limit. Planner inaccessible; score reflects inability to evaluate deployed product, not proven ELD defects.

#### Application 10

- **Scores:** ELD 1/5; Other Functional 1/5; UI 1/5; UX 1/5; Bugs & Functionality 1/5.
- **Total:** 5/25 (20%).
- **Evaluation status:** Blocked.
- **Recorded assessment observations:** Trip-planning submission returned HTTP 500. No route, map, stops or ELD logs generated. Server-side root cause not established; UI score provisional.

#### Application 11

- **Scores:** ELD 1/5; Other Functional 1/5; UI 4/5; UX 2/5; Bugs & Functionality 1/5.
- **Total:** 9/25 (36%).
- **Evaluation status:** Blocked.
- **Recorded assessment observations:** Professional interface and accessible form, but planning failed because backend could not resolve PostgreSQL hostname. No route/map/stops/logs; raw internal database error exposed.

#### Application 12

- **Scores:** ELD 2/5; Other Functional 2/5; UI 4/5; UX 3/5; Bugs & Functionality 1/5.
- **Total:** 12/25 (48%).
- **Evaluation status:** Complete.
- **Recorded assessment observations:** Complete 24-hour logs and attractive map/log presentation, but pickup resolved to Huston-Tillotson University in Austin instead of Houston; 20 prior cycle hours ignored in recap; 30-minute breaks missing after 8 hours on Days 1 and 2; fuel stop late.

#### Application 13

- **Scores:** ELD 1/5; Other Functional 1/5; UI 3/5; UX 1/5; Bugs & Functionality 1/5.
- **Total:** 7/25 (28%).
- **Evaluation status:** Blocked.
- **Recorded assessment observations:** Signup blocked by CORS preflight failure between deployed frontend and backend. No planner or ELD outputs accessible; login was not confirmed tested.

#### Application 14

- **Scores:** ELD 1/5; Other Functional 1/5; UI 4/5; UX 1/5; Bugs & Functionality 1/5.
- **Total:** 8/25 (32%).
- **Evaluation status:** Blocked.
- **Recorded assessment observations:** Strong visual appearance, but trip-planning API returned HTTP 500. No route, map, stops or ELD logs. Exact server-side cause unknown without backend logs.

#### Application 15

- **Scores:** ELD 4/5; Other Functional 4/5; UI 4/5; UX 4/5; Bugs & Functionality 3/5.
- **Total:** 19/25 (76%).
- **Evaluation status:** Complete.
- **Recorded assessment observations:** Strongest observed submission: complete 24-hour logs, cycle recap reconciled with entered 20 hours and planned duty, HOS sequencing and multi-day trip worked, PDF export worked. Fuel stop about 45 miles late; ETA discrepancy about 30 minutes; final off-duty period not clearly shown.

#### Application 16

- **Scores:** ELD 4/5; Other Functional 3/5; UI 4/5; UX 4/5; Bugs & Functionality 2/5.
- **Total:** 17/25 (68%).
- **Evaluation status:** Complete.
- **Recorded assessment observations:** Correct route and complete 24-hour logs; driving limits, 30-minute breaks, 10-hour resets and cycle calculation verified. Generated dates were June 2025 rather than assessment date in November 2026; no fuel stop on a 1,786-mile trip despite 1,000-mile interval.

#### Application 17

- **Scores:** ELD 1/5; Other Functional 1/5; UI 2/5; UX 1/5; Bugs & Functionality 1/5.
- **Total:** 6/25 (24%).
- **Evaluation status:** Partially Evaluated.
- **Recorded assessment observations:** European manual driver-log application rather than a U.S. ELD trip planner. No FMCSA HOS logs, U.S. route planning, map, stops, fuel or multi-day itinerary; Russian-language interface and weak validation.

#### Application 18

- **Scores:** ELD 1/5; Other Functional 3/5; UI 4/5; UX 3/5; Bugs & Functionality 1/5.
- **Total:** 12/25 (48%).
- **Evaluation status:** Complete.
- **Recorded assessment observations:** Strong interface, route/map interaction and dated three-day itinerary, but Day 2 driving 12.8 hours and Day 3 11.6 hours exceeded 11-hour limit. Entered 20 cycle hours appeared ignored; fuel stops insufficient; some checkpoints mislabeled.

#### Application 19

- **Scores:** ELD 1/5; Other Functional 1/5; UI 4/5; UX 2/5; Bugs & Functionality 1/5.
- **Total:** 9/25 (36%).
- **Evaluation status:** Blocked.
- **Recorded assessment observations:** Clean professional form with required inputs and explicit 70-hour/8-day prior-cycle wording plus rest strategy. Geocoding returned HTTP 502 for Dallas; no route, map, stops or ELD logs. Core workflow unverified.

#### Application 20

- **Scores:** ELD 1/5; Other Functional 1/5; UI 2/5; UX 1/5; Bugs & Functionality 1/5.
- **Total:** 6/25 (24%).
- **Evaluation status:** Blocked.
- **Recorded assessment observations:** Frontend loaded, but backend /api/trips/ request blocked by CORS: missing Access-Control-Allow-Origin and failed OPTIONS preflight. No trip, route, map, stops or ELD logs; core workflow unverified.


### 8. Evaluation Status Definitions

| Status | Meaning |
|---|---|
| Complete | The application workflow was sufficiently accessible to assess the main criteria and record the category scores. |
| Partially Evaluated | Some functionality was exercised, but important criteria remained unverified or the submission did not match the intended product scope. |
| Blocked | An access, deployment, authentication, API, or backend issue prevented meaningful evaluation of the core workflow. |

The status is separate from the historical numeric score. A blocked application's score does not prove that inaccessible functionality was tested.

### 9. Ranking Preparation

The original workbook ranks all 20 submissions by total score, including blocked or partially evaluated submissions. The published ranking retains that original score-based order for transparency, while clearly labelling evaluation limitations. Tied totals share the same rank.

### 10. Assessment Limitations

Scores represent the tester's reported hands-on observations and console/network observations recorded in the source workbook. They are not a source-code audit, security assessment, or formal regulatory certification. UI and UX scores involve evaluative judgement. Blocked applications have limited functional evidence, and their results should be interpreted accordingly.

### 11. Conclusion

The original 20-application score sheet has now been transcribed into this repository. The results preserve the recorded category scores, totals, percentages, and application-level observations while distinguishing completed, partially evaluated, and blocked workflows.
