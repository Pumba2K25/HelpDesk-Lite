Branch Policy

main is always deployable. Protected branch; no direct commits.

Use short-lived branches:

feat/<slug> – new feature (e.g., feat/ticket-comments)

fix/<slug> – bug fix (e.g., fix/status-transition-guard)

chore/<slug> – tooling, deps, configs

docs/<slug> – documentation only

Rebase or squash on merge (prefer Squash & Merge).

Pull Requests

Reference story IDs in title/description (e.g., HLP-007: add ticket comments).

Include: scope, screenshots (if UI), test notes, and checklist:

 Lint passes

 Unit tests added/updated

 README/usage updated if needed

Require ≥1 reviewer approval and passing CI.

Commit Messages (Conventional Commits)
feat: allow handlers to assign tickets (HLP-005)
fix: block invalid status transitions (HLP-004)
docs: update setup with seed script (HLP-012)
test: add API tests for ticket create (HLP-001)
chore: add eslint and prettier configs

Coding Standards

Keep functions small and purposeful; prefer pure logic where possible.

Server: validate inputs; never trust client fields for identity/role.

Client: basic a11y (labels, focus order, contrast).

Add unit tests for critical flows (ticket create, status update, permissions).

Issue Labels

story, bug, tech-debt, docs, good-first-issue, blocked, needs-review.

Definition of Done

AC met and demoable.

Tests passing in CI.

Docs updated (README or inline).

Peer reviewed and merged to main.

Included in next tagged release.

Optional: Quick Git Bootstrapping
echo "# HelpDesk Lite" > README.md
echo "# Contributing" > CONTRIBUTING.md
git init
git add .
git commit -m "chore: initial repo with README and CONTRIBUTING"
git branch -M main
git remote add origin <YOUR_GITHUB_REPO_URL>
git push -u origin main
