---
title: "Cursor"
description: "AI-first IDE на базе VS Code. Самый популярный инструмент для вайбкодинга"
date: 2026-02-09
provider: "Anysphere"
item_type: "IDE"
pricing:
  free: true
  from: "$0 (free tier)"
  tiers:
    - name: "Hobby"
      price: "$0"
    - name: "Pro"
      price: "$20/мес"
    - name: "Ultra"
      price: "$200/мес"
website: "https://cursor.com/"
features:
  - "Fork VS Code — привычный интерфейс"
  - "Composer для multi-file editing"
  - "Tab-автодополнение"
  - "Inline Chat в коде"
  - "Поддержка Claude, GPT, Gemini"
  - "Background Agent"
weight: 2
category: "IDE"
category_weight: 1
tags: ["ide", "claude-code"]
---

## Обзор

Cursor — самый популярный AI-редактор для кодинга. Это форк VS Code с встроенным AI, который понимает ваш проект и помогает писать код. Работает с файлами на компьютере, умеет не только писать код, но и работать с текстами, промптами, конфигами — любыми файлами.

Рекомендован для студентов, которые хотят графический интерфейс вместо терминала.

## Быстрый старт

1. Скачать с [cursor.com](https://cursor.com) (бесплатно)
2. Открыть папку проекта
3. Запустить Composer (Cmd+I / Ctrl+I):

```
Создай Telegram-бота на Python.
Используй python-telegram-bot.
Бот отвечает на /start приветствием.
```

4. Cursor создаст файлы, предложит изменения — принять или отклонить каждое
5. Для планирования: переключить Composer в режим **Plan** — агент сначала спланирует, потом выполнит

## Ключевые возможности

- **Composer**: создание и редактирование нескольких файлов одновременно по текстовому описанию. Основной режим работы
- **Tab**: умное автодополнение, которое предсказывает следующий код на основе контекста
- **Chat**: обсуждение кода прямо в контексте файла — выделил код → задал вопрос
- **Background Agent**: автономное выполнение задач в фоне (аналог Codex)
- **Rules**: `.cursor/rules/*.md` — аналог [CLAUDE.md](/concepts/claude-md/) и [Skills](/concepts/skill/) в Claude Code

## Настройка Rules

Rules — это файлы в `.cursor/rules/`, которые Cursor читает при запуске. Аналог CLAUDE.md:

```markdown
# .cursor/rules/project.md
## Стек
- Python 3.12, FastAPI, PostgreSQL
- Деплой на Railway

## Стиль
- async/await везде
- Type hints обязательны
- Коммиты на английском
```

## Сравнение с альтернативами

| Критерий | Cursor | VS Code + Copilot | [Claude Code](/tools/claude-code/) |
|----------|--------|-------------------|------------|
| Интерфейс | GUI (VS Code) | GUI (VS Code) | Терминал |
| Цена | $20/мес | $10/мес | $100-200/мес |
| Модели | Claude, GPT, Gemini | Claude Opus 4.6 и др. | Claude Opus 4.6 |
| Расширения | ~95% совместимость | Полная экосистема | Через MCP |
| Rules/Skills | `.cursor/rules/` | `.github/prompts/` | `.claude/skills/` |

**Вывод из курса:** VS Code + Copilot за $10 даёт те же модели, что Cursor за $20 — вдвое дешевле. Для студентов это существенная разница.

## Когда выбрать Cursor

- Уже используете — нет смысла переезжать
- Нужен графический интерфейс (терминал непривычен)
- Tab-автодополнение и Composer удобнее для вашего workflow
- Цена не критична

## В курсе

| Урок | Контекст |
|------|----------|
| Урок 2 | Основной редактор урока для создания Telegram-бота. Упал под нагрузкой — группа переключилась на VS Code + Kilo Code. Режим Agent, режим Plan для планирования |
| Урок 4 | Упомянут в контексте скиллов: Rules в Cursor (`.cursor/rules/*.md`) — аналог Skills в Claude Code |

## Ссылки

- [Cursor](https://cursor.com)
- [Тарифы](https://cursor.com/pricing)
- [Документация](https://docs.cursor.com)

## Связанное

- [Claude Code](/tools/claude-code/) — терминальная альтернатива
- [Kilo Code](/tools/kilo-code/) — расширение VS Code, альтернатива Cursor
- [Windsurf](/tools/windsurf/) — ещё одна AI-IDE
- [CLAUDE.md](/concepts/claude-md/) — концепция, которую Rules реализует в Cursor
- [Skills](/concepts/skill/) — аналог Rules, но в Claude Code
- [Plan mode](/concepts/plan-mode/) — режим планирования, есть в Cursor и Claude Code
