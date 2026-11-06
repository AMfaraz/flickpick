# Progress

Last updated: 2026-11-06

## Project
- Name: **FlickPick** (technical name: `flickpick`)
- Website: Movie Watchlist (TMDB API for movie data + own PostgreSQL for users, watchlist and reviews)
- Folder: `E:\IDE workspace\React\flickpick` (moved from `blogapp` on 2026-11-06)
- Roadmap: [roadmap.md](roadmap.md). ✅ **Approved 2026-11-06.**

## Current phase: Phase 1 — Project ki buniyad + Web basics (next: Lesson 1)

### Setup checklist (Phase 0)
- [x] Node.js **v26.13.0** (LTS), npm **11.20.0**, Git **2.56.0** (verified from their screenshot)
- [x] Antigravity installed
- [x] Extensions: ESLint (`dbaeumer.vscode-eslint`), Prettier (`esbenp.prettier-vscode`),
      Tailwind CSS IntelliSense (`bradlc.vscode-tailwindcss`)
- [x] GitHub account + 2FA (already had both)
- [—] Private (noreply) email: skipped by the student's choice; uses their normal email
- [x] Git config: `user.name`, `user.email` set (verified from screenshot; values not recorded here)
- [x] Git config: `init.defaultBranch main` (student first thought it creates a branch; now understands
      it is only a setting for future repos)
- [x] DevTools task: answered correctly. Changes were local, and refresh loads the original page again.
      Introduced the word "DOM".
- [—] `core.editor`: skipped on purpose; we use `git commit -m "..."`. Vim escape tip given.
- [—] `C:\dev`: replaced; projects live in `E:\IDE workspace\React\`

### How the website was chosen
- Round 1: 1) Blog Platform, 2) Task Manager, 3) Mini E-commerce.
- Round 2 (student wanted public APIs): 4) Movie Watchlist ✅ chosen, 5) Recipe Hub, 6) ShopLite store,
  7) Portfolio + Blog + GitHub API (kept as a later side project).

### Next steps
1. ~~Student approves the roadmap.~~ Approved 2026-11-06.
2. Lesson 1 is split in two:
   - **1A ← we are here.** First sent as one long message; the student found it too big, so it is being
     re-taught in 3 parts, one per "next": (1) concept + RN bridge + create project; (2) run dev server +
     open in editor + metadata code + industry + alternatives; (3) mistakes + task + git.
     **Part 1 done (project created 2026-11-07: next 16.4.5, react 19.3.0, Tailwind via
     `@tailwindcss/turbopack`, commit 680886c "Initial commit from Create Next App"). Part 2 sent.**
     npm audit: 8 moderate in dev-only ESLint chain (minimatch via typescript-eslint); `--omit=dev` = 0. Part 2 done (metadata title changed, verified). **Part 3 sent:** h1 task + first own commit.
     Told the student NOT to run `npm audit fix --force` (it would downgrade eslint-config-next to 15.5.29). Content: `create-next-app .` with **"customize settings"**
     (same as recommended but with `src/` = Yes), `npm run dev`, change `metadata` in `app/layout.tsx` (given) and the `<h1>` in
     `app/page.tsx` (their task), then their first own commit. When they say done, review the real files
     in the folder.
   - **1B:** tour of the actual generated files, create + connect the GitHub repo (HTTPS vs SSH),
     check `.gitignore`, push, README.

### Open issues
- ~~Old empty `blogapp` folder~~ Deleted by the student on 2026-11-06.
- Project path contains a space (`IDE workspace`). Usually fine with npm and Next.js; remember it
  if a tool ever fails on paths.
- ~~TypeScript version~~ Resolved: create-next-app 16.4.5 writes `typescript: "^5"`, so the project gets
  TS 5.x, not 7.
