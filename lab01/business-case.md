# Business case: live quizzes for the IT department

## 1. Problem

Lecturers across the IT department spend substantial manual effort grading recurring quizzes and paper tests without gaining immediate insight into student comprehension during classroom lectures. Delayed feedback prevents timely pedagogical intervention, while manual marking places an avoidable administrative drain on teaching faculty.

Assumptions:
- Number of departmental lecturers running quizzes: 10
- Average marking time per lecturer per week: 1 h
- Teaching weeks per academic year: 30
- Notional value of one faculty/student hour: 10 USD (student labor is academically credited and unpaid; 10 USD/h is an economic benchmark used to quantify and compare effort)
- Total annual recurring marking effort: 10 lecturers * 1 h/week * 30 weeks = 300 hours/year (valued at 3,000 USD/year)

## 2. Options

| Option | Description | One-off cost | Annual cost | Annual benefit |
|--------|-------------|--------------|-------------|----------------|
| A | Do nothing: continue manual quiz distribution and physical/spreadsheet marking | 0 USD | 0 USD | 0 USD |
| B | Buy SaaS: purchase institutional commercial quiz subscriptions (e.g., Kahoot! EDU / Wooclap at an assumed educational tier of 15 USD per lecturer per month, cited October 2026) | 0 USD | 1,800 USD | 3,000 USD |
| C | Build Realtime Quiz: develop an internal web application using student capstone engineering effort and department VPS hosting | 4,900 USD | 300 USD | 4,800 USD |

## 3. Comparison

| Option | Net annual benefit | Payback (years) | Sensitivity (6 lecturers) |
|--------|--------------------|-----------------|----------------------------|
| B | 3,000 - 1,800 = 1,200 USD | 0 (no one-off cost) | 1,800 - 1,080 = 720 USD |
| C | 3,000 + 1,800 - 300 = 4,500 USD | 4,900 / 4,500 = 1.09 (approx. 1.1 years) | 1,800 + 1,080 - 300 = 2,580 USD: 4,900 / 2,580 = 1.9 years |

*(Note: In Option C, one-off economic cost reflects 490 hours of total effort at 10 USD/h notional = 4,900 USD, while actual project cash expenditure is strictly capped at 200 USD. Annual benefit includes 3,000 USD in saved marking labor plus 1,800 USD in avoided commercial SaaS licensing fees, offset by 300 USD annual Linode VPS hosting).*

## 4. Benefits not priced

- **Capstone learning outcomes:** Delivers 448 hours of hands-on production software engineering and DevOps practice to student developers (Spring Boot, WebSocket STOMP, Docker Compose, automated CI/CD).
- **Data sovereignty and privacy:** Full institutional control over student academic records, attendance logs, and quiz performance with on-premise/local VPS storage, preventing third-party vendor data harvesting.
- **No seat or participant limitations:** Free scaling across all departmental cohorts without per-student license tiers, subscription paywalls, or feature restrictions.
- **Customizability and extensibility:** Direct departmental control to adapt quiz schemas, analytics exports, and future features to specific curriculum needs.

## 5. Risks per option

### Option A (Do nothing)
- **Persistent administrative burden:** Faculty continue expending 300 hours annually on routine grading rather than research and student mentoring.
- **Instructional latency:** Inability to assess real-time lecture comprehension leads to lower student engagement and delayed remediation of learning gaps.

### Option B (Buy SaaS)
- **Vendor lock-in and escalating subscription fees:** Ongoing exposure to price increases, license changes, and potential cancellation if department operating budgets fluctuate.
- **Privacy and compliance hurdles:** Transmitting student identifiers and assessment analytics to external third-party cloud servers requires ongoing privacy clearance and vendor risk assessments.

### Option C (Build Realtime Quiz)
- **Delivery and execution risk:** Student team project delivery could suffer delays due to technical roadblocks with newer frameworks (Spring Boot 4 / WebSocket proxies). *Mitigated through a strict MVP scope, SockJS fallback, and weekly mentoring.*
- **Long-term operational support:** Risk that operational hand-over after week 14 is incomplete. *Mitigated by requiring automated CI test coverage >= 80%, Docker containerization, and structured runbook documentation for IT operations.*

## 6. Recommendation and review gate

**Recommendation:** Proceed with **Option C (Build)**. The project achieves an economic payback period of approximately 1.1 years (and 1.9 years under the pessimistic sensitivity scenario of 6 lecturers), requires only 200 USD in actual cash outlay, ensures institutional data ownership, and generates outstanding educational value for the student engineering team.

**Review gate:** A formal go/no-go review gate is established at the **week-7 MVP demo**. If the student engineering team fails to demonstrate all core Must features (quiz authoring, live timed participation, instant scoring, WebSocket leaderboards, and authentication) with zero critical blockers, the sponsor will exercise the contingency decision to pivot to **Option B (Buy SaaS)** for the following semester, reclassifying the build effort as exploratory research.
