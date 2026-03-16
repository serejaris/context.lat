---
title: "Windsurf"
description: "AI IDE от Codeium. Flows — уникальный подход к AI-ассистенту"
date: 2026-02-09
provider: "Codeium"
item_type: "IDE"
pricing:
  free: true
  from: "$0 (free tier)"
  tiers:
    - name: "Free"
      price: "$0"
    - name: "Pro"
      price: "$15/мес"
    - name: "Ultra"
      price: "$60/мес"
website: "https://windsurf.com/"
features:
  - "Cascade — агентный AI ассистент"
  - "Flows — контекстуальное понимание"
  - "Доступный тариф Pro $15/мес"
  - "Поддержка Claude и GPT"
  - "Кодовая индексация проекта"
weight: 3
category: "IDE"
category_weight: 1
tags: ["ide", "промпты"]
---

## Обзор

Windsurf (ранее Codeium) — AI-IDE с уникальным подходом Flows: система отслеживает ваши действия в редакторе и предлагает помощь в контексте. Cascade — агентный AI, который может выполнять многоэтапные задачи.

Самый доступный тариф среди AI-IDE: Pro за $15/мес vs $20 у Cursor.

## Быстрый старт

1. Скачать с [windsurf.com](https://windsurf.com)
2. Настроить Rules (аналог CLAUDE.md):

Создать `.windsurfrules` в корне проекта:

```markdown
## Стек
- Python 3.12, FastAPI
- PostgreSQL, Railway

## Стиль
- async/await, type hints
- Коммиты на английском
```

3. Открыть Cascade (Cmd+L) и описать задачу:

```
Добавь эндпоинт /api/stats, который возвращает
количество сообщений за последние 7 дней.
```

## Ключевые возможности

- **Cascade**: агентный AI для многоэтапных задач (аналог Composer в Cursor)
- **Flows**: контекстуальное понимание — система видит, что вы делаете, и предлагает релевантную помощь
- **Rules**: `.windsurfrules` + `.windsurf/skills/` — аналог [CLAUDE.md](/concepts/claude-md/)
- **Кодовая индексация**: понимает весь проект, не только открытые файлы

## Сравнение с альтернативами

| Критерий | Windsurf | [Cursor](/tools/cursor/) | [Claude Code](/tools/claude-code/) |
|----------|---------|--------|------------|
| Цена | $15/мес | $20/мес | $100-200/мес |
| Интерфейс | IDE | IDE (VS Code) | Терминал |
| Уникальность | Flows — контекстуальное AI | Composer, Tab | MCP, Skills |
| Модели | Claude, GPT | Claude, GPT, Gemini | Claude |
| Rules | `.windsurfrules` | `.cursor/rules/` | `CLAUDE.md` |

## Когда выбрать Windsurf

- Бюджет ограничен: $15 vs $20 у Cursor
- Нравится подход Flows — контекстуальные подсказки
- Хотите попробовать альтернативу Cursor
- Уже привыкли к Windsurf

## Ссылки

- [Windsurf](https://windsurf.com)
- [Тарифы](https://windsurf.com/pricing)
- [Документация](https://docs.windsurf.com)

## Связанное

- [Cursor](/tools/cursor/) — основной конкурент
- [Kilo Code](/tools/kilo-code/) — бесплатная альтернатива в VS Code
- [Claude Code](/tools/claude-code/) — терминальная альтернатива
- [CLAUDE.md](/concepts/claude-md/) — концепция, которую Rules реализует в Windsurf
