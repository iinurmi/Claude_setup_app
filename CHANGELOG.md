# Changelog

All notable changes to this project will be documented here.
Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/)

## [Unreleased]

### Added
- `components/HelloWorld.tsx` — smoke-test component, validates named export + Tailwind patterns end-to-end
- `.claude/commands/` — custom slash commands for CTO workflow (cto, plan, dev, explore, review, document, create-issue, learning-opportunity)

### Changed
- `app/page.tsx` — replaced inline placeholder with `<HelloWorld />` component
- Supabase env var names updated to 2025 format:
  - `NEXT_PUBLIC_SUPABASE_ANON_KEY` → `NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY`
  - `SUPABASE_SERVICE_ROLE_KEY` → `SUPABASE_SECRET_KEY`
- `CLAUDE.md` — added Role, How to Respond, and Workflow sections; updated env var names
- `.gitignore` — added `issues/` (local issue tracking directory)

### Removed
- `.env.example` — deleted; superseded by updated env var names
