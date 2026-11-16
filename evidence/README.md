# Evidence Review
## Truck Trip Planner — Application 16 (Spotter AI)

### Purpose

This page records the visual evidence supplied for Application 16 during the assessment portfolio review. Application 16 received **17/25 (68%)**, tied for second place in the original assessment.

The user has confirmed that Spotter AI is Application 16 and that the screenshots already supplied are sufficient. **No further screenshot collection is planned.**

### Evidence received

The six screenshots below were supplied in this conversation and visually reviewed. They are recorded here as received evidence; the original image files have **not** been committed to this repository. No browser or viewport metadata was supplied.

| Evidence ID | Screenshot content | Directly visible information |
|---|---|---|
| APP16-00 | Trip input form | Current location Dallas, TX; pickup Houston, TX; drop-off Los Angeles, CA; current cycle used 20 hours. |
| APP16-01 | Generated trip dashboard and route map | Route map shows Dallas → Houston → Los Angeles. Dashboard shows 1,786.3 miles, 30.62 hours drive time, 56.48 hours total trip time, 3 log-sheet days, and 13.52 hours cycle remaining. The visible stop timeline begins with a 0.25-hour pre-trip inspection, a 4.33-hour / 238-mile drive to Houston, and a 1-hour pickup. |
| APP16-02 | Earlier Day 1 ELD log | Date 2025-06-01; 605 miles; Off Duty 6h; Sleeper Berth 5.25h; Driving 11h; On Duty (ND) 1.75h; displayed total 24h. |
| APP16-03 | Earlier Day 3 ELD log | Date 2025-06-03; 576.3 miles; Off Duty 9.52h; Sleeper Berth 2.25h; Driving 10.48h; On Duty (ND) 1.75h; displayed total 24h. |
| APP16-04 | Fuel-stop map popup | Fuel stop in Vinton, TX; Fri Nov 13 at 4:00 PM; 741 miles remaining; return at 4:30 PM. |
| APP16-05 | ELD daily log preview | Day 1 dated November 12, 2026; 605 miles; Off Duty 8:30; Sleeper Berth 3:00; Driving 11:00; On Duty (Not Driving) 1:30; displayed total 24 hours. A Download PDF control is visible. |

### Evidence-based observations

1. **Trip inputs and route:** The supplied input screen shows the intended Dallas → Houston → Los Angeles locations and 20 hours of cycle usage. The generated map displays the same route.
2. **Daily log totals:** The visible duty-status totals in APP16-02, APP16-03, and APP16-05 each add up to 24 hours.
3. **Driving time:** APP16-02 and APP16-05 each display 11 hours of driving; APP16-03 displays 10.48 hours.
4. **Fuel stop:** APP16-04 visibly shows a scheduled fuel stop in Vinton, Texas. This means the earlier assessment concern that no fuel stop appeared must not be repeated as a universal finding without confirming the exact run and configuration.
5. **Date inconsistency across supplied evidence:** APP16-02 and APP16-03 show June 2025 dates, while APP16-05 shows November 12, 2026. Treat these as separate observed outputs unless the same run/configuration can be established. Do not merge them into one execution record.
6. **PDF export:** APP16-05 shows the Download PDF control, but the screenshot alone does not establish that the PDF downloaded successfully or that the exported file is complete and readable.
7. **Cycle calculation:** The dashboard displays 13.52 hours remaining after 20 hours of cycle usage, but the screenshots do not provide enough calculation detail to independently validate the displayed result.

### Limitations and execution status

- These are observations from screenshots, not a fresh independent execution of every functional test case.
- No test case should be marked Passed or Failed solely because a screenshot exists.
- The screenshot of a PDF control is not proof of a successful PDF export.
- The fuel-stop popup confirms a displayed stop in that view; it does not by itself prove the stop interval is correct for the full trip.
- The differing log dates must remain separately documented until their run context is known.
- Original screenshot files remain in the conversation and have not been uploaded as binary assets to this repository.

### Traceability

- [Functional Test Cases](../test-cases/functional-test-cases.md) — designed tests and execution placeholders.
- [Evaluation Scorecard](../test-results/evaluation-scorecard.md) — original comparative assessment scores and observations.
- [Application Ranking](../test-results/application-ranking.md) — ranking of the assessed applications.

This review records only what is visible in the six supplied screenshots. It does not claim that additional tests, PDF downloads, or independent retests have been completed.
