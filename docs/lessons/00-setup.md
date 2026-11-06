# Lesson 0: Setup — Summary (revision ke liye)

## Kya install kiya
| Tool | Version | Kaam |
|---|---|---|
| Node.js | v26.13.0 (LTS) | JavaScript ko computer par chalata hai. Next.js ka dev server aur build iske upar chalte hain. |
| npm | 11.20.0 | Packages (libraries) install karta hai. Node ke saath aata hai. |
| Git | 2.56.0 | Code ki history (commits = save points) |
| Antigravity | — | Code editor (VS Code ka fork) |
| GitHub | — | Git history online + team kaam (Pull Requests) |
| DevTools (`F12`) | — | Browser ka debugger |

**Rule:** Node hamesha **LTS** version ka lena hai. Alpha ya odd version nahi.

## Extensions
- **ESLint:** bugs aur buri practices pakarta hai (jaise unused variable, `useEffect` ki missing dependency)
- **Prettier:** sirf formatting (spaces, quotes, semicolons)
- **Tailwind CSS IntelliSense:** classes ka autocomplete. Class par hover karein to asal CSS dikhti hai.

## TypeScript vs ESLint vs Prettier
- **TypeScript:** types check karta hai (`number` ki jagah `string` di?)
- **ESLint:** code quality check karta hai. TS ke saath bhi chalta hai (typescript-eslint ke zariye).
- **Prettier:** code ki shakal (formatting) theek karta hai.
- TypeScript ke liye editor mein alag extension nahi chahiye, wo built-in hai.

## Extension vs library
- **Extension** editor mein errors dikhata hai. Editor mein **ek dafa** install hota hai.
- **Library** (`eslint` package) asal kaam karti hai, aur **har project mein alag** install hoti hai.
  `create-next-app` ye khud install kar deta hai.
- Tools ko global (`-g`) install nahi karte. Har project mein local install karte hain, taake sab ka version ek ho.

## Tailwind: RN se farq
- Web par `div` **by default flex nahi hota**, `flex` class lagani parti hai.
- Web par default direction **`row`** hai. RN mein `column` hota hai.
- Hum Tailwind **v4** use karenge. Purane (v3) tutorials mein `tailwind.config.js` aur `@tailwind base;` hote hain;
  v4 mein sirf `@import "tailwindcss";` hota hai.

## DevTools aur DOM
- `F12` dabane se DevTools khulta hai. **Console** tab mein JavaScript chalti hai, aur **Elements** tab mein page dikhta hai.
- Browser server se HTML le kar memory mein page ka ek "tree" banata hai. Isay **DOM** kehte hain.
- DevTools mein jo badla, wo sirf **aap ke browser ka DOM** tha. Server ki asal file nahi badli.
- Refresh karne par browser page dobara load karke DOM naye siray se banata hai, is liye tabdeeli gayab ho jati hai.
- RN mein React native views ka tree update karta hai. Web par React **DOM** ko update karta hai.

## Git settings
- `init.defaultBranch main` **branch nahi banati.** Ye sirf setting hai ke aage bane naye repos ki pehli branch ka naam `main` ho.

## Vim se bahar kaise niklein 🆘
- Save karke: `Esc`, phir `:wq`, phir `Enter`
- Bina save kiye: `Esc`, phir `:q!`, phir `Enter`

## Common mistakes
1. Install ke baad terminal restart nahi kiya, to "node is not recognized" aata hai.
2. PowerShell mein `npm.ps1` wala "scripts disabled" error. Command Prompt mein ye nahi aata.
3. Git ki `user.email` GitHub account wali email se match nahi karti, to commits profile se link nahi hote.
4. Extension ke page par likhi `npm install eslint` command bina project ke chala dena.
