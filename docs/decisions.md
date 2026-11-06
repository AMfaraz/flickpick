# Decisions log

| Date | Topic | Decision | Why |
|---|---|---|---|
| 2026-11-06 | Runtime | Node.js **26 LTS** (v26.13.0) | Latest LTS. Next.js needs ≥ 20.9. Node 27 is still alpha. |
| 2026-11-06 | Package manager | **npm** | Comes with Node; simplest for a beginner. pnpm mentioned as the alternative. |
| 2026-11-06 | Editor | **Antigravity** | Student's choice. VS Code fork; extensions from Open VSX. |
| 2026-11-06 | Language | **TypeScript** | From the brief. No extra extension needed (built into the editor). |
| 2026-11-06 | Framework | **Next.js App Router** | From the brief. Exact Next.js version: confirm in `package.json` after creating the project. |
| 2026-11-06 | Styling | **Tailwind CSS v4**, CSS basics first | `create-next-app` default. v4 uses `@import "tailwindcss";`, no `tailwind.config.js` by default (old tutorials show v3 setup). |
| 2026-11-06 | Lint / format | **ESLint + Prettier** | Industry default. ESLint understands TS via typescript-eslint (set up by Next.js config). Biome = alternative. Tools are installed **per project**, never globally. |
| 2026-11-07 | Folder structure | **`src/` directory** (code lives in `src/app/...`) | Student's choice. Equally common in industry; `@/*` alias points to `./src/*`. All lesson paths use `src/app/...`. |
| 2026-11-07 | Agent feedback | **Off** (answered No in create-next-app) | Student's choice (privacy). Not needed for learning. |
| 2026-11-07 | React Compiler | **Off** | Student wants to learn `useMemo` / `useCallback` / `React.memo` by hand first. Can be enabled later with `reactCompiler: true`. |
| 2026-11-06 | Git editor | **None set** | Student doesn't want the Antigravity CLI. Use `git commit -m`. |
| 2026-11-06 | Website | **Movie Watchlist**: TMDB API for movie data + own PostgreSQL for users, watchlist and reviews | Student's choice. Real API integration with a key (env vars, server-only secrets), plus own backend. TMDB is non-commercial use only, with attribution required. |
| 2026-11-06 | Database | **PostgreSQL** | Student agreed. Most common in the Next.js world; close to the MySQL they saw in phpMyAdmin. ORM (Prisma vs Drizzle) and hosting: decide in the database lesson, after checking official docs and pricing. |
| 2026-11-06 | Git email | **Normal email** (not GitHub noreply) | Student's choice. Told them: it shows in public commits; it can be switched later, but old commits keep the old email. Must match an email on their GitHub account. |
| 2026-11-06 | Project name | **FlickPick** (technical name `flickpick`) | Student's choice from 6 suggestions. "Flick" = movie (slang), "pick" = choose. |
| 2026-11-06 | Project location | `E:\IDE workspace\React\flickpick` (was `blogapp`) | Student's choice of parent folder; renamed after picking the name. |
| 2026-11-06 | Notes folder | `docs/` (renamed from `md/`) | `create-next-app` allows `docs` in the target folder; `docs/` is also the usual place for project documentation. |

## Open questions
- Roadmap approval
- ORM (Prisma vs Drizzle), auth library (Better Auth vs Auth.js), DB hosting: decide in Phase 4

## Verified facts (checked 2026-11-06)
- **npm registry, `latest` versions:** next 16.4.5 · react 19.3.1 · create-next-app 16.4.5 · tailwindcss 4.3.4 ·
  typescript 7.0.2 · better-auth 1.7.18 · next-auth 4.24.15 · drizzle-orm 0.45.4 ·
  prisma 8.0.0-rc.30 (the `latest` tag points to a release candidate, so check this before choosing).
- **nodejs.org/en/about/previous-releases:** v26 "Lithium" = latest LTS (v26.13.0); v24 and v22 also LTS;
  v27 = alpha. From Node 27 the release cycle becomes annual.
- **nextjs.org/docs/app/getting-started/installation** (updated 2026-10-02):
  - Minimum Node 20.9.
  - `npx create-next-app@latest` recommended defaults: TypeScript, ESLint, no React Compiler, Tailwind CSS,
    no `src/` directory, App Router, Cache Components, `AGENTS.md`; import alias `@/*`.
  - Turbopack is the default bundler.
  - Since Next.js 16, `next build` no longer runs the linter (use the `lint` script).
- **dummyjson.com/docs:** resources are products, carts, recipes, users, posts, comments, todos, quotes and auth
  (login, current user, refresh token; Bearer token). `limit`/`skip` pagination; search for products, recipes,
  posts and users; product categories and `sortBy`/`order`. No API key step is described.
  **Add, update and delete are simulated and not saved on the server** (stated on the products docs page).
- **developer.themoviedb.org (getting started + FAQ):** you need a TMDB account, then request an API key from
  account settings after accepting the terms. Free for **non-commercial** use with attribution; commercial use
  needs a license. Attribution: an approved TMDB logo (less prominent than yours), plus the notice "This product
  uses the TMDB API but is not endorsed or certified by TMDB.", placed in an About or Credits section.
  Rate limiting exists (no numbers on that page).
- **create-next-app v16.4.5 source (checked 2026-11-07):**
  - `templates/index.ts`: react / react-dom `19.3.0`, next = its own version, typescript `^5`, @types/node `^20`,
    @types/react(-dom) `^19`, tailwindcss `^4`, eslint `^9`, eslint-config-next = same as next.
    Scripts: `dev`, `build`, `start`, `lint` (`eslint`). Cache Components adds `cacheComponents: true` and
    `partialPrefetching: true` to `next.config.ts`.
  - `helpers/git.ts`: if git is installed and the folder is not already in a repo, it runs `git init`, `git add -A`
    and commits "Initial commit from Create Next App" (uses `init.defaultBranch` if set, else `main`).
  - `templates/app-tw/ts/app/layout.tsx`: Geist fonts, `metadata` title "Create Next App",
    `RootLayout({ children }: LayoutProps<"/">)`.
  - `templates/app-tw/ts/app/page.tsx`: `<h1>` "To get started, edit the `page.tsx` file.", plus links to
    Templates, Learning, Deploy Now and Documentation.
- **create-next-app recommended defaults (as seen by the student, 2026-11-07):** TypeScript, ESLint, No React
  Compiler, Tailwind CSS, No src/ directory, App Router, Cache Components, AGENTS.md, **Agent feedback**.
- **nextjs.org/docs/app/guides/ai-agents** (updated 2026-10-15): Next.js 16.2+ bundles version-matched docs in
  `node_modules/next/dist/docs/`; `AGENTS.md` (managed block re-added by `next dev`) points agents there.
  **Agent feedback** (`experimental.agentFeedback`, added in v16.4.0, turned on by the recommended defaults):
  a detected coding agent collects anonymized Next.js issues and opens a review form in the browser, and
  **nothing is sent until the user clicks "Send feedback"**. It needs Next.js telemetry on and doesn't run in CI.
  To turn it off, remove the option or set it to `false` (turning telemetry off also removes it).
- **create-next-app `helpers/is-folder-empty.ts`:** allowed entries in a non-empty target folder include
  `.claude`, `.cursor`, `.git`, `.gitattributes`, `.gitignore`, `.idea`, `.vscode`, `.zed`, `LICENSE`, `docs`,
  `mkdocs.yml`, `Thumbs.db`, `.DS_Store`, and some log files. Anything else counts as a conflict.
