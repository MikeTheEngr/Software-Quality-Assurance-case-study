# Bug Reports and Assessment Observations
## Truck Trip Planner – Manual QA Assessment

### 1. Purpose and Evidence Basis

This register captures issues and execution blockers recorded in the original **Truck Trip Planner QA Assessment** workbook, primarily the *Individual QA Analysis* sheet. Application identifiers are anonymised and correspond to the candidate numbers in the scorecard and ranking.

The source workbook contains tester notes and score justifications, not a complete set of timestamped screenshots, screen recordings, HTTP traces, or independently repeatable bug tickets. Accordingly:

- The entries below are **assessment observations transcribed from the source workbook**.
- Reproduction steps are expressed as a concise retest path based on the standard assessment scenario; they are not represented as a verbatim historical click-by-click record.
- The source workbook observation is cited for traceability. No screenshot or network-log attachment is claimed where none was supplied.
- For blocked applications, the register records an observed access/integration failure, not an assumed defect in unobserved ELD or trip-planning logic.
- Severity is an assessment of observed user impact, not a confirmed root-cause diagnosis or a developer-assigned priority.

### 2. Severity Classification

| Severity | Definition |
|---|---|
| Critical | Core workflow cannot be completed, or a central result is materially unsafe/unusable against the assessment criteria. |
| High | A major trip-planning or HOS requirement is violated or materially incorrect. |
| Medium | A material supporting feature or output is incomplete/inconsistent, but the main workflow remains usable. |
| Low | A minor presentation, usability, or feedback issue with limited functional impact. |

### 3. Confirmed Functional / Output Observations

These records are based on behaviour explicitly described as observed in the source workbook. They are not claims that the underlying cause has been identified.

#### BUG-APP01-001 — Required trip-planning features are missing

| Field | Details |
|---|---|
| Application ID | Application 01 |
| Related Test Cases | TC-007, TC-008, TC-004 |
| Severity | High |
| Status | Observed — retest not recorded |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #1 (Fless Lab) |

**Summary:** The application provided basic inputs, ELD logs, and a map, but the assessment notes recorded missing rest breaks, fuel stops, and pickup/drop-off activities.

**Retest path:** Enter the standard Dallas → Houston → Los Angeles trip and inspect the generated itinerary, duty timeline, pickup/drop-off events, and fuel/rest-stop schedule.

**Expected:** Required trip events, rest periods, and fuel stops should be represented in the generated plan according to the assessment requirements.

**Observed:** The assessment notes recorded that these features were missing. The exact individual controls and output screenshots were not preserved in the workbook.

#### BUG-APP02-001 — ELD log fields and stop labels are incomplete

| Field | Details |
|---|---|
| Application ID | Application 02 |
| Related Test Cases | TC-005, TC-009 |
| Severity | Medium |
| Status | Observed — retest not recorded |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #2 (Taha Meskini) |

**Summary:** The assessment notes recorded blank hours, remarks, and header fields, unnamed stops, truncated text, and nested scrolling in the log presentation.

**Retest path:** Generate the standard trip, inspect each daily log and stop entry, then review the layout at the same viewport.

**Expected:** Log fields should be populated where applicable, stops should be identifiable, text should remain readable, and the log should be navigable without avoidable nested scrolling.

**Observed:** Blank fields, unnamed stops, truncated text, and nested scrolling were recorded.

#### BUG-APP03-001 — Generated schedule does not reflect submitted trip inputs

| Field | Details |
|---|---|
| Application ID | Application 03 |
| Related Test Cases | TC-002, TC-003, TC-004 |
| Severity | Critical |
| Status | Observed — retest not recorded |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #3 (okaycodes; personal name not verified) |

**Summary:** The generated schedule did not correspond to the submitted trip. The notes also recorded that inputs were not reflected and that stop markers, a stops list, and a start date were absent.

**Retest path:** Submit Dallas, Houston, and Los Angeles with the standard cycle input; generate the schedule and compare every displayed route and trip detail with the submitted values.

**Expected:** The generated schedule should preserve the submitted origin, intermediate stop, destination, and applicable trip details, with clear stop information and a trip date.

**Observed:** The generated schedule did not correspond to the submitted trip; the specified stop/date information was not displayed.

#### BUG-APP04-001 — Entered cycle hours are not reflected in recap

| Field | Details |
|---|---|
| Application ID | Application 04 |
| Related Test Cases | TC-005, TC-006 |
| Severity | High |
| Status | Observed — retest not recorded |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #4 (Hannah Mariel Tamayo) |

**Summary:** The selected 20-hour cycle input was not reflected in the recap/availability information.

**Retest path:** Enter the standard trip and 20 prior cycle hours, generate the plan, and compare the entered value with the cycle recap and remaining availability.

**Expected:** The recap and available cycle hours should account for the entered prior-cycle value and planned duty.

**Observed:** The assessment notes recorded that the selected 20-hour cycle was not reflected in the recap/availability.

#### BUG-APP04-002 — Mileage changes between comparable generated runs

| Field | Details |
|---|---|
| Application ID | Application 04 |
| Related Test Cases | TC-003, TC-010 |
| Severity | Medium |
| Status | Observed — root cause unknown |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #4 (Hannah Mariel Tamayo) |

**Summary:** Mileage changed between comparable runs of the trip.

**Retest path:** Repeat the same trip inputs under the same conditions and compare the reported route distance and itinerary mileage.

**Expected:** Equivalent inputs and routing conditions should produce consistent mileage, or the application should explain a route change.

**Observed:** The assessment notes recorded changing mileage between comparable runs. The workbook does not preserve the individual values or establish the cause.

#### BUG-APP05-001 — ELD daily logs do not account for a complete 24-hour period

| Field | Details |
|---|---|
| Application ID | Application 05 |
| Related Test Cases | TC-005 |
| Severity | High |
| Status | Observed — retest not recorded |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #5 (Derek) |

**Summary:** The assessment recorded incomplete 24-hour accounting in the generated ELD logs.

**Retest path:** Generate the standard multi-day trip and total the displayed duty-status intervals for each day.

**Expected:** Each daily log should account for the full 24-hour period without unexplained gaps or overlaps.

**Observed:** The source notes described incomplete 24-hour accounting. Exact interval values were not preserved.

#### BUG-APP05-002 — Driving-limit and rest-break requirements are violated

| Field | Details |
|---|---|
| Application ID | Application 05 |
| Related Test Cases | TC-006, TC-007 |
| Severity | Critical |
| Status | Observed — retest not recorded |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #5 (Derek) |

**Summary:** The assessment notes recorded driving-limit and break violations in the generated schedule.

**Retest path:** Generate the standard trip and compare the duty timeline with the assessment's driving-limit and break criteria.

**Expected:** The schedule should respect the applicable driving limit and required break placement.

**Observed:** Driving-limit and break violations were recorded. The workbook does not include the exact timestamps needed to reproduce each violation.

#### BUG-APP05-003 — Entered cycle-hour value is ignored

| Field | Details |
|---|---|
| Application ID | Application 05 |
| Related Test Cases | TC-002, TC-006 |
| Severity | High |
| Status | Observed — retest not recorded |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #5 (Derek) |

**Summary:** The application did not incorporate the entered cycle-hour input into its calculations.

**Retest path:** Enter the standard trip and 20 prior cycle hours, generate the plan, and inspect the cycle recap and remaining availability.

**Expected:** The entered cycle-hour value should be incorporated into the calculation.

**Observed:** The source workbook states that the cycle input was ignored.

#### BUG-APP05-004 — Exported PDF does not match on-screen trip schedule

| Field | Details |
|---|---|
| Application ID | Application 05 |
| Related Test Cases | TC-009 |
| Severity | High |
| Status | Observed — retest not recorded |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #5 (Derek) |

**Summary:** The PDF export and on-screen schedule contained inconsistencies.

**Retest path:** Generate the standard trip, record the visible schedule, export the PDF, and compare dates, trip events, and duty-status information.

**Expected:** Exported information should match the corresponding on-screen plan.

**Observed:** The assessment recorded inconsistencies between the PDF and on-screen schedule. The exact differing fields were not preserved.

#### BUG-APP08-001 — Generated daily logs do not account for 24 hours

| Field | Details |
|---|---|
| Application ID | Application 08 |
| Related Test Cases | TC-005, TC-006 |
| Severity | High |
| Status | Observed — retest required |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #8 (Fedhako7) |

**Summary:** After the application generated logs, the assessment recorded that Day 1 accounted for 23 hours and Day 2 for 22 hours.

**Retest path:** Repeat the same trip after ensuring the planner has generated logs, then total all duty-status intervals for Days 1 and 2.

**Expected:** Each daily log should account for 24 hours.

**Observed:** The recorded totals were 23 hours on Day 1 and 22 hours on Day 2. Break/reset/14-hour compliance and the recap could not be fully verified; sleeper-berth status was unclear.

#### BUG-APP12-001 — Pickup location resolves to the wrong city

| Field | Details |
|---|---|
| Application ID | Application 12 |
| Related Test Cases | TC-003, TC-004 |
| Severity | High |
| Status | Observed — retest not recorded |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #12 (Jerome Balagtas) |

**Summary:** The requested Houston pickup resolved to Huston-Tillotson University in Austin, Texas.

**Retest path:** Enter Houston, Texas as the pickup/intermediate location and inspect the resolved location, route marker, and generated itinerary.

**Expected:** The planner should resolve the intended Houston, Texas location, not a similarly named place in Austin.

**Observed:** The pickup resolved to Huston-Tillotson University in Austin.

#### BUG-APP12-002 — Prior cycle hours are omitted from recap

| Field | Details |
|---|---|
| Application ID | Application 12 |
| Related Test Cases | TC-002, TC-006 |
| Severity | High |
| Status | Observed — retest not recorded |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #12 (Jerome Balagtas) |

**Summary:** The entered 20 prior cycle hours were not reflected in the cycle recap.

**Retest path:** Enter 20 prior cycle hours, generate the standard trip, and compare the input with the cycle recap and remaining availability.

**Expected:** Prior cycle hours should be included in the recap and remaining-cycle calculation.

**Observed:** The source workbook recorded that the 20 prior cycle hours were ignored.

#### BUG-APP12-003 — Required 30-minute breaks are missing from generated schedule

| Field | Details |
|---|---|
| Application ID | Application 12 |
| Related Test Cases | TC-006, TC-007 |
| Severity | Critical |
| Status | Observed — retest not recorded |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #12 (Jerome Balagtas) |

**Summary:** The assessment recorded missing 30-minute breaks after 8 hours on Days 1 and 2.

**Retest path:** Generate the standard multi-day trip and inspect the driving timeline on Days 1 and 2 for the required break.

**Expected:** The schedule should include the required 30-minute break at the appropriate point in each driving period.

**Observed:** The notes recorded that the required breaks were missing on Days 1 and 2.

#### BUG-APP12-004 — Fuel stop is scheduled late

| Field | Details |
|---|---|
| Application ID | Application 12 |
| Related Test Cases | TC-008 |
| Severity | Medium |
| Status | Observed — retest not recorded |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #12 (Jerome Balagtas) |

**Summary:** A fuel stop was recorded as late relative to the assessment's 1,000-mile interval.

**Retest path:** Generate the standard route and compare the mileage at each scheduled fuel stop with the required interval.

**Expected:** Fuel stops should be scheduled at or before the defined interval.

**Observed:** The source workbook describes the fuel stop as late but does not preserve the exact stop mileage.

#### BUG-APP15-001 — Fuel stop is approximately 45 miles late

| Field | Details |
|---|---|
| Application ID | Application 15 |
| Related Test Cases | TC-008 |
| Severity | Medium |
| Status | Observed — retest recommended |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #15 (Boredoom17) |

**Summary:** The highest-scoring application scheduled a fuel stop approximately 45 miles later than the assessment's 1,000-mile interval.

**Retest path:** Generate the standard trip and inspect the mileage at the first scheduled fuel stop.

**Expected:** The fuel stop should occur at or before the 1,000-mile assessment interval.

**Observed:** The source notes recorded the stop as approximately 45 miles late.

#### BUG-APP15-002 — ETA differs by approximately 30 minutes

| Field | Details |
|---|---|
| Application ID | Application 15 |
| Related Test Cases | TC-003, TC-010 |
| Severity | Low |
| Status | Observed — retest recommended |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #15 (Boredoom17) |

**Summary:** An approximately 30-minute discrepancy was recorded in the estimated arrival time.

**Retest path:** Generate the standard trip and compare the ETA values shown in the trip summary and relevant itinerary details.

**Expected:** ETA values shown for the same event should be consistent, or any difference should be clearly explained.

**Observed:** The source workbook notes an ETA discrepancy of approximately 30 minutes; the exact fields being compared were not preserved.

#### BUG-APP15-003 — Final off-duty period is not clearly represented

| Field | Details |
|---|---|
| Application ID | Application 15 |
| Related Test Cases | TC-005, TC-007 |
| Severity | Medium |
| Status | Observed — retest recommended |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #15 (Boredoom17) |

**Summary:** The final off-duty period was not clearly visible in the generated daily-log presentation.

**Retest path:** Generate the same multi-day trip and inspect the final day's 24-hour log and end-of-trip duty-status timeline.

**Expected:** The final off-duty period should be clearly represented in the applicable daily log.

**Observed:** The source notes state that the final off-duty period was not clearly shown; they do not establish whether the underlying calculation was absent or only poorly presented.

#### BUG-APP16-001 — Generated trip dates are stale

| Field | Details |
|---|---|
| Application ID | Application 16 |
| Related Test Cases | TC-003, TC-005 |
| Severity | High |
| Status | Observed — retest recommended |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #16 (esa-yas) |

**Summary:** The generated logs used June 2025 dates rather than the November 2026 assessment date.

**Retest path:** Generate the trip using the assessment start-date conditions and compare the generated itinerary and daily-log dates with the selected/current trip date.

**Expected:** Generated dates should follow the date selected or supplied for the trip, not an unrelated stale date.

**Observed:** The assessment recorded June 2025 dates while the assessment took place in November 2026.

#### BUG-APP16-002 — No fuel stop generated for a 1,786-mile trip

| Field | Details |
|---|---|
| Application ID | Application 16 |
| Related Test Cases | TC-008 |
| Severity | High |
| Status | Observed — retest recommended |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #16 (esa-yas) |

**Summary:** No fuel stop appeared in the generated plan for a trip of approximately 1,786 miles, despite the 1,000-mile assessment interval.

**Retest path:** Generate the same long-distance trip and inspect the itinerary and map for fuel-stop events.

**Expected:** The plan should include fuel stops at or before the defined interval.

**Observed:** The source workbook recorded no fuel stop for the approximately 1,786-mile trip.

#### BUG-APP18-001 — Daily driving time exceeds the 11-hour assessment limit

| Field | Details |
|---|---|
| Application ID | Application 18 |
| Related Test Cases | TC-005, TC-006 |
| Severity | Critical |
| Status | Observed — retest not recorded |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #18 (Truck Trip Planner Engine) |

**Summary:** The generated itinerary showed 12.8 hours of driving on Day 2 and 11.6 hours on Day 3, exceeding the assessment's 11-hour daily driving limit.

**Retest path:** Generate the same three-day itinerary and total the driving intervals shown for Days 2 and 3.

**Expected:** Daily driving time should not exceed the 11-hour assessment limit.

**Observed:** The workbook recorded 12.8 hours on Day 2 and 11.6 hours on Day 3.

#### BUG-APP18-002 — Entered cycle hours appear to be ignored

| Field | Details |
|---|---|
| Application ID | Application 18 |
| Related Test Cases | TC-002, TC-006 |
| Severity | High |
| Status | Observed — retest recommended |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #18 (Truck Trip Planner Engine) |

**Summary:** The entered 20 cycle hours appeared not to affect the generated cycle calculation.

**Retest path:** Enter 20 prior cycle hours, generate the trip, and compare the input with the cycle recap and remaining availability.

**Expected:** The prior-cycle input should be reflected in the calculation.

**Observed:** The source notes state that the 20-hour input appeared to be ignored.

#### BUG-APP18-003 — Fuel-stop count is insufficient for the generated route

| Field | Details |
|---|---|
| Application ID | Application 18 |
| Related Test Cases | TC-008 |
| Severity | High |
| Status | Observed — retest recommended |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #18 (Truck Trip Planner Engine) |

**Summary:** The generated route contained an insufficient number of fuel stops under the assessment's fuel-stop interval.

**Retest path:** Generate the same route and compare total route mileage with the mileage and number of scheduled fuel stops.

**Expected:** Fuel stops should be placed often enough to comply with the defined interval.

**Observed:** The workbook records an insufficient fuel-stop count but does not preserve the exact stop positions or count.

#### BUG-APP18-004 — Some route checkpoints are mislabeled

| Field | Details |
|---|---|
| Application ID | Application 18 |
| Related Test Cases | TC-003, TC-004 |
| Severity | Medium |
| Status | Observed — retest recommended |
| Source evidence | Original workbook → Individual QA Analysis → Candidate #18 (Truck Trip Planner Engine) |

**Summary:** Some checkpoints in the generated route were mislabeled.

**Retest path:** Generate the standard trip and compare checkpoint labels with the route locations and stop sequence.

**Expected:** Each checkpoint should display the correct corresponding location or stop name.

**Observed:** The assessment notes recorded mislabeled checkpoints; the individual incorrect labels were not retained.

### 4. Access and Integration Blockers

The following events prevented meaningful evaluation of the core workflow. They are recorded separately because the workbook does not establish the underlying root cause or prove defects in inaccessible trip-planning/ELD logic.

| Application ID | Observed blocker | Assessment impact | Source workbook reference |
|---|---|---|---|
| Application 06 | Backend API hostname DNS resolution failure; U.S. locations could not be used; primary action and login/register controls did not work. | No route, map, stops, or ELD output; core workflow unverified. | Individual QA Analysis, Candidate #6 |
| Application 07 | Deployed frontend requests blocked by CORS/preflight failure. | No route, map, itinerary, or ELD logs; core workflow unverified. | Candidate #7 |
| Application 08 | Initial geocoding HTTP 429 and trip API HTTP 500; logs generated after cache clear. | Partial execution; HOS checks and recap not fully verifiable. | Candidate #8 |
| Application 09 | Registration blocked by Clerk development instance 100-user limit. | Planner inaccessible; no ELD functionality evaluated. | Candidate #9 |
| Application 10 | Trip-planning request returned HTTP 500. | No route, map, stops, or ELD logs generated. | Candidate #10 |
| Application 11 | Backend could not resolve PostgreSQL hostname; raw internal database error exposed. | No route, map, stops, or ELD logs generated. | Candidate #11 |
| Application 13 | Signup blocked by frontend/backend CORS preflight failure. | Planner and ELD outputs inaccessible. | Candidate #13 |
| Application 14 | Trip-planning API returned HTTP 500. | No route, map, stops, or ELD logs generated. | Candidate #14 |
| Application 19 | Dallas geocoding returned HTTP 502. | No route, map, stops, or ELD logs generated. | Candidate #19 |
| Application 20 | `/api/trips/` request blocked by CORS; missing `Access-Control-Allow-Origin` and failed OPTIONS preflight. | No trip, route, map, stops, or ELD logs generated. | Candidate #20 |

### 5. Areas Requiring Further Verification (Not Logged as Confirmed Defects)

| Application ID | Unverified or limited area | Why it is not a confirmed defect |
|---|---|---|
| Application 08 | Break/reset/14-hour compliance, recap, and sleeper-berth interpretation. | The source workbook explicitly says these could not be verified or were unclear. |
| Application 15 | Whether the final off-duty period was absent from the calculation or only unclear in the presentation. | The observation concerns visibility; the underlying status calculation was not established as wrong. |
| Application 17 | U.S. ELD/HOS and truck trip-planning suitability. | The submitted product was a European manual driver-log application, outside the intended U.S. trip-planner workflow. |
| Applications 06, 07, 09, 10, 11, 13, 14, 19, 20 | ELD calculations and route/stop behaviour. | Core workflows were inaccessible, so these behaviours were not exercised. |

### 6. Defect Lifecycle and Retest

1. **Record:** Preserve the observed behaviour and source workbook reference.
2. **Reproduce:** Re-run the retest path against an available version of the application.
3. **Capture:** Collect screenshots, screen recordings, inputs, timestamps, and relevant network responses where permitted.
4. **Triage:** Confirm the requirement, impact, severity, and whether the issue is reproducible.
5. **Track:** Update the status and add verified reproduction evidence.
6. **Retest:** After a fix is available, repeat the same scenario and record the result.
7. **Close:** Close only when the expected behaviour is observed.

**Current limitation:** The original workbook preserves observation summaries but not all raw screenshots, timestamps, exact input payloads, or network logs. Therefore, entries are marked as observed from the assessment record and retest is outstanding; they must not be presented as independently reproduced or developer-confirmed defects.

### 7. Conclusion

The assessment record contains functional and output issues across several applications, as well as distinct deployment, authentication, DNS, API, and CORS blockers. Separating observed defects from access limitations preserves the integrity of the case study and gives a clear basis for future reproduction and retesting.
