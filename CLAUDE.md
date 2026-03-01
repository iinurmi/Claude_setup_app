# Claude Code Project Instructions

## Project Overview

Full-stack web application built with Next.js 15, TypeScript, Supabase, and Tailwind CSS.
This is a learning project for a beginner developer.

## Tech Stack

- **Framework**: Next.js 15 (App Router)
- **Language**: TypeScript (strict mode)
- **Database**: Supabase (PostgreSQL + Auth)
- **Styling**: Tailwind CSS v4
- **Package Manager**: npm
- **Code Quality**: ESLint + Prettier

## Project Structure

- `app/` - Next.js App Router pages and layouts
- `app/api/` - API route handlers (backend endpoints)
- `components/` - Reusable React components
- `lib/` - Utility functions, Supabase client, helpers
- `types/` - TypeScript type definitions
- `public/` - Static assets (images, fonts, icons)
- `supabase/` - Database migrations and seed data

## Development Commands

```bash
npm run dev         # Start development server (localhost:3000)
npm run build       # Production build
npm run lint        # Run ESLint
npm run lint:fix    # Auto-fix ESLint issues
npm run format      # Format all files with Prettier
npm run type-check  # Run TypeScript compiler check (no emit)
```

## Coding Conventions

- Use TypeScript strict mode — never use `any` type
- Prefer named exports over default exports for components
- Use `async/await` over `.then()` chains
- Component files: PascalCase (e.g., `UserCard.tsx`)
- Utility files: camelCase (e.g., `formatDate.ts`)
- Use Tailwind utility classes — avoid writing custom CSS unless absolutely necessary
- All database interactions go through `lib/supabase/` helper functions, not directly in components

## Commit Message Convention

Use Conventional Commits:

- `feat:` new feature
- `fix:` bug fix
- `docs:` documentation changes
- `refactor:` code restructure without behavior change
- `chore:` maintenance (deps, config)
- `style:` formatting only

## Environment Variables

Required variables (get from Supabase dashboard > Settings > API):

- `NEXT_PUBLIC_SUPABASE_URL` - Your Supabase project URL
- `NEXT_PUBLIC_SUPABASE_ANON_KEY` - Your Supabase anonymous key
- `SUPABASE_SERVICE_ROLE_KEY` - Server-side only, never expose to client

NEVER commit `.env.local` to git. It is already in .gitignore.
See `.env.example` for the template.

## What NOT To Do

- Do not modify `supabase/migrations/` files that have already been applied to production
- Do not use `var` — always use `const` or `let`
- Do not make direct database calls in React components — use Server Components or API routes
- Do not add `// @ts-ignore` comments — fix the type error properly
- Do not use `any` type — use `unknown` and narrow the type if needed

## Database Schema Changes

All database changes must be done via Supabase migrations in `supabase/migrations/`.
Run `npx supabase migration new <name>` to create a new migration file.

## Testing Approach

- Test API routes via browser or a REST client (e.g., Thunder Client VSCode extension)
- Test UI components visually in the dev server at localhost:3000
- Use browser DevTools Console for debugging client-side errors
