# CLAUDE.md — Landings Portfolio

# Project rules for Claude

Работай как исполнитель, не как дизайнер-концептор.

## Главные правила
- Не придумывай новый дизайн, если есть шаблон, скриншот или существующая реализация.
- Не меняй структуру страницы без прямого указания.
- Не добавляй новые блоки, секции, поля, эффекты и тексты без прямого указания.
- Не запускай background tasks.
- Не используй Task tool.
- Не запускай параллельных subagents.
- Не делай git commit и git push.
- Не запускай npm install и npm audit fix.
- Не меняй package.json и package-lock.json без прямого указания.
- Не трогай файлы вне явно разрешенного списка.
- Если задача требует больше файлов, чем разрешено, остановись и напиши почему.

## Для Astro
- Рабочий проект находится в cyan-comet.
- Стили страниц лежат в cyan-comet/src/styles.
- CSS подключать в .astro через frontmatter import:
  import '../styles/file.css';
- Не подключать CSS через /src/... или относительный link href.

## Для лендингов
- Если есть HTML-шаблон в Templates, он является источником правды.
- Нужно переносить шаблон, а не делать новый лендинг.
- Цвета, отступы, порядок секций и стили брать из шаблона.
- Фото не искать и не скачивать без отдельной команды.
- Если фото нет, ставить временный placeholder.

## Для CMS
- /admin — настоящий Decap CMS.
- /cms-demo — только безопасная демо-страница.
- /cms-demo не должна сохранять данные в JSON, Git, localStorage или API.
- Если нужно сделать demo похожим на Decap, использовать реальный /admin как визуальный референс, а не придумывать собственную CRM.

## Формат работы
- Перед изменениями коротко назвать файлы, которые будут изменены.
- После изменений дать короткий отчет:
  - измененные файлы;
  - что сделано;
  - результат npm.cmd run build.

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
