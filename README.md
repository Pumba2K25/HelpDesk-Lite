# HelpDesk-Lite
Purpose
HelpDesk Lite is a minimal but realistic ticketing system for small teams that need to capture issues, triage them quickly, and document resolutions. The project’s goal is to deliver a usable MVP that showcases the full Software Development Lifecycle (SDLC) with Agile practices: iterative planning, short feedback loops, continuous improvement, and working software over heavy process. The system will support ticket creation, status transitions, basic assignment, comments, and simple reporting—enough to be useful while staying achievable within two 3-week sprints.

Stakeholders

Product Owner (Instructor) – validates learning objectives and scope integrity.

End Users (Students/Techs) – submit and track tickets; provide feedback on usability.

Development Team (Me + peers) – implement features, tests, and documentation.

Reviewers/Peers – perform code reviews, file issues, and test acceptance criteria.

Scope & Deliverables
Scope covers a working web app with: ticket CRUD, statuses (Open, In-Progress, Resolved, Closed), priority levels, comments, basic user roles (submitter vs. handler), and a lightweight dashboard. Deliverables include: source code, README with setup and usage, CONTRIBUTING guidelines, user story backlog, sprint plan, and tagged releases per sprint. Stretch goals (non-blocking) include CSV export, basic analytics, and email-style notifications.

Risks

Time Compression – Two 3-week sprints demand strict work-in-progress limits and ruthless MVP focus.

Scope Creep – Ticketing systems can balloon (SLA timers, escalations, on-call). We will defer advanced features.

Integration/Tooling Debt – CI, tests, and seeding data must be right-sized to avoid pipeline churn.

Ambiguous Requirements – We’ll mitigate via crisp acceptance criteria and frequent backlog refinement.

Assumptions

Single-team deployment, small user base.

Modern stack (e.g., Node/Express + SQLite/Postgres + React/Vite or a monolith like Flask + Jinja).

GitHub used for issues, PRs, reviews, releases, and actions.

Success Criteria

Functional MVP deployed locally (and optionally containerized) with clear setup steps.

Backlog Delivery – At least 12 INVEST stories implemented or demonstrably planned with traceable status.

Quality Signals – Linting, basic unit tests, passing CI on PRs.

Process Evidence – Sprint goals, a retro note per sprint, and a tagged release per sprint.

User Value – A user can submit, track, and close a ticket; a tech can triage and resolve.

Why Agile
Agile lets us deliver value early (a usable ticket flow by Sprint 1), get feedback, then refine. The cadence—planning, standups (async notes), review, and retro—keeps scope tight and learning visible. This mirrors real-world IT/service contexts where needs shift and “done” means working software in users’ hands.

Two-Sprint Plan (8-week term)

Sprints are 3 weeks each: Sprint 1 (Weeks 2–4), Sprint 2 (Weeks 5–7). Week 1 = kickoff/setup; Week 8 = final polish/demo.

Sprint	Timeframe	Objectives	Planned Output
Sprint 1	Weeks 2–4	MVP ticket flow, roles, persistence, and basic UX.	Ticket CRUD; statuses (Open/In-Progress/Resolved/Closed); priorities; minimal auth (submitter vs. handler); seed data; README setup; tagged release v0.1.0.
Sprint 2	Weeks 5–7	Quality, reporting, and polish.	Comments on tickets; filtering/search; dashboard KPIs; CSV export; tests + CI hardening; accessibility pass; tagged release v1.0.0.
Personal Backlog (INVEST user stories)

Format: HLP-### — As a <role>, I want <capability> so that <benefit>.
Each includes acceptance criteria (AC).

HLP-001 – Create ticket

AC: Form with title, description, priority; on submit, ticket saved and listed as Open; validation errors shown inline.

HLP-002 – View ticket list

AC: List shows ID, title, status, priority, created date; paginated; newest first.

HLP-003 – View ticket details

AC: Detail page shows all fields plus history; deep linkable by ID.

HLP-004 – Update ticket status

AC: Allowed transitions: Open→In-Progress→Resolved→Closed; invalid transitions blocked with message.

HLP-005 – Assign ticket to handler

AC: Assign dropdown limited to handler role; audit log records who assigned and when.

HLP-006 – Minimal auth & roles

AC: Submitter can create/view own tickets; handler can view all, change status, assign; auth simulated if needed.

HLP-007 – Ticket comments

AC: Add comment text; shows author & timestamp; prevents empty comments.

HLP-008 – Filter & search

AC: Filter by status/priority/assignee; search by title/ID; filters persist via query params.

HLP-009 – Dashboard KPIs

AC: Cards for Open, In-Progress, Resolved (7d), Avg. time to close (rolling 14d).

HLP-010 – CSV export

AC: Export current filtered view to CSV; headers include ID, Title, Status, Priority, Assignee, Created, Closed.

HLP-011 – Validation & errors

AC: Required fields enforced; server errors show friendly message; 404 for missing ticket.

HLP-012 – Seed data & demo script

AC: Script seeds 10–20 tickets with varied statuses; README documents how to run.

HLP-013 – CI (lint + tests)

AC: PRs run lint and unit tests; failing checks block merge.

HLP-014 – Accessibility baseline

AC: Forms labeled; keyboard navigation works; color contrast meets WCAG AA for text.

(Add more as needed: email-style notifications, SLA tags, tag system, attachments, etc.)

Trends Note (past → present → near-future)

Past: Waterfall ticketing projects typically front-load requirements and design, producing late surprises and minimal user touchpoints until the end.
Present: Agile/DevOps emphasize short cycles, working increments, CI, trunk-based or short-lived branches, and continuous feedback via PR reviews and lightweight metrics. For HelpDesk Lite we’ll use user stories with AC, two tight sprints, and GitHub Actions for lint/tests.
Near-Future: Expand automation with conventional commits + semantic release, containerized dev environments (Dev Containers), and testable infrastructure (IaC). We’ll also explore basic observability (request logs, timings) and AI-assisted code review where it improves clarity—not as a crutch, but to enforce standards faster.

Getting Started (suggested)
# Monolith example (Node)
git clone <your-repo-url>
cd helpdesk-lite
npm install
npm run dev   # start local
