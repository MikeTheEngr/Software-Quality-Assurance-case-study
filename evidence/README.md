# Evidence Capture Guide
## Truck Trip Planner — Top Three Application Reviews

### 1. Purpose and evidence status

This guide organises genuine visual evidence for the three highest-ranked applications in the assessment. The original workbook records Application 15 at 19/25 (76%), and Applications 02 and 16 tied at 17/25 (68%). These are historical assessment scores, not new test results.

**Current evidence status:** No screenshots have been added to this directory. Every item below is a planned capture, not evidence already collected.

### 2. Capture integrity

- Capture the actual application interface or output. Do not create mockups or reconstruct screens.
- Redact personal names, email addresses, credentials, tokens, private URLs, and confidential assessment information before publishing.
- Preserve enough screen context to identify the feature and understand the observation.
- Record the capture date, browser, viewport, and evidence ID.
- A screenshot proves only what is visible in that capture; it does not independently prove hidden calculations, backend behaviour, or regulatory compliance.
- If an application is no longer accessible, mark the capture **Unavailable** and explain why. Never substitute an unrelated image.

### 3. Capture plan

#### Application 15 — 19/25 (76%)

The assessment notes recorded complete 24-hour logs, a cycle recap reconciling with the entered 20 prior hours and planned duty, HOS sequencing, multi-day planning, and working PDF export. Follow-up concerns included a fuel stop approximately 45 miles late, an ETA discrepancy of about 30 minutes, and a final off-duty period that was not clearly shown.

| Evidence ID | Suggested filename | Capture target |
|---|---|---|
| APP15-01 | APP15-01-trip-inputs-route.png | Trip inputs and Dallas → Houston → Los Angeles route |
| APP15-02 | APP15-02-eld-daily-log.png | Representative 24-hour ELD daily log |
| APP15-03 | APP15-03-cycle-hos-recap.png | Cycle-hours recap and HOS schedule |
| APP15-04 | APP15-04-fuel-stop-eta.png | Fuel-stop placement and ETA details |
| APP15-05 | APP15-05-pdf-export.png | Exported PDF and readable report content |

#### Application 02 — 17/25 (tied 2nd)

The assessment notes recorded broad functional coverage, including stop timings, breaks, fuel, pickup/drop-off, row totals, and daily miles. Presentation concerns included blank hours/remarks/header fields, unnamed stops, truncated text, and nested scrolling.

| Evidence ID | Suggested filename | Capture target |
|---|---|---|
| APP02-01 | APP02-01-trip-inputs-route.png | Trip inputs and generated route |
| APP02-02 | APP02-02-stops-breaks-fuel.png | Stop, break, and fuel schedule |
| APP02-03 | APP02-03-eld-log-fields.png | ELD log fields, including hours and remarks |
| APP02-04 | APP02-04-log-layout-scroll.png | Log layout, labels, truncation, and scrolling |

#### Application 16 — 17/25 (tied 2nd)

The assessment notes recorded a correct route, complete 24-hour logs, and verified driving limits, breaks, resets, and cycle calculations. Concerns included generated dates in June 2025 rather than the November 2026 assessment period and no fuel stop on an approximately 1,786-mile trip despite the 1,000-mile interval.

| Evidence ID | Suggested filename | Capture target |
|---|---|---|
| APP16-01 | APP16-01-route-distance.png | Generated route and displayed distance |
| APP16-02 | APP16-02-eld-log-dates.png | ELD daily-log date headers |
| APP16-03 | APP16-03-hos-break-reset.png | HOS timeline with driving, break, and reset periods |
| APP16-04 | APP16-04-fuel-stop-schedule.png | Fuel-stop schedule for the long route |

### 4. Evidence register

Update this register only after capturing and reviewing the actual image.

| Evidence ID | Application | Status | Repository path | Capture date | Browser / viewport | Notes |
|---|---|---|---|---|---|---|
| APP15-01 | Application 15 | Pending capture | — | — | — | |
| APP15-02 | Application 15 | Pending capture | — | — | — | |
| APP15-03 | Application 15 | Pending capture | — | — | — | |
| APP15-04 | Application 15 | Pending capture | — | — | — | |
| APP15-05 | Application 15 | Pending capture | — | — | — | |
| APP02-01 | Application 02 | Pending capture | — | — | — | |
| APP02-02 | Application 02 | Pending capture | — | — | — | |
| APP02-03 | Application 02 | Pending capture | — | — | — | |
| APP02-04 | Application 02 | Pending capture | — | — | — | |
| APP16-01 | Application 16 | Pending capture | — | — | — | |
| APP16-02 | Application 16 | Pending capture | — | — | — | |
| APP16-03 | Application 16 | Pending capture | — | — | — | |
| APP16-04 | Application 16 | Pending capture | — | — | — | |

### 5. Adding screenshots

1. Review each image for sensitive or confidential information.
2. Save the redacted publication copy using the matching filename above.
3. Add it under `evidence/screenshots/`.
4. Update the evidence register with its exact path and capture metadata.
5. Link the evidence ID from the relevant test case or bug observation where it supports a finding.

Suggested structure:

```text
evidence/
├── README.md
└── screenshots/
    ├── APP15-01-trip-inputs-route.png
    ├── APP02-01-trip-inputs-route.png
    └── APP16-01-route-distance.png
```

The filenames are examples of the naming convention only; they do not mean the screenshots have been captured.

### 6. Traceability

- [Evaluation Scorecard](../test-results/evaluation-scorecard.md) — original scores and application observations.
- [Application Ranking](../test-results/application-ranking.md) — score-based ranking and top-three comparison.
- [Functional Test Cases](../test-cases/functional-test-cases.md) — test definitions and execution records.
- [Bug Reports](../bug-reports/bug-reports.md) — recorded observations, severity, and retest paths.

This is an evidence capture plan. It does not claim that new screenshots or independent retests have been completed.
