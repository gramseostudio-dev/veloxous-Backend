# Roadmap: Issue #7 (DB-01: RLS for Marketplace Listings)

## Phase 1: Preparation & Specification
- [ ] Define precise RLS requirements in `spec/features/db-01-rls/spec.md`.
- [ ] Map out affected tables (`listings`, `bids`, `escrow`).

## Phase 2: Implementation (Database Level)
- [ ] Develop SQL migration for `deleted_at` soft-deletion support on target tables.
- [ ] Implement RLS policies for:
    - `SELECT` (read restrictions).
    - `INSERT` (authenticated user check).
    - `UPDATE` (ownership check).
    - `DELETE` (disable or replace with `deleted_at` update).
- [ ] Implement Triggers for automated status updates synced with blockchain events.

## Phase 3: Verification (Security Testing)
- [ ] Setup `pgTAP` environment in `backend/supabase/`.
- [ ] Write unit tests for RLS policies (positive and negative cases).
- [ ] Validate triggers using pgTAP.

## Phase 4: Finalization
- [ ] Document final policy structures.
- [ ] Generate changelog for Issue #7.
