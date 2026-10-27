# Post-mortem: CampusPay wallet failure analysis (2026)

## 1. Timeline and sources

| # | When | Event | Source |
|---|------|-------|--------|
| 1 | Month 1 (February) | University IT unit is requested to develop CampusPay, a cashless payment mobile app for canteen purchases and library fines within one academic semester. | Fictional case from Lab-01 |
| 2 | Month 2 (March) | Head of Finance endorses the initiative via email as nominal "sponsor" but establishes no formal project charter and attends zero project review meetings. | Fictional case from Lab-01 |
| 3 | Month 3 (April) | Lead developer assumes dual responsibilities as both Project Manager and sole primary coder without formal project management authority or oversight. | Fictional case from Lab-01 |
| 4 | Month 4 (May) | A broad student survey triggers uncontrolled scope creep, expanding requirements to include campus bus ticketing and parking permits without budget or timeline adjustment. | Fictional case from Lab-01 |
| 5 | Month 6 (July) | Development continues with progress reported informally as "on schedule" based solely on code completion; no integration tests are conducted with actual canteen card terminals. | Fictional case from Lab-01 |
| 6 | Month 7 (September 1) | CampusPay launches publicly on the first day of the semester; real card terminals reject 40% of payment transactions immediately, doubling canteen wait queues. | Fictional case from Lab-01 |
| 7 | Month 7 (September 4) | Following overwhelming operational chaos and student outrage, university leadership officially withdraws CampusPay after three days of operation. | Fictional case from Lab-01 |
| 8 | Month 12 (February) | CampusPay relaunches five months later with drastically reduced scope, restricted solely to canteen payments after complete architectural rework. | Fictional case from Lab-01 |

## 2. Classification and organisation

- **Project / programme classification:** CampusPay was initiated as a temporary, unique project to digitize canteen and library fine transactions. However, when requirements expanded to encompass bus transit ticketing, parking gate integration, and payment settlement, it morphed into an unmanaged, uncoordinated programme of distinct projects without the required programme governance, interface architecture, or funding mechanisms.
- **Organizational structure and PM authority:** The project operated within a rigid functional or weak-matrix university structure. The lead developer was thrust into the PM role without project management training, formal delegation of authority, or the ability to negotiate resources. The PM lacked authority to decline scope additions from departmental surveys or demand operational hardware for pre-release testing.
- **Sponsor, charter, and PMO:** A legitimate sponsor was completely absent. The Head of Finance provided only passive "sponsorship by email" without signing a project charter, defining business value, or participating in governance gates. No Project Charter existed to baseline scope, milestones, or success metrics. There was no PMO or quality audit body to enforce testing gates or risk oversight.

## 3. Success criteria

- **Stated criteria:** The sole stated success criterion was a delivery deadline: "launch in September" with functional payment screens.
- **Missing measurable criteria:** The project lacked quantitative, measurable service level and technical criteria, including:
  - Transaction failure rate threshold (e.g., payment error rate < 0.1%).
  - Maximum processing latency at the point-of-sale terminal (e.g., transaction round-trip <= 2 seconds).
  - Minimum concurrent transaction throughput during peak canteen lunch rushes.
  - End-to-end payment terminal integration test coverage across all hardware revisions.
- **Ignored wider dimensions:**
  - *Benefits realization:* The business goal was reducing canteen congestion, yet the rollout aggravated delays.
  - *User experience:* Students and canteen cashiers were never included in usability trials prior to go-live.
  - *Operations readiness:* Canteen cashiers and IT support staff received neither operational runbooks nor fallback procedures for transaction timeouts.
  - *Team sustainability:* The dual-role PM/developer experienced immense burnout and isolation, carrying development and delivery liabilities alone.

## 4. Process groups and knowledge areas

| Process group | What went wrong or was skipped |
|---------------|--------------------------------|
| Initiating | Skipped charter formulation and formal sponsor sign-off; financial sponsorship existed only as an informal email thread without committed governance. |
| Planning | Inadequate scope definition and lack of a Work Breakdown Structure (WBS); zero planning for integration testing environments, terminal hardware procurement, or risk management. |
| Executing | Development proceeded in isolation without intermediate integration releases; the lead developer was overloaded trying to program complex payment features while handling coordination. |
| Monitoring and controlling | Project progress was reported subjectively as "on schedule" without objective earned value metrics, quality inspections, or gate reviews (falling into the "invisibility trap"). |
| Closing | No formal handover, user training, operational acceptance sign-off, or pilot stage occurred before exposing the unverified application to the entire student body. |

**Knowledge areas most responsible for the failure:**
1. **Scope Management:** Requirements were never baselined. Uncontrolled feature additions (bus tickets, parking fees) were admitted without evaluating cost, schedule, or technical feasibility impacts.
2. **Quality Management:** No formal quality assurance or verification process was executed. Testing software against live physical point-of-sale hardware was omitted entirely before launch day.
3. **Stakeholder and Integration Management:** The project failed to engage essential operational stakeholders (canteen staff, terminal hardware vendors), while the nominal sponsor provided zero direction or boundary enforcement.

## 5. Ethics

**Decision examined:** The decision by project leadership to proceed with the September 1 public launch despite having performed zero integration testing with physical canteen payment terminals.

- **Responsibility:** Leadership abandoned professional ownership by deploying an unverified payment platform into a live commercial environment where student funds and daily food services were directly impacted.
- **Respect:** The decision showed deep disrespect toward students and canteen staff, treating them as unconsenting test subjects and causing severe operational disruption during lunch hours.
- **Fairness:** It was fundamentally unfair to shift technical risk onto front-line canteen cashiers, who bore the public blame and anger of long student lines when terminals failed.
- **Honesty:** Reporting the project as ready for production launch constituted intellectual dishonesty, concealing the total absence of real-world hardware integration and transaction testing.

## 6. What our project will do differently

| # | Commitment (We will ...) | Measured by | By week | Charter line |
|---|--------------------------|-------------|---------|--------------|
| 1 | We will run a live session with 100 simulated concurrent students and the real campus Wi-Fi before the pilot | Load test execution report with 0 critical errors and response time <= 500 ms | 12 | Milestone week 12, Objective O3, Objective O4 |
| 2 | We will hold a signed charter with a named sponsor who attends the week-7 and week-13 phase gates | Formally signed charter document and documented gate review minutes | 1 | Section 10 approval, PM authority clause |
| 3 | We will strictly reject scope additions beyond the approved Must and Should lists without a formal written change request | Change log audit showing zero unapproved features added to the sprint backlogs | 7 | Section 3 High-level scope, PM authority clause |
| 4 | We will maintain automated continuous integration with rigorous test coverage on every merge | Automated CI pipeline status green with unit and integration line coverage >= 80% | 14 | Objective O5, Quality targets |
| 5 | We will conduct a full operational dry-run and knowledge handover with IT Operations before go-live | Handover sign-off checklist and approved deployment runbook with docker-compose.prod.yml | 13 | Milestone week 14, Section 9 PM authority, Phase Gate 3 |
