# Project charter: Realtime Quiz platform

| Field    | Value                              |
|----------|------------------------------------|
| Version  | 1.0 (draft for sponsor approval)   |
| Date     | 2026-09-29                         |
| Sponsor  | Head of the IT department          |
| PM       | Theng Van Heng, Lead Software Engineer  |

## 1. Purpose and justification
The department currently faces high manual grading workloads and a lack of immediate live feedback mechanisms during lectures, resulting in delayed engagement assessments as detailed in `business-case.md`. To solve this, the Realtime Quiz platform will be developed to deliver low-latency interactive quizzes, automated grading synchronization, and instant analytical insights for instructors. This system reduces administrative overhead, accelerates feedback loops, and enhances overall student participation and learning outcomes during lectures.

## 2. Objectives and success criteria
| #  | Objective (what will be true)      | Success criterion (number + week) |
|----|------------------------------------|-----------------------------------|
| O1 | Core project setup and secure user authentication foundation operational | Completed and verified with role-based access control by week 3 |
| O2 | Pilot with 50 students in one live session | 50 participants, 0 blocking defects, week 14 |
| O3 | Broadcast latency during the pilot | $\le 500\text{ ms}$ at the 95th percentile, measured week 14 |
| O4 | Concurrent user capacity handling during load tests | Supports at least 100 simultaneous quiz participants during testing in week 12 |
| O5 | Automated grade export functionality integrated with campus LMS | Successfully exports assessment grades with 100% data accuracy, verified in week 10 |

## 3. High-level scope
**In scope:**
- Quiz editor page
- Live session host dashboard
- Student participant interface
- Automated grade export module
- Instructor analytics and reporting view

**Out of scope:**
- Native mobile applications for iOS and Android
- Advanced AI-generated question authoring tools
- Multi-tenant SaaS subscription billing integration
- Offline standalone desktop mode

## 4. Milestones
| Week | Milestone                          | Ends process group |
|------|------------------------------------|--------------------|
| 1    | Charter approved, team formed      | Initiating         |
| 3    | Core setup and user authentication | Planning           |
| 5    | Quiz authoring module completed    | Executing          |
| 7    | MVP demo                           | Executing          |
| 10   | Analytics and grade export module  | Executing          |
| 12   | System hardening and load testing  | Monitoring & Controlling |
| 14   | Pilot with 50 students, closure    | Closing            |

## 5. Budget summary
Effort:  students 4 x 14 x 8 h = 448 h; PM 14 x 3 h = 42 h; total 490 h  
Cash:    hosting 4 x 25 USD = 100; domain 15; tools 60; reserve 25 (14%); total 200 USD

## 6. Assumptions
- Student developers will consistently dedicate an average of 8 hours per week throughout the 14-week project lifecycle.
- Cloud hosting infrastructure providers will maintain stable uptime during development, staging, and testing phases.
- University faculty members will be available for scheduled feedback sessions during weeks 4, 7, and 10.

## 7. Constraints
- Project delivery must be completed strictly within the 14-week academic semester timeframe.
- Total cash expenditures cannot exceed the hard cap of 200 USD including reserves.
- All student participation data must remain compliant with campus data privacy policies and stay on approved infrastructure.

## 8. High-level risks
- **Risk 1:** WebSocket connection instability under high concurrency during live sessions. *(Mitigation: Implement robust auto-reconnection logic and perform rigorous load testing in week 12).*
- **Risk 2:** Scope creep during the quiz authoring feature build phase. *(Mitigation: Strict adherence to defined In-Scope deliverables and formal change request tracking).*

## 9. Project manager authority
The PM may re-plan tasks within the 490 hours effort and 200 USD cash budget without prior approval. Adding scope, altering the pilot timeline, or drawing on funds beyond the specified reserve requires the sponsor's written approval within 5 working days.

## 10. Approval
Sponsor: `____________________`  Date: `________`  
PM:      `____________________`  Date: `________`