# Changelog

All notable changes to this project will be documented here.
Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/)

## [Unreleased]

### Added
- GitHub remote configured; `master` pushed to `https://github.com/iinurmi/Claude_setup_app.git`
- `components/HelloWorld.tsx` — smoke-test component, validates named export + Tailwind patterns end-to-end
- `.claude/commands/` — custom slash commands for CTO workflow: `explore`, `plan`, `dev`, `review`, `document`, `create-issue`, `learning-opportunity`, `commit`
- `.claude/commands/commit.md` — guided commit workflow: quality gate → diff review → CHANGELOG check → stage → commit message → optional push

### Changed
- `app/page.tsx` — replaced inline placeholder with `<HelloWorld />` component
- Supabase env var names updated to 2025 format:
  - `NEXT_PUBLIC_SUPABASE_ANON_KEY` → `NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY`
  - `SUPABASE_SERVICE_ROLE_KEY` → `SUPABASE_SECRET_KEY`
- `CLAUDE.md` — added Role, How to Respond, and Workflow sections; updated env var names
- `.gitignore` — added `issues/` (local backlog) and `.claude/settings.local.json` (machine-local Claude permissions)

### Removed
- `.env.example` — deleted; superseded by updated env var names
