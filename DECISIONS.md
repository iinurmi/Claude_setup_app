# Architecture Decisions

Significant choices where future developers might ask "why did we do it this way?"

---

## 2026-03-01 — `/document` runs before `/commit`, not after

**Why:** Documentation (DECISIONS.md, CLAUDE.md) belongs in the same commit as the code it describes. Running `/document` first means the commit message can be derived directly from the git diff — no duplication of thought. Documenting after would split context across two commits.

**Rule:** Workflow order is always `/dev` → `/review` → `/document` → `/commit`.

---

## 2026-03-01 — `.claude/settings.local.json` excluded from git

**Why:** Despite holding project-relevant permission rules, the filename convention `*.local.*` signals machine-local config (same pattern as `.env.local`). Different developers may want different permission scopes. Gitignoring it prevents accidental commits and merge conflicts on a file that isn't truly shared state.

---

## 2026-03-01 — Named exports for all React components

**Why:** Consistent with TypeScript best practices and easier to tree-shake. Default exports make
refactoring harder (rename the file ≠ rename the import). Named exports also work better with
barrel files if we add them later.

**Rule:** All files in `components/` use named exports — no `export default`.
