# TPM Command Center — Aparajita Sahay

**Live dashboard:** [View on GitHub Pages](https://aparajitasahay.github.io/tpm-dashboard)
**Full blog post:** [How I use Claude + Jira MCP as a TPM](https://medium.com/@aparajitasahay) *(link to your Medium/LinkedIn post)*

---

## What this is

A Power BI-style interactive program dashboard built from two live Jira boards —
**Project UNIFY** (Enterprise Identity Federation, 15M subscribers, 3 global regions)
and **Project AAIG** (AI Agent Identity Gateway) — using the Claude + Jira MCP workflow.

This is a portfolio artifact demonstrating how a TPM can use AI-assisted tooling
to accelerate program coordination while keeping human judgment as the final gate.

---

## The workflow

```
Jira (source of truth)
        ↓
Claude reads board via Jira MCP connector
        ↓
Claude drafts: sprint schedule · risk flags · dependency map
              status report · Agile specs · trade-off matrices
        ↓
TPM reviews every output before anything posts to Jira
        ↓
Validated output posted as Jira comments / exported to this dashboard
```

**The key assumption:** Jira is well-maintained. Tickets have descriptions,
acceptance criteria, and correct status. Claude amplifies a good board — it
cannot rescue a bad one.

---

## Dashboard panels

| Panel | What it shows | TPM skill demonstrated |
|---|---|---|
| Program health | KPI cards, issue breakdown charts, full issue list with filters | Situational awareness |
| Roadmap | Gantt timeline Jun → Sep 30, sprint plan by milestone | Delivery planning |
| Risk register | 5 risks ranked Critical/High/Medium, expandable with mitigation | Proactive risk management |
| Dependencies | 5 within-project chains + 1 cross-program gate (AAIG → UNIFY) | Cross-functional thinking |
| Status report | Copy-ready weekly brief for leadership, switchable by project | Executive communication |
| How it works | Claude + Jira MCP workflow diagram, trust model table | AI-assisted TPM practice |

---

## The trust model

Not all Claude outputs are equal. Here's where the human gate sits:

**Claude does autonomously:**
- Read any ticket or board
- Draft comments, specs, and reports
- Build dashboards and visualizations
- Flag risks, dependencies, and missing criteria
- Refuse duplicate writes (idempotency check)

**TPM reviews before posting to Jira:**
- Risk mitigation comments on live tickets
- Agile acceptance criteria drafts
- Trade-off matrices (e.g. P0 latency options)
- Any comment on a P0 or blocker ticket
- Status report content

**Requires a separate explicit decision:**
- Writing ticket fields directly (status, priority, assignee)
- Creating new tickets
- Modifying in-field acceptance criteria
- Assigning tickets to specific people

This boundary isn't permanent — it's a trust level that evolves as the workflow
matures and confidence in the output quality grows.

---

## Data sources

- **UNIFY board:** 12 issues — 1 Epic, 5 Stories, 4 Tasks, 2 Bugs
  (`aparajitasahay.atlassian.net/jira/software/projects/UNIFY`)
- **AAIG board:** 6 issues — 3 Epics, 3 Stories
  (`aparajitasahay.atlassian.net/jira/software/projects/AAIG`)
- Data read via Claude's Jira MCP connector on Jun 29, 2026
- All ticket keys, titles, dates, and labels are real — not synthetic

---

## Why two projects?

A single board shows task management. Two boards show program management.

The cross-program dependency — AAIG's gateway proxy (AAIG-2) must be stable
before UNIFY can activate VaultID SSO (UNIFY-2) — is the most important
signal in this portfolio. It shows a TPM who holds the inter-workstream view
that no individual team member can hold from inside their own work.

One program. Two workstreams. One go-live date. That's the real job.

---

## How to deploy (GitHub Pages, 2 minutes)

1. Fork or clone this repository
2. Go to **Settings → Pages → Source → Deploy from branch → main → / (root)**
3. GitHub will publish at `https://[your-username].github.io/tpm-dashboard`
4. Update the live URL link in this README and in your blog post

---

## Tech stack

Plain HTML, CSS, and JavaScript. No framework, no build step, no dependencies
except Chart.js (loaded from cdnjs). The entire dashboard is one self-contained
file — `dashboard.html` — that works offline and embeds anywhere.

---

## Contact

**Aparajita Sahay** — Technical Program Manager
[LinkedIn](https://linkedin.com/in/aparajitasahay) · [Jira instance](https://aparajitasahay.atlassian.net)
