# Test Report — Random Date Generator

## 1. Executive summary
This report defines a focused black-box QA assessment for the CodeBeautify Random Date Generator. The public page exposes controls for number of dates, output format, custom date format, start date, and end date. The main risks are invalid range handling, boundary inclusivity, leap-year correctness, count validation, and incorrect formatting.

**Current status: Test design complete; interactive execution pending.** No confirmed functional defect is claimed in this report. The accompanying issue is a feature-improvement proposal based on making validation behavior explicit and testable.

## 2. Objective
Evaluate whether the generator:
- Generates the requested number of dates.
- Produces valid calendar dates.
- Respects the requested start and end boundaries.
- Handles equal, reversed, malformed, and leap-day ranges safely.
- Applies selected and custom output formats consistently.
- Communicates validation errors clearly and accessibly.

## 3. Scope
### In scope
- Count input and generated result count
- Date output format selector
- Custom date format input
- Start date and end date
- Generate action and result area
- Validation and error messaging directly related to this widget

### Out of scope
- Other CodeBeautify tools or site pages
- Account, advertising, or site-wide features
- Security penetration testing and backend implementation
- Statistical proof of randomness or cryptographic quality

## 4. Method
Use black-box testing with equivalence partitioning, boundary-value analysis, negative tests, and calendar-specific cases. For every case, compare actual output with the expected result and save evidence for failures.

## 5. Initial observations
- The publicly accessible page identifies controls for count, output format, custom format, start date, and end date.
- The page describes the generator as useful for QA, simulation, and data analysis.
- Interactive behavior has not been verified in a real browser for this assessment.
- Accordingly, all execution statuses in the test-case file remain `Not Run`; no pass rate is reported.

## 6. Priority test areas
| Priority | Area | Risk |
|---|---|---|
| P0 | Valid basic range | Core generation may fail |
| P0 | Start date equals end date | Single-date range may be mishandled |
| P0 | Reversed or invalid range | Incorrect output or unclear failure |
| P1 | Count boundaries and non-numeric values | Wrong number of results or UI failure |
| P1 | Leap day and year boundaries | Invalid calendar values |
| P1 | Built-in/custom formats | Output does not match selected format |
| P2 | Empty values, whitespace, keyboard access | Usability and accessibility issues |

## 7. Test data and expected behavior
Use deterministic ranges where possible:
- `2024-02-29` to `2024-02-29`: only `2024-02-29` is valid.
- `2024-02-28` to `2024-03-01`: every generated date must be one of Feb 28, Feb 29, or Mar 1, 2024.
- `2025-12-31` to `2026-01-01`: only those two dates are valid.
- Start later than end: should be rejected with a clear, actionable validation message.
- Invalid date such as `2025-02-30`: should not be silently normalized into a different date.

Confirm whether the product treats range endpoints as inclusive; if that is the intended contract, verify both endpoints can be generated and no result falls outside the range. A random run that does not happen to select an endpoint is not evidence that endpoint handling is broken.

## 8. Exit criteria
Before closing the assessment:
- Execute all P0 cases.
- Execute all P1 cases or document why they were blocked.
- Attach evidence for every failure.
- Re-test failed cases after any change.
- Record browser, OS, test date, and actual output.
- Report defects only when reproducible; otherwise file a feature request or further-investigation item.

## 9. Risks and limitations
- The live generator's interactive behavior was not executed as part of this initial review.
- Random outputs are nondeterministic; repeat tests or use narrow ranges to validate boundaries.
- UI labels alone do not prove underlying validation behavior.
- The improvement report is a proposal, not a confirmed bug.

## 10. Recommendation
Complete interactive execution, prioritizing invalid/reversed ranges, single-day ranges, leap-year handling, count validation, and format consistency. Publish the resulting evidence and execution log alongside this report.
