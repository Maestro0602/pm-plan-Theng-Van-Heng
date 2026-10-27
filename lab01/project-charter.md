# Project charter: Realtime Quiz platform

| Field    | Value                              |
|----------|------------------------------------|
| Version  | 1.0 (draft for sponsor approval)   |
| Date     | 2026-09-29                         |
| Sponsor  | Head of the IT department          |
| PM       | Supervising lecturer               |

## 1. Purpose and justification

Department lecturers face substantial manual grading workloads and lack mechanisms for immediate feedback during lectures, leaving student engagement unmeasured until exams. The Realtime Quiz platform solves this by delivering an interactive web platform where instructors author multiple-choice quizzes and host live, timed sessions with instant scoring and real-time WebSocket leaderboards. As justified in `business-case.md`, building this platform yields an estimated net annual benefit of 4,500 USD by saving 300 hours of marking effort across 10 lecturers and avoiding recurring commercial SaaS subscription costs. The project also provides students with valuable capstone development experience while ensuring full departmental data ownership.

## 2. Objectives and success criteria

| #  | Objective (what will be true) | Success criterion (number + week) |
|----|-------------------------------|-----------------------------------|
| O1 | Core MVP functionality (all Must features: authoring, live timed participation, instant scoring, WebSocket leaderboards, authentication) operational | Demonstrated live to sponsor with 0 critical defects in week 7 |
| O2 | Pilot with 50 students in one live session | 50 participants, 0 blocking defects, week 14 |
| O3 | Broadcast latency during the pilot | <= 500 ms at the 95th percentile, measured week 14 |
| O4 | Server capacity and resilience under peak concurrent load | 1 single instance serves 20 concurrent sessions of 100 participants on 2 vCPU and 2 GB RAM, validated in week 12 |
| O5 | Software quality and test automation standard | Code line coverage >= 80% with green CI pipeline on every merge by week 14 |

## 3. High-level scope

**In scope:**
- Multiple-choice quiz authoring module
- Live session hosting runner with per-question countdown timers
- Student participant live answering and instant scoring interface
- Real-time leaderboard broadcast module over WebSocket
- Instructor analytics dashboard and results export module (CSV and PDF)

**Out of scope:**
- Native mobile applications for iOS and Android
- Question types other than multiple choice (no free text questions)
- Integrated video conferencing tools
- Direct Learning Management System (LMS) integration
- Multi-node clustering and distributed scaling infrastructure

## 4. Milestones

| Week | Milestone | Ends process group |
|------|-----------|--------------------|
| 1 | Charter approved, team formed | Initiating |
| 3 | Accounts, security architecture, and development setup verified | Planning |
| 5 | Quiz authoring and live session core complete | Executing |
| 7 | MVP demo | Executing |
| 10 | Analytics, reporting, and CSV/PDF export complete | Executing |
| 12 | Load testing with 100 simulated users and system hardening | Monitoring and Controlling |
| 14 | Pilot with 50 students, closure | Closing |

## 5. Budget summary

Effort: students 4 x 14 x 8 h = 448 h; PM 14 x 3 h = 42 h; total 490 h  
Cash: hosting 4 x 25 USD = 100; domain 15; tools 60; reserve 25 (14 %); total 200 USD

## 6. Assumptions

- Student developers dedicate an average of 8 hours per week each throughout the 14-week semester.
- The Linode VPS hosting environment and campus network remain accessible and stable for deployment.
- Instructors and 50 pilot students will be available to participate in live trial sessions in week 14.

## 7. Constraints

- Fixed time constraint: The project must complete within exactly 14 weeks starting 2026-09-29.
- Hard cash budget cap: Total project expenditure cannot exceed 200 USD, including all reserves.
- Technology constraint: Single server instance deployment (2 vCPU, 2 GB RAM) behind a Caddy reverse proxy on Linode.

## 8. High-level risks

- **Campus proxy WebSocket blocking:** The campus network proxy may block WebSocket traffic. *(Mitigation: Implement SockJS fallback mechanism in week 4).*
- **Modern framework compatibility:** Spring Boot 4 and Spring Security 7 have limited tutorial resources. *(Mitigation: Rapid technical spike and early security architecture verification by week 3).*
- **Client clock drift:** Discrepancies between student client devices and server time may cause race conditions when closing questions. *(Mitigation: Enforce authoritative server-side timing and keep drift under 200 ms).*

## 9. Project manager authority

The PM may re-plan project tasks within the 490 hours of effort and 200 USD cash budget without prior sponsor approval. Adding scope deliverables, rescheduling the week-14 pilot date, or spending funds beyond the allocated contingency reserve requires the sponsor's written approval within 5 working days.

## 10. Approval

Sponsor: ____________________ Date: ________  
PM:      ____________________ Date: ________
