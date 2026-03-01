# My App

A full-stack web application built with Next.js, TypeScript, Supabase, and Tailwind CSS.

## Getting Started

### Prerequisites

- Node.js v20+ — [download here](https://nodejs.org/en/download)
- A [Supabase](https://supabase.com) account (free)
- A [GitHub](https://github.com) account

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
   cd YOUR_REPO
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Set up environment variables:

   ```bash
   cp .env.example .env.local
   # Open .env.local and fill in your Supabase credentials
   ```

4. Start the development server:

   ```bash
   npm run dev
   ```

5. Open [http://localhost:3000](http://localhost:3000) in your browser.

## Available Commands

| Command              | Description              |
| -------------------- | ------------------------ |
| `npm run dev`        | Start development server |
| `npm run build`      | Create production build  |
| `npm run lint`       | Check for code issues    |
| `npm run format`     | Auto-format all files    |
| `npm run type-check` | Check TypeScript types   |

## Tech Stack

- **Framework**: [Next.js 15](https://nextjs.org) — App Router
- **Language**: TypeScript
- **Database + Auth**: [Supabase](https://supabase.com)
- **Styling**: [Tailwind CSS](https://tailwindcss.com)

## Project Conventions

See [CLAUDE.md](./CLAUDE.md) for coding conventions, architecture decisions, and Claude Code instructions.

## Deployment

Connect this repository to [Vercel](https://vercel.com) — it auto-deploys on every push to `main`.
Add your environment variables in the Vercel project dashboard under Settings > Environment Variables.
