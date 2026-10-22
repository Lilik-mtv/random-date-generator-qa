# Feature Improvement Report — Explicit Input Validation and Accessible Errors

**ID:** IMP-001  
**Type:** Feature / UX improvement  
**Priority:** Medium (proposed)  
**Status:** Proposed — requires product review  
**Component:** Random Date Generator only

## Summary
Provide explicit, field-level validation for count, start date, end date, and custom date format, with clear instructions when generation cannot proceed.

## Context
The public page exposes fields for count, output format, custom date format, start date, and end date. During the initial page inspection, interactive validation behavior was not verified. This is therefore an improvement proposal, not a confirmed defect.

## User impact
Without clear and consistent validation, users may not know why generation failed or how to correct the inputs. This can slow QA/data-preparation workflows and make the tool harder to use with assistive technology.

## Proposed behavior
- Reject malformed or impossible calendar dates instead of silently changing them.
- Reject a start date later than the end date and explain the required order.
- Validate count as a positive integer and communicate any supported minimum/maximum.
- If custom format is selected, explain accepted tokens and flag an empty or unsupported pattern.
- Associate each error with its field; move focus to or announce the first error accessibly.
- Preserve valid user-entered values after validation fails.

## Acceptance criteria
1. Invalid input produces a clear message adjacent to the relevant field.
2. Error text explains how to fix the input.
3. Errors are announced to assistive technologies and are not conveyed by color alone.
4. Invalid input does not generate misleading or out-of-range dates.
5. Valid inputs continue to generate output as expected.
6. Automated or manual tests cover each validation rule.

## Steps to validate the proposal
1. Enter an impossible date such as `2025-02-30`.
2. Set start date later than end date.
3. Enter count values `0`, `-1`, a decimal, alphabetic text, and an extremely large integer.
4. Select custom format and leave the format field blank or enter an unsupported token.
5. Verify the message, focus behavior, preserved values, and absence of misleading output.

## Evidence
No failure evidence is attached because these interactive cases have not been executed. Confirm actual current behavior before converting this improvement proposal into a defect report.
