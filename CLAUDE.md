# CLAUDE.md — Landings Portfolio

## Project overview
Commercial landing pages portfolio built with Astro + TypeScript + Tailwind CSS.

## Directory structure
- `Templates/` — reference HTML prototypes. READ ONLY. Do not delete, do not modify without a direct explicit command.
- `cyan-comet/src/pages/` — Astro pages (one per landing).
- `cyan-comet/src/components/` — reusable Astro components.
- `cyan-comet/src/styles/` — global styles.
- `cyan-comet/public/images/<landing>/` — landing-specific images.

## Astro project location
The Astro project lives in `cyan-comet/`. Always run `npm run build`, `npm run dev`, etc. from inside `cyan-comet/`.

## Workflow rules
1. Port one landing or one group of sections per task — never all at once.
2. Do not send full HTML files in responses.
3. Do not do a general redesign.
4. Always check `git status -sb` before making changes.
5. After changes: show changed files + brief diff summary only.
6. Do not push to remote.

## Agent roles
- **frontend-developer** — implements sections in Astro/Tailwind. Point changes only.
- **tech-lead-reviewer** — audit only. Checks architecture, scope, dependencies, build.
- **qa-tester** — audit only. Checks build, responsive risks, links, a11y, SEO basics.

## Stack
- Astro (static site generator), project root: `cyan-comet/`
- TypeScript
- Tailwind CSS (via @tailwindcss/vite)
- No backend
- No extra libraries without explicit approval
