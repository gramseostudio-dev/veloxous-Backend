# Veloxous Backend Agent Instructions

## Core Workflow: Specification Driven Development (SDD)
Adhere strictly to `GUIA_MAESTRA_SDD.md` (FASE 0-5).
- **Phases:** 0-Initialization, 1-Constitution, 2-Specification, 3-Tasks, 4-Implementation, 5-Verification.
- **SDD Required:** All features must exist as specs in `/spec/` and docs in `/docs/`.
- **Atomic Tasks:** Every task in `tasks.md` MUST conclude with a verifiable test.

## Domain & Constraints
- **Active Focus:** Issue #7 (DB-01: RLS for Marketplace Listings).
- **Scope:** PostgreSQL RLS, PL/pgSQL triggers, and pgTAP testing in `backend/supabase/`.
- **Prohibited:** Do NOT modify Express/Bun routes or Stellar SDK integrations.
- **Verification:** Use **pgTAP** for all database security changes.

## Environment & Commands
- **Project Root:** `./proyecto/veloxous-Backend-main/`
- **Verification:** Always verify changes with `pgTAP` before proceeding to the next task.
- **Context:** Use `context7` MCP for Supabase/Postgres best practices.

## Agent Protocol
- **Trust the Plan:** If a task is not in `plan.md` or `tasks.md`, stop and update specs.
- **Atomic Progress:** Do NOT batch tasks; implement one, verify, and pause for feedback.
- **Documentation:** Maintain `docs/sessions/` for notes and `docs/changelogs/` for final PR-ready reports.
