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

## 6. Evidence and Reporting Guidelines

- Record the actual observed behaviour, not what the application was expected to do.
- Use screenshots, exported files, or concise observation notes where available and permitted.
- Reference evidence consistently (for example, `APP01-TC005-01` for the first evidence item supporting Application 01, TC-005).
- Mark a case **Blocked** only when execution was attempted and a specific blocker prevented completion. Describe the blocker.
- Mark a case **Fail** only when an observed result contradicts the expected result.
- If a feature is unavailable or not present, describe what was observed and follow the assessment's scoring approach; do not invent a failure condition.
- Keep application identifiers anonymised and exclude private links, candidate identities, credentials, and confidential assessment materials from this public case study.

## 7. Conclusion

These functional test cases provide a repeatable structure for evaluating the Truck Trip Planner applications against the agreed assessment scenario. Once execution records are completed from verified observations, the results can be consolidated into the evaluation scorecard, defect reports, application ranking, and final QA report.
