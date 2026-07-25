# Tech Stack - Veloxous Backend (Security Focus)

## Core Technologies
- **Runtime:** Node.js (via Bun)
- **Framework:** Express.js
- **Database:** Supabase (PostgreSQL)
- **Blockchain Integration:** @stellar/stellar-sdk (Soroban)

## Database & Security Layer (Focus for Issue #7)
- **Engine:** PostgreSQL (hosted via Supabase)
- **Security Mechanism:** Row Level Security (RLS)
- **Testing Framework (Security):** pgTAP (PostgreSQL Transactional Application Testing)
- **Automation:** SQL Migration files (to be structured in `backend/supabase/migrations/`)

## Infrastructure
- **CI/CD:** GitHub Actions (to be configured for RLS/pgTAP validation)
- **Environment:** Node.js + Bun
