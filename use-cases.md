# Use Case List

1. Login
2. Logout
3. Register Scholar
4. Assign Scholarship
5. Configure Scholarship Requirements
6. View Requirements
7. Submit Grades
8. Verify Grade Submission
9. Evaluate Academic Compliance
10. Record Deficiency
11. View Deficiency
12. Update Scholar Status
13. Process Scholarship Renewal
14. Search Scholar
15. Filter Scholars
16. Generate Compliance Report
17. View Dashboard

# Major Detailed Use Cases

## UC-07 Submit Grades
- Primary Actor: Scholar/Authorized Staff
- Goal: Record semester academic information.
- Preconditions: User is authenticated; scholar exists.
- Trigger: User selects Submit Grades.
- Main Flow:
  1. Select scholar.
  2. Enter academic year and semester.
  3. Enter GWA, units, failed subjects, incomplete subjects.
  4. System validates values.
  5. System saves submission as Pending.
- Alternative Flow: Invalid values cause validation error.
- Exception Flow: Duplicate scholar/year/semester is rejected by database constraint.
- Postconditions: Pending submission exists.
- Related Requirements: FR-04, FR-05, FR-14.
- Business Rules: BR-03.

## UC-08 Verify Grade Submission
- Primary Actor: Scholarship Staff
- Goal: Verify a pending submission.
- Preconditions: Pending submission exists; staff is authenticated.
- Trigger: Staff clicks Verify.
- Main Flow:
  1. Staff selects pending submission.
  2. System confirms authorization.
  3. System marks submission Verified.
  4. System stores verifier and verification time.
  5. System evaluates the verified record.
- Alternative Flow: User without staff/admin role is denied.
- Exception Flow: Already verified submission cannot be verified again through the normal action.
- Postconditions: Submission is Verified and has a compliance result.
- Related Requirements: FR-06, FR-07, FR-16.
- Business Rules: BR-04, BR-05, BR-09.

## UC-09 Evaluate Academic Compliance
- Primary Actor: Scholarship Coordinator/Staff
- Goal: Determine whether verified grades satisfy the assigned program.
- Preconditions: Submission is Verified; scholarship requirements exist.
- Trigger: Verification completes.
- Main Flow:
  1. Retrieve assigned scholarship requirements.
  2. Compare GWA.
  3. Compare enrolled units.
  4. Check failing-grade policy.
  5. Check incomplete subjects.
  6. Save Compliant or With Deficiency.
  7. Update scholar status.
- Alternative Flow: One or more conditions fail; system records reasons.
- Exception Flow: Missing scholarship requirements prevents final evaluation.
- Postconditions: Compliance result is stored.
- Related Requirements: FR-07, FR-08, FR-09.
- Business Rules: BR-02, BR-05, BR-06, BR-07.

## UC-13 Process Scholarship Renewal
- Primary Actor: Scholarship Coordinator
- Goal: Monitor and process renewal eligibility.
- Preconditions: Scholar has a verified academic record and compliance result.
- Trigger: Coordinator opens renewal workflow.
- Main Flow:
  1. Review latest compliance result.
  2. Confirm all mandatory documents/conditions.
  3. Mark For Renewal if requirements are met.
  4. Mark Renewed after approval.
  5. Mark Disqualified when program rules are not met.
- Alternative Flow: Missing requirement places scholar on appropriate pending/deficiency status.
- Exception Flow: No verified semester record means renewal cannot be finalized.
- Postconditions: Renewal status is updated.
- Related Requirements: FR-07, FR-09.
- Business Rules: BR-06, BR-07.

# Required Status Definitions

| Status | Condition |
|---|---|
| Active | Scholar is currently enrolled in an active scholarship program. |
| Pending Submission | Scholar has no current semester submission yet. |
| For Verification | Grade submission has been submitted and is awaiting staff verification. |
| Compliant | Latest verified submission satisfies all mandatory scholarship requirements. |
| With Deficiency | Latest verified submission fails at least one requirement. |
| Probationary | Program policy permits continued scholarship with specified conditions. |
| For Renewal | Scholar has completed required conditions and is awaiting renewal processing. |
| Renewed | Renewal has been approved for the next scholarship period. |
| Disqualified | Scholar no longer meets required scholarship conditions under program policy. |
