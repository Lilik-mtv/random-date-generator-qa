# QA Assessment: CodeBeautify Random Date Generator

**Target:** https://codebeautify.org/generate-random-date  
**Scope:** Random Date Generator widget only.  
**Assessment type:** Black-box functional test design + public-page inspection.  
**Status:** Initial review prepared; interactive execution is not yet verified.

## Purpose
Assess the generator's core behavior: count, output format, custom format, start/end date boundaries, invalid inputs, and generated-date validity.

## Important evidence note
The public page was inspected for the available controls and scope. This repository does **not** claim that the interactive test cases were executed in a real browser. Test cases are marked `Not Run` until someone performs them and records actual evidence. The improvement report is a recommendation, not a confirmed defect.

## Contents
- `reports/test-report.md` — summary, scope, approach, risks, and exit criteria
- `test-cases/test-cases.csv` — execution-ready test cases
- `issues/feature-improvement-report.md` — actionable UX improvement report
- `reports/execution-log-template.csv` — template for recording actual results

## How to execute
1. Open the target URL in a desktop browser.
2. Use the test data in `test-cases/test-cases.csv`.
3. Record actual output, pass/fail, browser/version, date, and evidence.
4. For each failure, repeat the test and capture a screenshot or short recording.
5. Do not mark a case Passed based only on expected behavior; verify the actual result.

## Suggested test strategy
- Equivalence partitioning for valid and invalid inputs
- Boundary-value analysis for count and date range
- Calendar edge cases (leap day, month/year boundaries)
- Format coverage and custom-format token combinations
- Negative testing for reversed/invalid dates and invalid count
- Basic usability and accessibility observations

## Environment
- Target URL: https://codebeautify.org/generate-random-date
- Initial page inspection: 2026-10-21
- Browser / OS for interactive execution: Not recorded (not executed in this assessment)
- Build/version: Not independently verified

## Publication
Create a **public** GitHub repository, upload these files, and link it from your resume or application. Do not claim tests were executed until the execution log contains real results.
