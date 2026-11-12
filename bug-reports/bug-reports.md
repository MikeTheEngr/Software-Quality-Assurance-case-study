# Bug Reports — Truck Trip Planner QA Assessment

## 1. Purpose

This document provides a consistent format for recording, classifying, and tracking defects identified during the Truck Trip Planner assessment.

A bug report should describe a behaviour that was actually observed and can be compared with an expected result. The issues and risk areas listed in this document are investigation prompts based on the assessment scope; they are **not confirmed defects** unless supported by a completed test, observation, and evidence.

## 2. Defect Reporting Principles

Every reported defect should be:

- **Evidence-based:** Record what happened, not what is assumed to have happened.
- **Reproducible where possible:** Include the steps and input data needed to repeat the issue.
- **Specific:** Identify the affected application and feature.
- **Traceable:** Link the report to a functional test case (for example, TC-005).
- **Objective:** Describe expected and actual behaviour without emotional or subjective language.
- **Safe to share:** Use anonymised application identifiers and exclude credentials, private assessment links, candidate identities, and confidential information.

Do not create a defect report solely because a feature is absent from an application. First determine whether the feature was required by the assessment and document the observed behaviour accurately.

## 3. Severity Classification

| Severity | Definition | General example |
|---|---|---|
| Critical | A failure that prevents the core application from being used or makes a central result unusable, with no reasonable workaround. | The application cannot be accessed or the core trip-planning workflow cannot be completed. |
| High | A major functional failure that significantly affects trip planning, ELD/log accuracy, or another essential assessment requirement. | A confirmed material error in driving-time or cycle-hour calculations. |
| Medium | A functional issue that affects part of the workflow or produces an incorrect/incomplete result, but does not completely prevent use. | A generated report omits a relevant trip detail while the main trip remains available. |
| Low | A minor issue with limited functional impact. | A non-critical label, formatting, or feedback issue that causes little disruption. |

**Severity guidance:** Assign severity based on demonstrated impact, not how frequently an issue is mentioned or how difficult it appears to fix. Record priority separately if the assessment process requires it.

## 4. Bug Report Template

Duplicate this template for each confirmed defect.

### BUG-[APP ID]-[NUMBER] — [Short descriptive title]

| Field | Details |
|---|---|
| Bug ID | BUG-[APP ID]-[NUMBER] |
| Application ID | Application [01–20] |
| Related Test Case | TC-XXX |
| Feature / Module | [Affected feature] |
| Date Identified | [YYYY-MM-DD] |
| Environment | [Browser, device, or environment, if known] |
| Severity | [Critical / High / Medium / Low] |
| Status | [New / Under Review / Retest Required / Closed] |

**Summary**  
[One or two sentences describing the observed defect.]

**Preconditions**  
[State the application state and any required setup.]

**Steps to Reproduce**
1. [First action]
2. [Second action]
3. [Third action]
4. [Continue as needed]

**Test Data**  
[Record the relevant input values. Do not include secrets or personal information.]

**Expected Result**  
[Describe what should happen according to the assessment requirement.]

**Actual Result**  
[Describe exactly what happened during the test.]

**Impact**  
[Explain how the observed behaviour affects the user or assessment requirement.]

**Reproducibility**  
[Consistent / Intermittent / Unable to Reproduce / Not Retested]

**Evidence**  
[Reference screenshot, recording, exported file, or observation note. Example: APP01-TC005-01.]

**Additional Notes**  
[Relevant context, workaround if observed, or retest information.]

---

## 5. Defect Register

Only add an entry after the issue has been observed and supported by evidence. Use one row per distinct defect.

| Bug ID | Application ID | Related Test Case | Short Description | Severity | Status | Evidence Reference |
|---|---|---|---|---|---|---|
| — | — | — | No confirmed defects recorded in this register yet. | — | — | — |

The register is intentionally empty until verified defects are documented.

## 6. Assessment Areas to Investigate

The following areas reflect risks within the assessment scope and previously noted areas of concern. They are **not defect findings by themselves**. Execute the relevant test case and capture evidence before creating a bug report.

| Investigation Area | What to Verify | Related Test Cases |
|---|---|---|
| ELD log completeness | Whether each displayed daily log accounts for the full 24-hour period and whether gaps or overlaps are present. | TC-005 |
| HOS calculations | Whether driving limits, duty windows, breaks, resets, and cycle-hour calculations are applied consistently. | TC-006 |
| Input handling | Whether submitted values are validated and retained in the generated trip. | TC-002, TC-004 |
| Fuel-stop scheduling | Whether fuel stops follow the assessment interval and appear in the trip plan. | TC-008 |
| Route and location accuracy | Whether the route follows the requested origin, intermediate stop, and destination. | TC-003, TC-004 |
| Backend or service failures | Whether a failed request prevents a feature from working and whether the application provides useful feedback. | TC-001, TC-010 |
| PDF and on-screen consistency | Whether exported trip and log information matches the information displayed in the application. | TC-009 |
| Error handling | Whether invalid input and failed operations are handled without crashes or misleading success messages. | TC-002, TC-010 |

## 7. Defect Lifecycle

1. **Identify:** Observe unexpected behaviour while executing a test case.
2. **Capture:** Record the actual result and collect supporting evidence.
3. **Validate:** Compare the observation with the expected result and confirm that the requirement applies.
4. **Document:** Create a bug report using the template and assign a severity based on impact.
5. **Track:** Add the confirmed issue to the defect register.
6. **Retest:** If a correction is made and retesting is within scope, repeat the relevant steps and record the outcome.
7. **Close or Reopen:** Close only when the issue is verified as resolved; otherwise retain or reopen the report with updated evidence.

This case study records the tester's assessment findings. It does not imply that the development teams received, accepted, or resolved the reported issues unless that is independently documented.

## 8. Conclusion

A structured defect log makes QA findings clear, traceable, and useful to developers and stakeholders. This document will be populated as test execution evidence is reviewed, ensuring that every published defect is tied to an observed result and a relevant assessment requirement.
