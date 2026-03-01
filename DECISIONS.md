# Architecture Decisions

Significant choices where future developers might ask "why did we do it this way?"

---

## 2026-03-01 — Supabase 2025 API key format adopted

**Why:** Supabase migrated to a new key format in 2025 (`sb_publishable_...` / `sb_secret_...`),
deprecating the legacy `anon` and `service_role` keys. We aligned immediately to avoid a forced
migration later and to stay compatible with the latest `@supabase/ssr` client.

**Impact:**
- Env var `NEXT_PUBLIC_SUPABASE_ANON_KEY` → `NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY`
- Env var `SUPABASE_SERVICE_ROLE_KEY` → `SUPABASE_SECRET_KEY`
- Both `lib/supabase/client.ts` and `lib/supabase/server.ts` updated
- Old `.env.example` deleted; new one should use the updated names

---

## 2026-03-01 — Named exports for all React components

**Why:** Consistent with TypeScript best practices and easier to tree-shake. Default exports make
refactoring harder (rename the file ≠ rename the import). Named exports also work better with
barrel files if we add them later.

**Rule:** All files in `components/` use named exports — no `export default`.
