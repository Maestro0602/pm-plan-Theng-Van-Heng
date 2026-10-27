# Task 1: project, operation or programme?

| #  | Initiative | Temporary? | Unique? | Coordinated? | Class | Justification |
|----|------------|------------|---------|--------------|-------|---------------|
| 1  | Build the Realtime Quiz platform and pilot it with 50 students in week 14 | Yes | Yes | No | Project | Has a defined timeframe, distinct scope, and delivers a unique pilot product. |
| 2  | Run the nightly backup of the gicitc.com PostgreSQL database | No | No | No | Operation | Repeats every night with the same output and no end date as part of keeping the service running. |
| 3  | Move the department's three web servers to a new Linode region before 15 December | Yes | Yes | No | Project | Has a strict deadline and a unique one-off infrastructure migration scope. |
| 4  | Answer helpdesk tickets within the 4-hour service level | No | No | No | Operation | Ongoing, repetitive service delivery without a fixed end date. |
| 5  | "Digital classroom": Realtime Quiz, LMS upgrade and lecture capture sharing one login and one grade export | Yes | Yes | Yes | Programme | Three related projects; the shared login and grade export are a benefit that none of them delivers alone, so they are coordinated. |
| 6  | Apply the monthly security patches to the VPS | No | No | No | Operation | Routine, repetitive operational maintenance performed on a regular cycle. |
| 7  | Add multi-node scaling (RabbitMQ relay, Redis registry) to Realtime Quiz next semester | Yes | Yes | No | Project | Has a specific time window next semester to deliver distinct new technical capabilities. |
| 8  | Operate the Realtime Quiz platform after go-live: password resets, restarts, monitoring | No | No | No | Operation | Ongoing, repetitive support and maintenance activities after project delivery. |
| 9  | Write and publish the department's annual IT report for the dean by 31 January | Yes | Yes | No | Project | Has a fixed deadline and produces a unique deliverable for that specific year. |
| 10 | Replace 40 wireless access points in two buildings during the summer break | Yes | Yes | No | Project | Limited to a definite timeframe during summer break with a unique hardware upgrade scope. |

## Grey zones

Row 9 (Annual IT report for the dean):
- Alternative Class: Operation (if treated as a routine, highly templated recurring administrative duty executed the same way every year).
- What would settle it: Checking whether the sponsor funds it as a separate endeavour with its own temporary team and budget, or whether departmental staff absorb it as standard recurring operational workflow.

Row 7 (Multi-node scaling next semester):
- Alternative Class: Operation (if treated as a routine backlog maintenance release handled by ongoing operational staff).
- What would settle it: Checking whether the department charters a distinct follow-up project with dedicated staffing and milestone deliverables, or folds the work into routine operational support.

## What our project hands over

At go-live in week 14, the project team will officially hand over the fully functional Realtime Quiz platform, along with source code, architecture documentation, configuration files, and deployment runbooks, to the IT department's operational staff. IT operations will take responsibility for day-to-day hosting management on the Linode VPS, monitoring server health, running nightly PostgreSQL database backups, and applying monthly security patches. The team will deliver a structured knowledge-transfer walkthrough covering common troubleshooting workflows and user support procedures so operations can maintain the service independently.
