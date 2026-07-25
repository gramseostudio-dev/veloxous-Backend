# Spec: DB-01 - RLS for Marketplace Listings

## Overview
Implement PostgreSQL RLS to protect marketplace listing data. Ensure data integrity, privacy, and proper access control.

## Requirements

### 1. Soft Deletion
- Add `deleted_at` (TIMESTAMPTZ) column to `listings` table.
- Implement an `UPDATE` policy to prevent permanent deletion.
- Update `SELECT` policies to filter out records where `deleted_at` IS NOT NULL.

### 2. RLS Policies
- `SELECT`: Users can view active listings only.
- `INSERT`: Authenticated users can create listings.
- `UPDATE`: Only the owner of the listing can modify it.
- `DELETE`: Prohibit direct deletion; enforce soft-delete via `deleted_at`.

### 3. Triggers
- Implement a trigger to automatically update `updated_at` on modification.
- (Future) Trigger to sync status changes with Stellar contract events (if applicable).

### 4. Verification (pgTAP)
- Write tests to verify:
  - Users cannot read other users' private data (if applicable).
  - Owners can update their listings.
  - Non-owners cannot update listings.
  - Soft-deletion works as expected (record exists but is filtered).
