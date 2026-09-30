# Functional Test Results Template

| Test ID | Scenario | Expected Result | Actual Result | Pass/Fail |
|---|---|---|---|---|
| TC-01 | Login with valid authorized account | Dashboard opens | | |
| TC-02 | Create scholar with complete data | Scholar saved | | |
| TC-03 | Create scholar without Student ID | Submission rejected | | |
| TC-04 | Submit semester grades | Record saved as Pending | | |
| TC-05 | Verify pending grade submission | Status becomes Verified | | |
| TC-06 | Evaluate scholar meeting requirements | Compliant | | |
| TC-07 | Evaluate scholar failing a requirement | With Deficiency | | |
| TC-08 | Search scholar by Student ID/name | Matching scholar displayed | | |
| TC-09 | Filter by scholarship/status | Correct subset displayed | | |
| TC-10 | Open deployed URL | System accessible online | | |

# Suggested demonstration data

## Compliant example
Program:
- Required GWA: 2.00
- Minimum Units: 15
- Failing grades allowed: No

Submission:
- GWA: 1.75
- Units: 18
- Failed: 0
- Incomplete: 0

Expected: Compliant

## Deficiency example
Program:
- Required GWA: 2.00
- Minimum Units: 15
- Failing grades allowed: No

Submission:
- GWA: 2.50
- Units: 15
- Failed: 0
- Incomplete: 0

Expected: With Deficiency because GWA is above the required maximum.
