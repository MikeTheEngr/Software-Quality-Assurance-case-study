# Software Quality Assurance Case Study
## Truck Trip Planner – Functional, ELD Compliance & UI/UX Evaluation

### Project Overview

This project documents a manual Quality Assurance (QA) evaluation of 20 independently developed Truck Trip Planner applications.

The objective was to assess application functionality, Electronic Logging Device (ELD) accuracy, user interface design, user experience, and overall software reliability against defined requirements.

The assessment involved hands-on application evaluation, review of functional behaviour and ELD/HOS outputs, documentation of observed quality concerns, and preparation of a standardised scoring and reporting framework. The original per-application scores and detailed evidence have not yet been transferred into this public portfolio.

### Project Objectives

- Evaluate application functionality against specified requirements.
- Assess ELD logs and Hours of Service (HOS) calculations.
- Verify route planning, stops, rest periods and fuel scheduling.
- Evaluate interface design and user experience.
- Identify functional defects, inconsistencies and usability issues.
- Establish a standardised framework for scoring and ranking applications; publish comparative results only after the original scores are verified.
- Provide recommendations for improving software quality.

### Testing Scope

The assessment covered the following areas:

| Testing Area | Evaluation Focus |
|---|---|
| Functional Testing | Required inputs, trip generation, route planning and expected outputs |
| ELD Accuracy | Daily logs, driving hours, rest periods and cycle calculations |
| UI Testing | Layout, visual presentation and information organisation |
| UX Testing | Navigation, usability, accessibility and ease of interaction |
| Defect Identification | Functional errors, inconsistencies and application failures |

### Test Scenario

A standardised test scenario was used to evaluate the applications consistently.

**Route:** Dallas → Houston → Los Angeles  
**Initial Cycle Hours:** 20 hours

The assessment examined whether applications could generate appropriate routes, stops, rest periods and multi-day ELD logs based on the supplied inputs.

### QA Evaluation Methodology

Each application was evaluated across five categories using a scoring scale of 1–5.

| Score | Classification |
|---|---|
| 1 | Poor / Blocked |
| 2 | Below Average |
| 3 | Average |
| 4 | Good |
| 5 | Excellent |

Each category contributed equally to the final score.

**Maximum score:** 25 points.

**Percentage calculation:** (Total Score ÷ 25) × 100.

Applications that could not be accessed or whose core functionality was blocked were to be documented accordingly. In such cases, inaccessible functionality is classified as unverified rather than assumed to be defective. The repository currently contains the scoring and ranking templates; verified individual scores and final rankings remain pending.

### Key QA Activities

- Manual functional evaluation of 20 applications.
- Verification of trip inputs and generated outputs.
- Review of ELD daily logs and HOS calculations.
- Assessment of route accuracy and stop scheduling.
- Identification of frontend and backend integration issues.
- Documentation of usability and interface problems.
- Comparative scoring and application ranking.
- Preparation of quality improvement recommendations.

### Key Findings

The assessment identified recurring quality concerns, including:

- Incomplete or inconsistent 24-hour ELD logs.
- Incorrect driving-hour and rest-break calculations.
- User inputs not properly reflected in generated schedules.
- Missing or incorrectly scheduled fuel stops.
- Route and geolocation inaccuracies.
- Backend API and CORS integration failures.
- Authentication and deployment accessibility issues.
- Inconsistencies between on-screen results and exported PDF reports.
- Poor error handling and unclear user feedback.

### Deliverables

The project documentation is organised into:

- Test plan and testing scope.
- Functional test cases.
- Defect and observation reports.
- QA evaluation scorecard.
- Comparative assessment results.
- Quality improvement recommendations.

### Documentation Guide

| Document | Purpose |
|---|---|
| [QA Test Plan](test-plan/test-plan.md) | Defines the assessment scope, scenario, approach, and evaluation criteria. |
| [Functional Test Cases](test-cases/functional-test-cases.md) | Provides repeatable test steps and expected results for the core workflows. |
| [Bug Reports](bug-reports/bug-reports.md) | Provides the defect-reporting template and observation register. |
| [Evaluation Scorecard](test-results/evaluation-scorecard.md) | Defines the five-category scoring rubric and per-application score register. |
| [Application Ranking](test-results/application-ranking.md) | Provides the methodology and register for verified comparative results. |
| [Final QA Report](final-report/final-qa-report.md) | Consolidates the assessment approach, findings, limitations, and pending quantitative results. |
| [Quality Improvement Recommendations](recommendations/quality-improvement.md) | Outlines engineering improvements linked to the assessment themes. |

**Portfolio status:** The documentation framework is published. The original score sheet and application-level evidence still need to be entered and verified before final scores, averages, or rankings can be reported.

### Skills Demonstrated

Manual Software Testing | Functional Testing | UI/UX Testing | Defect Identification | Test Documentation | Quality Evaluation | Analytical Thinking | Technical Reporting

### Important Note

This is an anonymised portfolio case study based on a completed software evaluation exercise. Candidate identities, private submission links and confidential assessment materials are excluded.
