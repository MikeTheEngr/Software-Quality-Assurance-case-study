# Functional Test Cases — Truck Trip Planner

## 1. Purpose

This document defines the functional test cases for the Truck Trip Planner assessment. It translates the scope and checks in the [test plan](../test-plan/test-plan.md) into repeatable test procedures.

The assessment covers route planning from Dallas, Texas, through Houston, Texas, to Los Angeles, California, using an initial cycle-hours value of 20. The same baseline scenario should be used consistently when comparing applications.

> **Execution note:** These are test-case definitions, not completed test results. Record actual outcomes only when supported by assessment observations or evidence. Do not infer a pass, failure, or defect from an untested feature.

## 2. Standard Test Data

| Field | Baseline value |
|---|---|
| Starting location | Dallas, Texas |
| Intermediate stop | Houston, Texas |
| Destination | Los Angeles, California |
| Initial cycle hours | 20 |
| Trip type | Multi-stop truck trip |
| Fuel-stop assessment interval | Every 1,000 miles, as specified in the assessment |
| Log review period | 24-hour daily ELD log |

Use the same inputs across applications wherever the interface permits. If an application requires additional data, record the values entered so the test can be repeated.

## 3. Test Case Status Definitions

- **Pass:** The observed result meets the expected result.
- **Fail:** The observed result does not meet the expected result.
- **Blocked:** The test was attempted but could not be completed because of an access, environment, or dependency issue.
- **Not Tested:** The test has not yet been executed.

## 4. Functional Test Cases

### TC-001 — Application Accessibility

| Attribute | Details |
|---|---|
| Test Case ID | TC-001 |
| Test Scenario | Verify that the application can be opened and its primary interface is accessible. |
| Preconditions | Application URL or launch instructions are available; a supported browser and internet connection are available. |
| Test Steps | 1. Open the application URL. 2. Wait for the page to load. 3. Observe whether the primary interface and key controls are displayed. 4. If a login or access prompt appears, follow only the assessment-provided access instructions. |
| Expected Result | The application loads successfully and presents a usable interface, or clearly communicates any required access step. |
| Actual Result | To be recorded from assessment evidence. |
| Status | Not Tested |

### TC-002 — Trip Input Validation

| Attribute | Details |
|---|---|
| Test Case ID | TC-002 |
| Test Scenario | Verify that the application accepts the required trip information and handles missing or invalid inputs. |
| Preconditions | Application is accessible and the trip-planning form is available. |
| Test Steps | 1. Enter Dallas, Texas as the starting location. 2. Enter Houston, Texas as the intermediate stop. 3. Enter Los Angeles, California as the destination. 4. Enter 20 as the initial cycle-hours value. 5. Submit or generate the trip. 6. Where practical, repeat with a required field omitted or an invalid value entered. |
| Expected Result | Valid inputs are accepted and used to generate the trip. Missing or invalid required inputs are identified with clear guidance rather than silently accepted. |
| Actual Result | To be recorded from assessment evidence. |
| Status | Not Tested |

### TC-003 — Route Generation

| Attribute | Details |
|---|---|
| Test Case ID | TC-003 |
| Test Scenario | Verify that the application generates a route that follows the entered stop sequence. |
| Preconditions | Valid baseline trip details have been entered. |
| Test Steps | 1. Generate the trip route. 2. Review the displayed route or map. 3. Confirm that Dallas is the origin, Houston is included as the intermediate stop, and Los Angeles is the destination. 4. Review any displayed distance, travel-time, or location details. |
| Expected Result | The generated route reflects the supplied origin, intermediate stop, and destination in the correct sequence. Route details are displayed consistently with the generated trip. |
| Actual Result | To be recorded from assessment evidence. |
| Status | Not Tested |

### TC-004 — Pickup and Drop-off Validation

| Attribute | Details |
|---|---|
| Test Case ID | TC-004 |
| Test Scenario | Verify that pickup, intermediate, and drop-off locations are represented correctly in the trip. |
| Preconditions | The trip input form or generated trip details support stop or pickup/drop-off information. |
| Test Steps | 1. Enter or review the pickup location in Dallas. 2. Enter or review the intermediate stop in Houston. 3. Enter or review the final drop-off location in Los Angeles. 4. Generate or inspect the trip summary. 5. Check that the locations and their sequence are retained. |
| Expected Result | The trip summary correctly represents the supplied locations and does not omit, replace, or reorder them unexpectedly. |
| Actual Result | To be recorded from assessment evidence. |
| Status | Not Tested |

### TC-005 — ELD Log Generation

| Attribute | Details |
|---|---|
| Test Case ID | TC-005 |
| Test Scenario | Verify that the application generates ELD-style daily logs for the planned trip. |
| Preconditions | A valid trip has been generated and the application provides an ELD/log view. |
| Test Steps | 1. Open the ELD or driver-log section. 2. Review the generated daily log entries. 3. Check whether the log represents the trip activities and duty-status periods. 4. Review the full 24-hour period for each displayed day. 5. Note missing time periods, gaps, overlaps, or inconsistencies. |
| Expected Result | Daily logs are generated and present a coherent 24-hour record for each displayed day, with trip activities represented consistently. |
| Actual Result | To be recorded from assessment evidence. |
| Status | Not Tested |

### TC-006 — Hours of Service (HOS) Calculations

| Attribute | Details |
|---|---|
| Test Case ID | TC-006 |
| Test Scenario | Check whether the application's driving, duty-window, break, reset, and cycle-hour calculations align with the assessment criteria. |
| Preconditions | Trip details and initial cycle hours have been entered; HOS or log calculations are available for review. |
| Test Steps | 1. Confirm that the initial cycle-hours value is 20. 2. Review the displayed driving-time calculations. 3. Check the 11-hour driving limit. 4. Check the 14-hour duty-window calculation. 5. Check the 30-minute break requirement. 6. Check the 10-hour off-duty reset treatment. 7. Review how cycle hours are calculated and updated. 8. Record any calculation that is missing, inconsistent, or unsupported by the displayed schedule. |
| Expected Result | The application applies the assessment's HOS checks consistently: 11-hour driving limit, 14-hour duty window, 30-minute break, 10-hour off-duty reset, and accurate cycle-hour tracking. |
| Actual Result | To be recorded from assessment evidence. |
| Status | Not Tested |

> These checks are assessment criteria and do not constitute legal or regulatory certification of an ELD product.

### TC-007 — Rest-Break Scheduling

| Attribute | Details |
|---|---|
| Test Case ID | TC-007 |
| Test Scenario | Verify that required rest breaks are scheduled and reflected in the trip timeline. |
| Preconditions | A trip has been generated and the application supports rest-break or stop scheduling. |
| Test Steps | 1. Review the proposed driving schedule. 2. Identify where the 30-minute break is scheduled. 3. Check whether the break is placed at an appropriate point in the driving timeline. 4. Review any longer off-duty reset shown in the schedule. 5. Compare the schedule with the displayed HOS calculations. |
| Expected Result | Required breaks and off-duty periods are represented in the schedule and are consistent with the application's HOS calculations. |
| Actual Result | To be recorded from assessment evidence. |
| Status | Not Tested |

### TC-008 — Fuel-Stop Scheduling

| Attribute | Details |
|---|---|
| Test Case ID | TC-008 |
| Test Scenario | Verify that fuel stops are scheduled according to the assessment's 1,000-mile interval. |
| Preconditions | A route has been generated and the application provides fuel-stop planning or recommendations. |
| Test Steps | 1. Review the total route distance, if available. 2. Review the proposed fuel stops. 3. Check the distance between consecutive fuel stops against the 1,000-mile assessment interval. 4. Check whether fuel stops are included in the trip timeline or route summary. 5. Record any missing, duplicated, or incorrectly positioned stops. |
| Expected Result | Fuel stops are scheduled at intervals consistent with the 1,000-mile assessment criterion and are reflected in the trip plan. |
| Actual Result | To be recorded from assessment evidence. |
| Status | Not Tested |

### TC-009 — PDF Export Validation

| Attribute | Details |
|---|---|
| Test Case ID | TC-009 |
| Test Scenario | Verify that the trip plan or ELD information can be exported to PDF and that the exported content matches the on-screen information. |
| Preconditions | A trip has been generated and a PDF export or download option is available. |
| Test Steps | 1. Locate the export or download option. 2. Export the available trip plan or logs to PDF. 3. Open the downloaded file. 4. Check that the file opens and that its pages are readable. 5. Compare key trip details and log information in the PDF with the on-screen version. 6. Note missing, truncated, or inconsistent content. |
| Expected Result | The PDF is generated successfully, opens correctly, is readable, and accurately represents the relevant on-screen trip and log information. |
| Actual Result | To be recorded from assessment evidence. |
| Status | Not Tested |

### TC-010 — Error Handling and Input Feedback

| Attribute | Details |
|---|---|
| Test Case ID | TC-010 |
| Test Scenario | Verify that the application responds clearly to invalid input, unavailable data, and failed operations. |
| Preconditions | Application is accessible and the relevant form or feature can be exercised safely. |
| Test Steps | 1. Submit a form with a required field missing, where practical. 2. Enter an invalid value in a field that supports validation. 3. Where an operation fails naturally during assessment, observe the feedback shown. 4. Check whether the application identifies the issue and provides a useful next step. 5. Note crashes, blank screens, unhandled errors, or misleading success messages. |
| Expected Result | The application handles invalid input and failed operations gracefully, provides understandable feedback, and does not misrepresent an unsuccessful operation as successful. |
| Actual Result | To be recorded from assessment evidence. |
| Status | Not Tested |

## 5. Execution Record

Use one execution record per application. Duplicate the template for Applications 02–20 and retain the same test case IDs to support comparison.

### Application 01

| Test Case ID | Actual Result / Evidence Summary | Status | Evidence Reference / Notes |
|---|---|---|---|
| TC-001 | To be recorded | Not Tested | |
| TC-002 | To be recorded | Not Tested | |
| TC-003 | To be recorded | Not Tested | |
| TC-004 | To be recorded | Not Tested | |
| TC-005 | To be recorded | Not Tested | |
| TC-006 | To be recorded | Not Tested | |
| TC-007 | To be recorded | Not Tested | |
| TC-008 | To be recorded | Not Tested | |
| TC-009 | To be recorded | Not Tested | |
| TC-010 | To be recorded | Not Tested | |

**Application URL / identifier:** To be recorded  
**Date tested:** To be recorded  
**Browser / environment:** To be recorded  
**Tester notes:** To be recorded


## 6. Retrospective Execution Summary — Original Assessment Evidence

The original assessment workbook contains application-level observations and scoring justifications. It does **not** contain a complete ten-test-case-by-twenty-application execution matrix, nor does it preserve a pass/fail result for every individual test. The table below therefore records only outcomes explicitly supported by the workbook. It is a retrospective evidence summary, not a claim that every test case was separately executed.

### 6.1 Application-level execution evidence

| Application | Access / execution outcome | Test cases with recorded evidence | Retrospective result summary |
|---|---|---|---|
| 01 — Fless Lab | Core workflow accessible | TC-003, TC-005, TC-007, TC-008, TC-004 | Basic logs and map were present. Rest breaks, fuel stops, and pickup/drop-off activities were recorded as missing. |
| 02 — Taha Meskini | Core workflow accessible | TC-002, TC-004, TC-005, TC-007, TC-008 | Broad trip and stop functionality was observed. Log fields, stop labels, and presentation issues were recorded. |
| 03 — okaycodes (identity unverified) | Schedule generated | TC-002, TC-003, TC-004, TC-005, TC-006 | Generated schedule did not reflect submitted trip inputs; stop markers/list and start date were absent. |
| 04 — Hannah Mariel Tamayo | Core workflow accessible | TC-003, TC-005, TC-006, TC-009 | Route continuity, daily logs, stop events, and PDF export were observed. Cycle recap did not reflect entered 20 hours; mileage varied between comparable runs. |
| 05 — Derek | Core workflow accessible; major output concerns | TC-005, TC-006, TC-007, TC-009, TC-003 | Incomplete daily accounting, HOS/break violations, ignored cycle input, incomplete trip, and PDF/on-screen inconsistencies were recorded. |
| 06 — TruckTrack | Blocked by backend DNS failure | TC-001, TC-002 | U.S. locations and core planning workflow could not be used; route, map, stops, and ELD outputs unavailable. |
| 07 — RouteRest | Blocked by CORS/preflight failure | TC-001, TC-002 | Frontend/backend integration prevented route, itinerary, and ELD output generation. |
| 08 — Fedhako7 | Partially accessible after cache clear | TC-001, TC-005, TC-006 | Logs were generated after initial HTTP 429/500 errors. Day 1 and Day 2 accounted for 23 and 22 hours; other HOS checks remained unverified. |
| 09 — Outbound Spotter | Blocked at registration | TC-001 | Registration could not proceed because the Clerk development instance had reached its user limit. Core workflow not tested. |
| 10 — FantaJinMode | Blocked by HTTP 500 during trip submission | TC-001, TC-002 | No route, map, stops, or ELD logs were generated. |
| 11 — Najma099 | Blocked by database-hostname resolution failure | TC-001, TC-002 | Form/interface was accessible, but planning failed; no route, map, stops, or logs were generated. |
| 12 — Jerome Balagtas | Core workflow accessible | TC-003, TC-004, TC-005, TC-006, TC-007, TC-008 | Complete 24-hour logs and map were observed. Pickup resolved to Austin instead of Houston; cycle input was ignored; breaks were missing on Days 1 and 2; fuel stop was late. |
| 13 — Royweru | Blocked at signup by CORS failure | TC-001 | Planner and ELD outputs could not be accessed. Login was not confirmed tested. |
| 14 — Schneider One | Blocked by trip-planning API HTTP 500 | TC-001, TC-002 | No route, map, stops, or ELD logs were generated. |
| 15 — Boredoom17 | Core workflow accessible | TC-003, TC-005, TC-006, TC-007, TC-008, TC-009 | Complete daily logs, cycle recap, HOS sequencing, multi-day trip, and PDF export were observed. Fuel stop was approximately 45 miles late; ETA differed by about 30 minutes; final off-duty period was unclear. |
| 16 — esa-yas | Core workflow accessible | TC-003, TC-005, TC-006, TC-007, TC-008 | Route and complete logs were observed; driving limits, breaks, resets, and cycle calculation were recorded as verified. Generated dates were stale and fuel stop was missing on a 1,786-mile trip. |
| 17 — Truck Driver Log | Accessible, but product scope mismatch | TC-001 (scope review) | European manual driver-log application rather than the intended U.S. truck trip planner. U.S. route and ELD test cases were not applicable / not executed. |
| 18 — Truck Trip Planner Engine | Core workflow accessible | TC-003, TC-004, TC-005, TC-006, TC-008 | Route/map and three-day itinerary were observed. Driving exceeded 11 hours on Days 2 and 3; cycle input appeared ignored; fuel stops were insufficient; checkpoints were mislabeled. |
| 19 — ELD Trip Planner | Blocked by Dallas geocoding HTTP 502 | TC-001, TC-002 | Form was accessible, but route, map, stops, and ELD logs were not generated. |
| 20 — Spotter FullStack Assignment | Blocked by CORS/preflight failure | TC-001, TC-002 | Frontend loaded, but trip API request failed; no trip, route, map, stops, or ELD logs were generated. |

### 6.2 Test-case outcome interpretation

| Test case | What the source workbook supports | Retrospective interpretation |
|---|---|---|
| TC-001 Accessibility | Multiple explicit access, signup, DNS, API, and CORS blockers; some applications' workflows were accessible. | Record as accessible, blocked, or scope-mismatched only where the application notes support it. |
| TC-002 Input validation | Input reflection/cycle-input issues and blocked submissions are noted; systematic invalid/empty-field testing is not recorded. | Partial evidence only; do not claim comprehensive validation testing. |
| TC-003 Route generation | Incorrect trip output, wrong pickup geocoding, stale dates, route availability and successful route observations are recorded. | Mixed outcomes; exact route pass/fail details are not available for every application. |
| TC-004 Pickup/drop-off | Missing pickup/drop-off functionality, wrong pickup resolution, and some correct stop/route observations are recorded. | Partial evidence; no complete per-application stop checklist survives in the workbook. |
| TC-005 ELD log generation | Complete, incomplete, absent, and partial daily-log observations are recorded. | Results vary by application; absent logs on blocked apps are not functional ELD failures. |
| TC-006 HOS calculations | Explicit driving-limit, break, cycle-hour, reset, and recap observations are recorded for selected applications. | Failures and successful checks can be attributed only where stated in the source notes. |
| TC-007 Rest-break scheduling | Missing breaks on some accessible applications and working HOS sequencing/break observations on others are recorded. | Partial cross-application evidence; do not infer results for unmentioned apps. |
| TC-008 Fuel-stop scheduling | Missing, late, insufficient, and successful/available fuel-stop observations are recorded. | Outcomes are documented only for applications with explicit notes. |
| TC-009 PDF export | Export worked for some accessible applications and was inconsistent for another. | No evidence that PDF export was available or tested in every application. |
| TC-010 Error handling | HTTP 429, 500, 502, DNS, CORS, authentication, and database errors were observed. | Technical failure evidence exists; systematic invalid-input and graceful-error-message testing is not fully documented. |

### 6.3 Evidence limitations

- The original workbook is the source for the retrospective observations and category scores.
- It does not preserve a separate execution timestamp, browser/version, screenshot ID, or full step-by-step result for every test case.
- The status of an individual test case is not inferred from the application's overall score.
- Where a core workflow was blocked, downstream route, ELD, HOS, fuel, and PDF cases are treated as **Blocked / Not Executed**, not Fail.
- Where the workbook records an observed result but no raw screenshot or export, this document labels it as an assessment observation and does not claim attached evidence.
- A future retest should record the actual test date, environment, inputs, expected result, actual result, status, and evidence filename for every executed test.

## 7. Updated Execution Record Template

Use this record for future retesting or when original supporting evidence becomes available.

| Field | Record |
|---|---|
| Application ID | |
| Test Case ID | |
| Test date and time | |
| Tester | |
| Browser / environment | |
| Input data | |
| Expected result | |
| Actual result | |
| Status (Pass / Fail / Blocked / Not Tested) | |
| Evidence reference | |
| Related bug ID | |
| Retest result | |

## 8. Evidence and Reporting Guidelines

- Record the actual observed behaviour, not what the application was expected to do.
- Use screenshots, exported files, or concise observation notes where available and permitted.
- Reference evidence consistently (for example, `APP01-TC005-01` for the first evidence item supporting Application 01, TC-005).
- Mark a case **Blocked** only when execution was attempted and a specific blocker prevented completion. Describe the blocker.
- Mark a case **Fail** only when an observed result contradicts the expected result.
- If a feature is unavailable or not present, describe what was observed and follow the assessment's scoring approach; do not invent a failure condition.
- Keep application identifiers anonymised and exclude private links, candidate identities, credentials, and confidential assessment materials from this public case study.

## 9. Conclusion

These functional test cases provide a repeatable structure for evaluating the Truck Trip Planner applications against the agreed assessment scenario. Once execution records are completed from verified observations, the results can be consolidated into the evaluation scorecard, defect reports, application ranking, and final QA report.
