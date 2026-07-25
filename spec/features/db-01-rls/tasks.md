# Tasks: DB-01 - Final Atomic Implementation Checklist

- [x] 1. Create migration file `supabase/migrations/001_add_deleted_at_to_listings.sql` to add the `deleted_at` column to `listings`.
- [x] 2. Create pgTAP test file `supabase/tests/test_schema_listings.sql` to verify the `deleted_at` column existence and default state.
- [ ] 3. Execute `supabase/tests/test_schema_listings.sql` to verify Task 1 migration.
- [x] 4. Update migration file `supabase/migrations/001_add_deleted_at_to_listings.sql` to enable RLS and add basic `SELECT` policy.
- [x] 5. Create pgTAP test file `supabase/tests/test_rls_listings.sql` to verify RLS enablement and `SELECT` policy behavior (non-deleted records only).
- [x] 6. Execute `supabase/tests/test_rls_listings.sql` to verify Task 4.
- [x] 7. Update migration file `supabase/migrations/001_add_deleted_at_to_listings.sql` to add `INSERT` and `UPDATE` policies.
- [x] 8. Update pgTAP test file `supabase/tests/test_rls_listings.sql` to verify `INSERT` and `UPDATE` policies (ownership checks).
- [x] 9. Execute `supabase/tests/test_rls_listings.sql` to verify Task 7.
- [ ] 10. Update migration file `supabase/migrations/001_add_deleted_at_to_listings.sql` to add `DELETE` policy (prohibit direct deletion).
- [ ] 11. Update pgTAP test file `supabase/tests/test_rls_listings.sql` to verify `DELETE` policy fails.
- [ ] 12. Execute `supabase/tests/test_rls_listings.sql` to verify Task 10.
- [ ] 13. Update migration file `supabase/migrations/001_add_deleted_at_to_listings.sql` to add `updated_at` trigger.
- [ ] 14. Update pgTAP test file `supabase/tests/test_schema_listings.sql` to verify `updated_at` trigger functionality.
- [ ] 15. Execute `supabase/tests/test_schema_listings.sql` to verify Task 13.
- [ ] 16. Final documentation and cleanup of migration/test files.
