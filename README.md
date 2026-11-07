# 🐰 Reading Rabbit

A playful reading-practice web app for young learners: students pick their name, read their level's stories, record their voice, and earn teacher stars.

## Features

- 🎨 Child-friendly design (bright colors, animations, sounds, confetti)
- 🔐 Class-code gate that keeps student names & recordings private
- 👧 Student flow: pick level → pick name → 8 stories per level (24 passages, questions never shown)
- 🎤 Per-story voice recording (MediaRecorder, max 3 min) — saved in the database, playable anytime, can be deleted or re-recorded
- ⭐ Teacher evaluation: 1–5 stars + written feedback note per recording
- 🗄️ PostgreSQL (works with the free Neon tier) via Prisma

## Tech stack

Next.js 16 (App Router) · TypeScript · Tailwind CSS 4 · shadcn/ui · Prisma · PostgreSQL

## Local development

```bash
bun install                 # or: npm install
cp .env.example .env        # then edit DATABASE_URL + SCHOOL_CODE
bun run db:push             # create tables
bun run db:seed             # add students + stories
bun run dev                 # start on http://localhost:3000
```

Default class code: `1234` (change it in `.env`).

## Deployment (free)

See the deployment guide (دليل النشر) for the full Arabic walkthrough:
GitHub → Vercel (free hosting) + Neon (free PostgreSQL).

Quick summary:

1. Push this repository to GitHub
2. Create a free database at neon.tech and copy the connection string
3. Import the repo on Vercel, add environment variables `DATABASE_URL` and `SCHOOL_CODE`
4. Create the tables + seed once against Neon (`prisma db push` + seed)
5. Deploy — done! 🚀
