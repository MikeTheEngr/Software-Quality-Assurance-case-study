# Application Ranking
## Truck Trip Planner – Software Quality Assurance Assessment

### 1. Purpose and Source

This is the score-based ranking transcribed from the original **Truck Trip Planner QA Assessment** workbook, specifically the *Final Ranking* and *Master Assessment* sheets. Application identifiers are anonymised. The original category scores and ties are preserved.

### 2. Ranking Method

Each application received five category scores, each out of 5: ELD Accuracy, Other Functional Requirements, UI Aesthetics, UX Intuitiveness, and Bugs & Functionality. The maximum total is 25.

`Percentage = (Total Score ÷ 25) × 100`

Applications are sorted by total score descending. Equal totals share the same rank. The original workbook included blocked and partially evaluated submissions in the ranking using its 1–5 minimum scoring convention. Their status is shown so readers do not mistake an inaccessible workflow for a fully tested product.

### 3. Final Ranking Register

| Rank | Application ID | ELD | Other Functional | UI | UX | Bugs | Total /25 | Percentage | Evaluation status |
|---:|---|---:|---:|---:|---:|---:|---:|---:|---|
| 1 | Application 15 | 4 | 4 | 4 | 4 | 3 | 19 | 76% | Complete |
| 2 | Application 02 | 4 | 4 | 2 | 3 | 4 | 17 | 68% | Complete |
| 2 | Application 16 | 4 | 3 | 4 | 4 | 2 | 17 | 68% | Complete |
| 4 | Application 04 | 3 | 4 | 4 | 3 | 2 | 16 | 64% | Complete |
| 5 | Application 01 | 3 | 3 | 3 | 3 | 3 | 15 | 60% | Complete |
| 6 | Application 12 | 2 | 2 | 4 | 3 | 1 | 12 | 48% | Complete |
| 6 | Application 18 | 1 | 3 | 4 | 3 | 1 | 12 | 48% | Complete |
| 8 | Application 03 | 2 | 2 | 3 | 3 | 1 | 11 | 44% | Complete |
| 9 | Application 11 | 1 | 1 | 4 | 2 | 1 | 9 | 36% | Blocked |
| 9 | Application 19 | 1 | 1 | 4 | 2 | 1 | 9 | 36% | Blocked |
| 11 | Application 14 | 1 | 1 | 4 | 1 | 1 | 8 | 32% | Blocked |
| 12 | Application 05 | 1 | 2 | 2 | 1 | 1 | 7 | 28% | Complete |
| 12 | Application 07 | 1 | 1 | 3 | 1 | 1 | 7 | 28% | Blocked |
| 12 | Application 13 | 1 | 1 | 3 | 1 | 1 | 7 | 28% | Blocked |
| 15 | Application 06 | 1 | 1 | 2 | 1 | 1 | 6 | 24% | Blocked |
| 15 | Application 08 | 1 | 2 | 1 | 1 | 1 | 6 | 24% | Partially Evaluated |
| 15 | Application 17 | 1 | 1 | 2 | 1 | 1 | 6 | 24% | Partially Evaluated |
| 15 | Application 20 | 1 | 1 | 2 | 1 | 1 | 6 | 24% | Blocked |
| 19 | Application 09 | 1 | 1 | 1 | 1 | 1 | 5 | 20% | Blocked |
| 19 | Application 10 | 1 | 1 | 1 | 1 | 1 | 5 | 20% | Blocked |

### 4. Ranking Summary

| Measure | Result |
|---|---:|
| Applications in assessment | 20 |
| Complete | 9 |
| Partially Evaluated | 2 |
| Blocked | 9 |
| Highest score | 19/25 (76%) — Application 15 |
| Lowest score | 5/25 (20%) — Applications 09 and 10 |
| Mean score across all 20 historical scores | 10/25 (40%) |
| Median score | 8.5/25 (34%) |

The mean and median include all 20 historical scores, including blocked and partially evaluated submissions. They are descriptive statistics for the original score sheet, not a pass rate or a measure of quality among fully testable applications only.

### 5. Top Three Score Positions

- **Application 15 — 19/25 (76%):** Strongest observed submission: complete 24-hour logs, cycle recap reconciled with entered 20 hours and planned duty, HOS sequencing and multi-day trip worked, PDF export worked. Fuel stop about 45 miles late; ETA discrepancy about 30 minutes; final off-duty period not clearly shown.
- **Application 02 — 17/25 (68%):** Broad functional coverage: four inputs, optional start time, stops/timings, breaks, fuel, pickup/drop-off, row totals and daily miles. Weak presentation; blank hours/remarks/header fields, unnamed stops, truncated text and nested scrolling.
- **Application 16 — 17/25 (68%):** Correct route and complete 24-hour logs; driving limits, 30-minute breaks, 10-hour resets and cycle calculation verified. Generated dates were June 2025 rather than assessment date in November 2026; no fuel stop on a 1,786-mile trip despite 1,000-mile interval.

Applications 02 and 16 are tied for second place. The detailed strengths and limitations for all applications are recorded in the [Evaluation Scorecard](evaluation-scorecard.md).

### 6. Cross-Submission Findings

The source workbook records recurring concerns across the submissions:

- **ELD/HOS correctness:** incomplete 24-hour accounting, driving-limit and break violations, ignored cycle-hour inputs, and uncertainty around reset or duty-status handling.
- **Trip-input integrity:** some generated schedules did not preserve the submitted locations or trip details.
- **Route and stop planning:** incorrect geocoding, insufficient or late fuel stops, and mislabeled checkpoints.
- **Integration and availability:** DNS, CORS/preflight, HTTP 500, geocoding HTTP 429/502, and authentication capacity issues blocked several workflows.
- **Reporting and consistency:** PDF/on-screen discrepancies, changing mileage, and unclear final off-duty representation.
- **Usability:** blank log fields, unnamed stops, truncated text, nested scrolling, and uneven visual hierarchy.

These themes summarise the actual observations in the source workbook. They do not imply that every application exhibited every issue.

### 7. Evaluation Limitations and Fairness

Nine applications were marked Blocked because a deployment, authentication, API, DNS, geocoding, or backend issue prevented meaningful evaluation of the core workflow. Two were partially evaluated: one produced logs but left key HOS checks unresolved; another was a different type of driver-log product rather than the intended U.S. truck trip planner.

The source workbook applied a minimum score of 1 in each category, even where core functionality could not be accessed. Those original scores are retained for historical accuracy, but blocked results must not be read as proof of defects in unobserved ELD calculations or logs. The status column provides the necessary context.

### 8. Traceability

- [Evaluation Scorecard](evaluation-scorecard.md) — full score register and application-level observations.
- [Functional Test Cases](../test-cases/functional-test-cases.md) — test definitions and expected results.
- [Bug Reports](../bug-reports/bug-reports.md) — defect-reporting process and confirmed issue register.
- [Final QA Report](../final-report/final-qa-report.md) — consolidated assessment conclusions.

### 9. Conclusion

Application 15 achieved the highest recorded score at 19/25 (76%). Applications 02 and 16 tied for second at 17/25 (68%). The ranking reflects the original assessment workbook and should be interpreted alongside the completion status and limitations recorded for each submission.
