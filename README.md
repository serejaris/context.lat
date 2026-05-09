# context.lat

Каталог AI-инструментов для вайбкодеров: модели, IDE, skills, MCP и другие building blocks. Репозиторий хранит Hugo-сайт, карточки инструментов и cross-links для публичного справочника.

## Что внутри

| Путь | Роль |
|---|---|
| `content/` | страницы и карточки каталога |
| `archetypes/` | шаблоны для новых карточек tools/models/skills/MCP |
| `layouts/` | Hugo templates |
| `data/cross_links.json` | связи между карточками |
| `static/` и `public/` | статические ассеты и build output |
| `CLAUDE.md` | правила работы агентов |

## Запуск

```bash
hugo server
```

## Границы

- Это каталог и справочник, не операционный backlog школы.
- Канон курсов живёт в `teach-vibecoding` и `cohorts`.
- Перед добавлением карточки проверять, нет ли уже близкого инструмента или alias.
