# Plan: Implementation Strategy for DB-01 RLS

## Approach
1.  **Preparation**: Create a new Supabase migration file.
2.  **Schema Update**: Apply soft-deletion column (`deleted_at`) to the `listings` table.
3.  **Policy Layer**:
    - Enable RLS on `listings` table.
    - Define granular policies (`SELECT`, `INSERT`, `UPDATE`, `DELETE`).
4.  **Security Testing**: Develop a dedicated pgTAP test suite to validate all RLS policies.

## Architectural Steps
1.  **Migration (`001_add_soft_delete_and_rls.sql`)**:
    - `ALTER TABLE listings ADD COLUMN deleted_at TIMESTAMPTZ;`
    - `ALTER TABLE listings ENABLE ROW LEVEL SECURITY;`
    - Create individual `CREATE POLICY` statements.
2.  **pgTAP Suite (`tests/pgtap/rls_listings.sql`)**:
    - Use `plan()` to define test count.
    - Use `performs_as()` to simulate different users (e.g., authenticated, anonymous, owner, non-owner).
    - Assert policy behavior using `is()` and `ok()`.
