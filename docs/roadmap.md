# FlickPick: Roadmap

**Status:** ✅ Approved (2026-11-06). Student beech mein approach badalne ka keh sakta hai (dekhein mentor-notes.md, "Teaching agreements").

**FlickPick** ek movie watchlist website hai. Movies ka data **TMDB API** se aata hai, aur users signup karke
apni **watchlist** banate hain aur **reviews/ratings** likhte hain, jo hamare apne **PostgreSQL** database mein save hote hain.

## Versions (jo code assume karega)
| Cheez | Version | Note |
|---|---|---|
| Node.js | 26 LTS (v26.13.0) | Installed ✅ |
| Next.js | 16.4.x | npm par latest 16.4.5 (2026-11-06) |
| React | 19.3.x | npm par latest 19.3.1 |
| Tailwind CSS | 4.3.x | v4 setup (`@import "tailwindcss";`) |
| TypeScript | Jo `create-next-app` install kare | npm par latest 7.0.2 hai, Lesson 1 mein compatibility check karenge |
| ORM, Auth, DB hosting | Phase 4 mein decide | Us waqt official docs aur free plans check karke |

**Budget: zero.** Sirf free tools aur free plans use honge.

**Andaza:** ~33 lessons. Roz 1–1.5 ghanta ke hisaab se, aur kuch lessons 2 sittings lenge, to takreeban **2–3 mahine**.
Ye sirf andaza hai, jaldi ki koi zaroorat nahi.

---

## Phase 0: Setup ✅
Node, npm, Git, Antigravity + extensions, GitHub + 2FA, Git config, DevTools aur DOM.

## Phase 1: Project ki buniyad + Web basics
**Phase ke end mein:** GitHub par FlickPick ka repo, aur ek styled static home page (header, hero section, footer).
1. **Project banana:** `create-next-app`, folders aur `package.json` ka tour, `npm run dev`, GitHub repo connect karna (HTTPS vs SSH), `.gitignore`, pehla commit + push, README
2. **Web kaise chalta hai:** URL, request/response, HTML/CSS/JS ka kaam, DOM, DevTools ka Network tab
3. **Semantic HTML:** home page ka dhancha (`header`, `nav`, `main`, `section`, `footer`, `button` vs `a`). RN ke `View`/`Text` se farq.
4. **CSS basics se Tailwind tak:** box model, Flexbox (web vs RN defaults), units, mobile-first responsive design
5. **Team workflow:** Prettier + ESLint (format on save), Conventional Commits, pehli feature branch + Pull Request

## Phase 2: React on the web + App Router (nakli data ke saath)
**Phase ke end mein:** saare pages chal rahe hain (Home, Search, Movie detail, Watchlist, About), abhi hardcoded data ke saath.

6. **Components + props + TypeScript types:** `MovieCard`, `MovieGrid`, lists aur `key`
7. **Layouts aur navigation:** root layout, pages, `<Link>`. React Navigation vs file-based routing.
8. **Dynamic routes:** `/movies/[id]`, `notFound()`, 404 page
9. **Server vs Client Components:** `"use client"` kab aur kyun; events, `useState`, search form, refs
10. **URL as state:** `/search?q=batman` (`searchParams`)

## Phase 3: TMDB API (asli data)
**Phase ke end mein:** asli movies: trending, search, details aur posters, sab TMDB se.

11. **API key aur secrets:** TMDB account, `.env.local`, environment variables, key ko browser se chhupana, pehla server-side `fetch`
12. **API client:** `lib/tmdb.ts`, API response ke TypeScript types, error handling
13. **Rendering strategies:** SSR, SSG, ISR, CSR; trending page par caching + revalidation (Next.js 16 ka caching model, docs dekh kar)
14. **Movie detail page:** TMDB data, SEO (`generateMetadata`), `next/image` se remote posters
15. **Search + pagination:** `loading.tsx` (skeletons), `error.tsx`, Suspense / streaming
16. **Apni API:** Route Handlers, live search suggestions (debounce), TanStack Query vs server fetching
17. **About / credits page:** TMDB attribution rules + accessibility basics (alt text, labels, keyboard)

## Phase 4: Database + Auth (apna backend)
**Phase ke end mein:** users signup/login karke watchlist banate hain aur reviews likhte hain, aur sab data PostgreSQL mein save hota hai.

18. **PostgreSQL cloud par (free tier):** ORM choose karna (Prisma vs Drizzle), schema, migrations, Studio (phpMyAdmin jaisa GUI)
19. **Auth:** signup, login, logout (Better Auth ya Auth.js, docs check karke). Sessions aur cookies vs AsyncStorage.
20. **Protected pages:** login ke baghair `/watchlist` na khule; server par user check
21. **Watchlist:** Server Actions se add/remove, optimistic UI, cache revalidation
22. **Reviews:** React Hook Form + Zod (client + server validation), create/edit/delete; sirf apna review edit ho sake (security)
23. **Client state:** Context vs Zustand vs Redux Toolkit (kab kaunsa); dark mode toggle (localStorage / cookie)
24. **Profile page:** user ki public watchlist aur reviews

## Phase 5: Quality (testing + CI)
**Phase ke end mein:** har Pull Request par GitHub Actions khud lint, type-check aur tests chalata hai.

25. **TypeScript strict + scripts:** `lint` aur `type-check` scripts, warnings saaf karna
26. **Unit tests:** Vitest + React Testing Library (components, Zod schemas)
27. **End-to-end test:** Playwright (login → movie watchlist mein add)
28. **GitHub Actions CI:** har PR par lint + type-check + tests

## Phase 6: Performance, SEO aur Deploy
**Phase ke end mein:** FlickPick internet par live, free `.vercel.app` address ke saath. 🎉

29. **Performance:** images, fonts (`next/font`), Core Web Vitals, Lighthouse
30. **SEO:** metadata, Open Graph (link share preview), `sitemap.xml`, `robots.txt`
31. **Vercel par deploy (Hobby, free):** env vars, alag production database, PR preview deployments
32. **Alternative deploy:** ek aur free option ka comparison (us waqt check karke)
33. **Final polish:** README, screenshots, portfolio mein add karna, aage kya (apna product)

---

## Git workflow har phase mein
- Har lesson ke end mein **commit** (Conventional Commits: `feat:`, `fix:`, `chore:`, `docs:`, `test:`, `ci:`)
- Har bare feature ki **alag branch + Pull Request**, jaise `feat/home-layout`, `feat/tmdb-trending`,
  `feat/auth`, `feat/watchlist`, `feat/reviews`, `ci/github-actions`
- README har phase ke baad update
- Saari Git commands student khud chalayega

## RN → Web bridge: kaunsa topic kis lesson mein
| RN topic | Web mein | Lesson |
|---|---|---|
| View/Text | Semantic HTML | 3 |
| StyleSheet + Flexbox | CSS, Tailwind, responsive | 4 |
| Metro | Next.js tooling (Turbopack) | 1 |
| React Navigation | File-based routing | 7, 8 |
| AsyncStorage | localStorage, cookies, sessions | 19, 23 |
| Device APIs | Browser APIs, DOM, DevTools | Phase 0, 2, 9 |
| (Web-only) | URLs, SEO, SSR/SSG, caching, accessibility | 10, 13, 14, 17, 30 |
