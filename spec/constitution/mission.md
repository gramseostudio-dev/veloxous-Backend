# Mission: Database Security Hardening (Issue #7)

## Objective
To implement robust Row Level Security (RLS) policies within the Supabase PostgreSQL database to ensure that Marketplace Listings, Bids, and Escrow-related data are protected from unauthorized access, modification, and deletion.

## Core Goals
1.  **Access Control:** Restrict data read/write access based on user roles and ownership.
2.  **Integrity:** Use PostgreSQL Triggers to ensure data consistency between the API layer and the blockchain state.
3.  **Protection:** Implement soft-deletion via `deleted_at` timestamps to prevent permanent loss of marketplace records.
4.  **Verification:** Implement a comprehensive pgTAP test suite to guarantee that RLS policies are enforced correctly and are regression-proof.
