# Test Execution Dashboard
## Truck Trip Planner – Manual QA Assessment

### Assessment at a Glance

| Measure | Result |
|---|---:|
| Applications reviewed | **20** |
| Evaluation categories | **5** |
| Maximum score per application | **25 points** |
| Complete evaluations | **9 (45%)** |
| Partial evaluations | **2 (10%)** |
| Blocked evaluations | **9 (45%)** |
| Highest recorded score | **19/25 (76%) — Application 15** |
| Second-highest score | **17/25 (68%) — Applications 02 and 16 (tie)** |
| Mean historical score | **10/25 (40%)** |
| Median historical score | **8.5/25 (34%)** |

> **Interpretation note:** The source assessment workbook assigned a minimum score of 1 in each category, including where an application's core workflow was blocked. Historical scores are preserved for traceability. Blocked scores do not demonstrate that inaccessible ELD calculations or trip-planning features were tested and found defective.

### 1. Evaluation Status Distribution

| Status | Applications | Count | Share |
|---|---|---:|---:|
| Complete | 01, 02, 03, 04, 05, 12, 15, 16, 18 | 9 | 45% |
| Partially Evaluated | 08, 17 | 2 | 10% |
| Blocked | 06, 07, 09, 10, 11, 13, 14, 19, 20 | 9 | 45% |
| **Total** | **01–20** | **20** | **100%** |

"Complete" means the main workflow was sufficiently accessible to assess the principal criteria; it does not mean the application passed every test. "Partially Evaluated" means some functionality was exercised but important checks remained unverified or the product did not match the intended scope. "Blocked" means an access, deployment, authentication, API, DNS, or backend issue prevented meaningful evaluation of the core workflow.

### 2. Highest Scoring Applications

| Position | Application | Score | Percentage | Summary |
|---:|---|---:|---:|---|
| 1 | Application 15 | 19/25 | 76% | Strong ELD logs, cycle recap, HOS sequencing, multi-day planning, and PDF export; fuel-stop timing and some ETA/final off-duty presentation concerns remained. |
| 2 (tie) | Application 02 | 17/25 | 68% | Broad functional coverage, with log-field and presentation issues. |
| 2 (tie) | Application 16 | 17/25 | 68% | Route and daily-log behaviour performed well in recorded checks; stale dates and missing fuel stop were noted. |
| 4 | Application 04 | 16/25 | 64% | Professional daily logs, route continuity, stop events, and PDF export; cycle recap and mileage consistency concerns. |
| 5 | Application 01 | 15/25 | 60% | Basic trip-planning foundation; rest breaks, fuel stops, and pickup/drop-off functionality were missing. |

See the [complete application ranking](application-ranking.md) for all 20 score records.

### 3. Key Assessment Findings

The original workbook records the following recurring issue themes:

1. **ELD and HOS accuracy:** incomplete 24-hour logs, driving-limit or break violations, and cycle-hour inputs not reflected in recaps.
2. **Route and location accuracy:** generated routes not matching submitted inputs, incorrect geocoding, and mislabeled checkpoints.
3. **Fuel-stop scheduling:** missing, late, or insufficient fuel stops against the assessment's 1,000-mile interval.
4. **Integration and availability:** DNS resolution, CORS/preflight, HTTP 500/502, geocoding, authentication, and database connectivity blockers.
5. **Output and usability:** PDF/on-screen inconsistencies, stale trip dates, incomplete log fields, and difficult navigation.

These are themes across selected submissions, not claims that every application exhibited every issue. Application-level observations and evidence limitations are documented in the scorecard and bug register.

### 4. Functional Test Coverage Snapshot

The assessment workbook preserves application-level notes and scoring justifications, but it does not contain a full Pass/Fail/Blocked execution matrix for every one of the ten defined test cases across all 20 applications.

| Test case | Area | Retrospective evidence |
|---|---|---|
| TC-001 | Application accessibility | Access, signup, DNS, API, and CORS outcomes recorded for multiple submissions. |
| TC-002 | Input validation | Input reflection and cycle-input observations recorded; systematic invalid-input testing is not fully documented. |
| TC-003 | Route generation | Route mismatches, incorrect geocoding, stale dates, and successful route observations recorded. |
| TC-004 | Pickup/drop-off validation | Missing stop features and incorrect pickup resolution recorded. |
| TC-005 | ELD log generation | Complete, incomplete, absent, and partial log observations recorded. |
| TC-006 | HOS calculations | Driving-limit, break, cycle-hour, reset, and recap observations recorded for selected apps. |
| TC-007 | Rest-break scheduling | Missing breaks and positive HOS sequencing observations recorded for selected apps. |
| TC-008 | Fuel-stop scheduling | Missing, late, insufficient, and available fuel-stop observations recorded. |
| TC-009 | PDF export | Export functionality and an export/on-screen discrepancy recorded for selected apps. |
| TC-010 | Error handling | HTTP, DNS, CORS, authentication, and database failures recorded; systematic error-message testing is incomplete. |

Do not interpret an unmentioned test case as a pass. For blocked applications, downstream cases that require the core workflow are **Blocked / Not Executed**, not Fail.

### 5. Assessment Method

- **Scenario:** Dallas, Texas → Houston, Texas → Los Angeles, California.
- **Initial cycle hours:** 20.
- **Evaluation model:** five categories scored from 1 to 5 (maximum 25).
- **Categories:** ELD Accuracy; Other Functional Requirements; UI Aesthetics; UX Intuitiveness; Bugs & Functionality.
- **Percentage calculation:** (Total Score ÷ 25) × 100.

This was a manual assessment against the stated project criteria. It was not a source-code audit, security review, or formal regulatory certification.

### 6. Related QA Documents

- [QA Test Plan](../test-plan/test-plan.md)
- [Functional Test Cases and Retrospective Execution Summary](../test-cases/functional-test-cases.md)
- [Bug Reports and Assessment Observations](../bug-reports/bug-reports.md)
- [Evaluation Scorecard](evaluation-scorecard.md)
- [Application Ranking](application-ranking.md)
- [Final QA Report](../final-report/final-qa-report.md)
- [Quality Improvement Recommendations](../recommendations/quality-improvement.md)

### 7. Dashboard Maintenance

Update this dashboard only when new source evidence or retest results are available. For each future execution, record the application ID, test case ID, execution date, environment, input data, expected result, actual result, status, evidence reference, and related bug ID. Keep historical assessment observations distinct from later retest results.
