# context.lat

База знаний про вайбкодинг и AI-инструменты. Hugo, тёмная моноширинная тема, деплой на Vercel.

## Boundaries

| | Rule |
|---|------|
| ✅ Always | `hugo` без ошибок перед коммитом, русский контент |
| ⚠️ Ask first | Новые секции, изменения навигации, правки baseof.html |
| 🚫 Never | Inline CSS вне baseof.html, English в контенте (кроме терминов) |

## Commands

| Task | Command |
|------|---------|
| Dev | `hugo server` |
| Build | `hugo` |
| Deploy | Push to main → Vercel auto-deploys |

## Architecture

| Path | Purpose |
|------|---------|
| `content/{models,tools,skills,articles,concepts,mcp}/` | Markdown-контент по секциям |
| `layouts/{section}/list.html` | Список карточек секции (card-grid + ByWeight) |
| `layouts/{section}/single.html` | Шаблон страницы (detail-header + content-body) |
| `layouts/_default/baseof.html` | Единый layout: nav, стили, footer |
| `layouts/index.html` | Главная: hero, последние обновления, grid разделов |
| `layouts/partials/` | card.html, breadcrumbs.html, seo.html |
| `hugo.toml` | Конфиг: gitInfo, sitemap, params |

## Key Patterns

**Новая секция**: создать `content/{name}/_index.md` + `layouts/{name}/list.html` + `single.html`, добавить в nav (`baseof.html:536`) и grid (`index.html:41`).

**Frontmatter статьи**: title, description, date, category, difficulty, weight. См. `content/articles/mcp-exa-guide.md:1`.

**Стили**: всё в `baseof.html` внутри `<style>`. Нет отдельных CSS-файлов.

## Style

- bg: `#0d0d0d`, text: `#999`, headings: `#ccc`, accent: `#4A9EFF`, borders: `#222`
- Font: Fira Code, container max-width: 1200px
- Home grid: `repeat(3, 1fr)`, card-grid: `auto-fill, minmax(280px, 1fr)`
