# Software Quality Assurance Case Study
## Truck Trip Planner — Functional Testing, ELD/HOS Evaluation & UI/UX Review

A portfolio case study documenting a manual QA assessment of **20 independently developed Truck Trip Planner applications**. The project covers test planning, functional test design, ELD/HOS output review, defect observation, comparative scoring, reporting, and quality improvement recommendations.

> **Assessment snapshot:** 20 applications reviewed · 5 scoring categories · 9 complete · 2 partially evaluated · 9 blocked  
> **Highest recorded score:** 19/25 (76%) — Application 15  
> **Assessment route:** Dallas, Texas → Houston, Texas → Los Angeles, California · **Initial cycle hours:** 20

**Start here:** [Open the Test Execution Dashboard](test-results/test-execution-dashboard.md) · [Read the Final QA Report](final-report/final-qa-report.md) · [View the Application Ranking](test-results/application-ranking.md)

---

## 1. Project Overview

The objective was to assess application functionality, Electronic Logging Device (ELD) accuracy, Hours of Service (HOS) calculations, user interface design, user experience, and overall reliability against the assessment requirements.

The original assessment workbook was used to transcribe the 20 application scores, score-based ranking, and application-level observation summaries into this portfolio. The repository distinguishes observed behaviour from features that could not be verified because an application was inaccessible or its workflow was blocked.

## 2. Assessment at a Glance

| Measure | Result |
|---|---:|
| Applications assessed | 20 |
| Scoring categories | 5 |
| Maximum score per application | 25 |
| Complete evaluations | 9 (45%) |
| Partially evaluated | 2 (10%) |
| Blocked | 9 (45%) |
| Highest score | 19/25 (76%) |
| Mean historical score | 10/25 (40%) |
| Median historical score | 8.5/25 (34%) |

**Scoring categories:** ELD Accuracy · Other Functional Requirements · UI Aesthetics · UX Intuitiveness · Bugs & Functionality.

**Scoring formula:** `(Total Score ÷ 25) × 100`.

> **How to interpret the results:** The original workbook assigned a minimum score of 1 in each category, including where the core workflow was blocked. Historical scores are preserved. A blocked application's low functional/ELD score is not proof that inaccessible calculations or logs were tested and found defective. See the [scorecard](test-results/evaluation-scorecard.md) for application-level context.

## 3. Standard Test Scenario

| Input | Assessment value |
|---|---|
| Starting location | Dallas, Texas |
| Intermediate stop / pickup | Houston, Texas |
| Final destination | Los Angeles, California |
| Initial cycle hours | 20 |
| Daily log review | 24-hour ELD log |
| Fuel-stop assessment interval | Every 1,000 miles |

The assessment reviewed whether each application could use the supplied trip inputs to generate an appropriate route, itinerary, stops, rest periods, and multi-day ELD logs.

## 4. Testing Scope and Activities

| Area | What was evaluated |
|---|---|
| Functional testing | Required inputs, trip generation, route planning, stops, and expected outputs |
| ELD/HOS review | Daily log completeness, driving hours, rest periods, cycle calculations, and duty sequencing |
| UI evaluation | Layout, visual presentation, readability, and information organisation |
| UX evaluation | Navigation, clarity, ease of interaction, and usability |
| Defect observation | Functional inconsistencies, output problems, API/integration errors, and application availability |

### Key QA activities

- Reviewed 20 independently developed applications using a common scenario.
- Examined trip inputs and generated route/itinerary outputs.
- Reviewed ELD daily logs and HOS-related calculations where available.
- Evaluated rest-break and fuel-stop scheduling.
- Observed frontend/backend integration and access failures.
- Recorded usability and presentation concerns.
- Applied the original five-category scoring framework.
- Compared submissions and prepared quality improvement recommendations.

## 5. Key Assessment Findings

The source assessment notes recorded recurring concerns across selected applications:

- Incomplete or inconsistent 24-hour ELD logs.
- Driving-limit, rest-break, and cycle-hour calculation concerns.
- Submitted inputs not reflected in generated schedules or recaps.
- Missing, late, or insufficiently scheduled fuel stops.
- Incorrect location resolution and route/checkpoint inaccuracies.
- Backend API, DNS, CORS, and database connectivity failures.
- Authentication and deployment accessibility blockers.
- Differences between on-screen results and exported PDF reports.
- Incomplete log fields, unclear labels, and usability issues.

These are cross-submission themes, not claims that every application exhibited every issue. The [bug report register](bug-reports/bug-reports.md) separates functional observations from access/integration blockers and records evidence limitations.

## 6. Project Documentation

Use this guide to explore the work in assessment order.

| Stage | Document | What it contains |
|---|---|---|
| 01 — Plan | [QA Test Plan](test-plan/test-plan.md) | Objectives, scope, scenario, approach, criteria, and limitations. |
| 02 — Design | [Functional Test Cases](test-cases/functional-test-cases.md) | Ten functional test cases, expected results, and retrospective execution observations. |
| 03 — Record | [Bug Reports & Observations](bug-reports/bug-reports.md) | Application-level observations, severity, retest paths, and access blockers. |
| 04 — Monitor | [Test Execution Dashboard](test-results/test-execution-dashboard.md) | Assessment snapshot, status distribution, key findings, and test coverage summary. |
| 05 — Score | [Evaluation Scorecard](test-results/evaluation-scorecard.md) | Five-category rubric, 20 application scores, and individual notes. |
| 06 — Compare | [Application Ranking](test-results/application-ranking.md) | Score-based ranking, ties, summary statistics, and interpretation limits. |
| 07 — Report | [Final QA Report](final-report/final-qa-report.md) | Consolidated approach, quantitative results, findings, limitations, and conclusions. |
| 08 — Improve | [Quality Improvement Recommendations](recommendations/quality-improvement.md) | Engineering improvement areas, priorities, and suggested QA practices. |

## 7. Skills Demonstrated

Manual software testing · Functional test design · ELD/HOS output review · UI/UX evaluation · Defect documentation · Severity assessment · Test reporting · Comparative analysis · Quality improvement recommendations.

## 8. Limitations and Integrity

- This was a manual assessment, not a source-code audit, security assessment, or formal regulatory certification.
- Nine submissions were blocked from meaningful core-workflow evaluation; two were only partially evaluated.
- The original workbook preserves assessment observations and scores but not a full Pass/Fail matrix for every test case across all 20 applications.
- Some observations do not include original screenshots, exact timestamps, or network traces. They are labelled as source-workbook observations and are not described as independently reproduced.
- Blocked or unverified functionality is not treated as a confirmed functional defect.
- Application identifiers are anonymised. Candidate names, private submission links, and confidential assessment materials are excluded.

**Portfolio status:** The original score sheet and ranking, retrospective application observations, test documentation, and final report are published. Detailed test-case execution records and individual defect tickets remain limited to the evidence available in the original assessment notes.

---

*This repository is an anonymised portfolio case study documenting a manual software quality evaluation exercise.*
