# Final Functional Requirements

| ID | Requirement |
|---|---|
| FR-01 | The system shall allow authorized staff to register scholar records. |
| FR-02 | The system shall associate a scholar with a scholarship program. |
| FR-03 | The system shall maintain academic requirements for each scholarship program. |
| FR-04 | The system shall allow semester grade submission. |
| FR-05 | The system shall record the academic year and semester of every submission. |
| FR-06 | The system shall allow authorized staff to verify a grade submission. |
| FR-07 | The system shall evaluate verified academic information against scholarship requirements. |
| FR-08 | The system shall identify deficiencies. |
| FR-09 | The system shall maintain scholar status. |
| FR-10 | The system shall identify pending grade submissions. |
| FR-11 | The system shall allow users to search scholars by Student ID or name. |
| FR-12 | The system shall allow users to filter scholars by scholarship program or status. |
| FR-13 | The system shall display dashboard counts for scholarship monitoring. |
| FR-14 | The system shall validate grade and scholar data before saving. |
| FR-15 | The system shall restrict grade verification to authorized staff/admin users. |
| FR-16 | The system shall record who verified a submission and when. |
| FR-17 | The system shall maintain compliance evaluation records. |

# Non-Functional Requirements

| ID | Category | Requirement |
|---|---|---|
| NFR-01 | Security | Authentication and RLS shall restrict protected data and actions to authorized users. |
| NFR-02 | Privacy | Sensitive academic records shall only be accessible according to user role and database policies. |
| NFR-03 | Usability | Forms and navigation shall be simple enough for staff to complete core transactions quickly. |
| NFR-04 | Performance | Dashboard and list views should load normal laboratory datasets within a few seconds. |
| NFR-05 | Reliability | Database constraints shall reject invalid values and preserve transaction records. |
| NFR-06 | Data Integrity | Foreign keys, unique Student IDs, required fields, and status rules shall protect data consistency. |

# Business Rules

| ID | Rule |
|---|---|
| BR-01 | Every scholar must be assigned to an active scholarship program. |
| BR-02 | Every scholarship program must define its academic requirements. |
| BR-03 | A grade submission must belong to one scholar, academic year, and semester. |
| BR-04 | Only authorized personnel may verify submitted grades. |
| BR-05 | Only verified submissions may be used for final compliance evaluation. |
| BR-06 | A scholar cannot be marked Compliant while mandatory requirements are incomplete. |
| BR-07 | Scholar status must be based on the rules of the assigned scholarship program. |
| BR-08 | Changes to verified academic records must be traceable through verification metadata and database timestamps. |
| BR-09 | A submission cannot be verified twice without an authorized correction process. |
| BR-10 | Sensitive grade information must only be visible to authorized users. |

# Traceability

| Requirement | Actor | Use Case | Business Rule | Implemented Feature |
|---|---|---|---|---|
| FR-01 | Staff/Admin | Register Scholar | BR-01 | Scholar Form |
| FR-04 | Scholar/Staff | Submit Grades | BR-03 | Grade Submission Form |
| FR-06 | Staff/Admin | Verify Grade Submission | BR-04, BR-05 | Verification Action |
| FR-07 | Staff/Admin | Evaluate Academic Compliance | BR-02, BR-07 | Compliance Logic |
| FR-10 | Staff/Admin | View Dashboard | BR-05 | Pending Counter |
| FR-11 | Staff/Admin | Search Scholar | — | Scholar Search |
| FR-12 | Staff/Admin | Filter Scholars | — | Program/Status Filters |
| FR-13 | Staff/Admin | View Dashboard | — | Live Dashboard Counts |
