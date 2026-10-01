# Maciej Czyż

**AI Workflow & Automation Engineer**

I build software through AI: I design, orchestrate and verify the work of AI agents (Claude Code) instead of writing
code by hand. My repositories are private — this page describes what is in them.

## Skolteka — school-management SaaS · [skolteka.com](https://skolteka.com)

A multi-tenant SaaS for running a school, full stack: Next.js, Supabase / PostgreSQL, TypeScript. Developed since
April 2025: ~2,280 commits and 300+ completed features. Pre-launch, designed from the experience of a pilot at a language school.

- School panel: students, teachers, parents, groups, lessons, calendar, rooms and buildings, branches, billing
- Separate portals for parents, students and the platform operator
- Self-service school sign-up with a public page under its own subdomain
- Polish and English interface; 57 database tables
- Automated quality gates on every commit (including RLS security checks in migrations) and error monitoring
  (Sentry)

## The fleet — AI agent orchestration environment for software development

Built since May 2026, through AI, out of the needs of daily work. A central host coordinates Claude agents with
defined roles; I set the direction and approve the critical steps. I develop Skolteka on it, and the fleet develops
itself. My feature registry, kept since February 2026, holds 900+ features, nearly 700 of them completed — 400+
since May 2026, when I started building the fleet, most of them for the fleet itself.

- **Roles.** A coordinator that talks to me and dispatches the work; builders that work end to end or in isolated
  git worktrees; a merger that applies database migrations and verifies the build; a critic that challenges research
  findings; a tester that checks the live production site in a browser.
- **Review before and after the code.** At normal and careful rigour a plan is reviewed before code is written; the
  finished code is reviewed again, with at least one reviewer who has not seen the plan. Database, auth, security and
  backend changes can never take the light path, so they always get the full review.
- **The host, not a model, owns production.** Agents don't push: they commit and ask the host to ship. The host
  checks that the commit is still the branch tip, ships one change at a time from a queue, checks the health of
  production on Vercel before pushing, and watches the deploy until it is live.
- **Status from evidence.** "Shipped" and "verified" are recorded by the host, from the deploy result and the
  tester's report — never self-reported by the agent that did the work.
- **Fleet tools by role.** Each agent gets only the fleet tools its role allows, from the host's internal MCP
  server: messaging, launching agents, merge, ship, feature tracking.
- **Keeps itself running.** It wakes agents after a usage limit resets, steers context compaction before a session
  overflows, diagnoses failed turns and git failures, nudges idle agents, and checks itself on startup for failures
  met in practice.
- **Dashboard.** A live view of every agent, chat with any of them, launch presets, and one hold on all production
  ships.

## Before

- **2024** — freelance (B2B) for an automation firm, at several of its clients, language schools: Airtable,
  Make.com, Bitrix24, Notion, two-way API synchronization. Since 2024, an unpaid pilot of my own system at a
  language school.
- **2009–2015** — software tester and analyst: accounting software for municipal offices, test automation, Oracle
  SQL, process analysis.

2,500+ commits in the last year (private repositories) · [CV](https://cv.moryszon.com/)
