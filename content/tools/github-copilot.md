---
title: "GitHub Copilot"
description: "AI-ассистент от GitHub/Microsoft. Встроен в VS Code, JetBrains, Neovim"
date: 2026-02-09
provider: "GitHub / Microsoft"
item_type: "Плагин"
pricing:
  free: true
  from: "$0 (free tier)"
  tiers:
    - name: "Free"
      price: "$0"
    - name: "Pro"
      price: "$10/мес"
    - name: "Pro+"
      price: "$39/мес"
website: "https://github.com/features/copilot"
features:
  - "Работает в любой IDE (VS Code, JetBrains, Neovim)"
  - "Copilot Chat"
  - "Agent mode"
  - "Coding Agent (автономный)"
  - "Глубокая интеграция с GitHub"
weight: 4
category: "CLI и плагины"
category_weight: 2
tags: ["openai", "ide"]
---

## Обзор

GitHub Copilot — AI-ассистент от Microsoft/GitHub, который работает как плагин в существующей IDE. После обновления в феврале 2026 превратился из автодополнения в полноценный облачный агент. За $10/мес даёт доступ к [Claude Opus 4.6](/models/claude/) — сильно субсидированная цена (аналог Claude Max за $100).

## Быстрый старт

1. Установить расширение GitHub Copilot в VS Code
2. Авторизоваться через GitHub-аккаунт
3. Copilot Chat: Cmd+I → описать задачу
4. Agent mode: попросить выполнить задачу автономно

## Ключевые возможности

### Agent Mode (в VS Code)

Автономное выполнение задач прямо в IDE:

```
→ "Добавь авторизацию через Supabase"
→ Copilot: читает проект → планирует → пишет код → предлагает review
```

### Coding Agent (из GitHub)

Полностью автономный агент, работающий фоном:

1. Создать Issue в репозитории с описанием задачи
2. Назначить Copilot как исполнителя (или через команду)
3. Copilot анализирует кодовую базу в sandbox
4. Результат — Pull Request с реализацией

Работает фоном — не занимает машину, пока вы работаете с другими агентами.

### Prompt Files

VS Code Copilot поддерживает `.github/prompts/*.prompt.md` — аналог [скиллов](/concepts/skill/) в [Claude Code](/tools/claude-code/). Каждый файл = инструкция для конкретного типа задач.

## Тарифы (февраль 2026)

| Тариф | Цена | Что входит |
|-------|------|-----------|
| Free | $0 | 2000 автодополнений, 50 чатов/мес |
| Pro | $10/мес | Безлимит + агент + 300 premium запросов |
| Pro+ | $39/мес | 1500 premium, все модели (Claude Opus, o3) |

Каждый запрос к premium-модели = 3 кредита вне зависимости от сложности.

## Copilot vs Claude Code vs Cursor

| Критерий | Copilot | [Claude Code](/tools/claude-code/) | [Cursor](/tools/cursor/) |
|----------|---------|------------|--------------------------|
| Интерфейс | VS Code плагин | Терминал | Отдельная IDE |
| Фоновая работа | Да (Coding Agent) | Нет | Нет |
| Результат | Pull Request | Файлы + коммит | Файлы |
| Модели | Claude, GPT, o3 | Claude | Claude, GPT |
| Цена | $10/мес | $20/мес (Pro) | $20/мес |

## В курсе

| Урок | Контекст |
|------|----------|
| Урок 4 | Обновление от февраля 2026. $10/мес за Opus 4.6. Агент работает фоном, результат = PR. Рекомендован для следующих потоков как первый инструмент входа |

## Ссылки

- [GitHub Copilot](https://github.com/features/copilot)
- [Тарифы](https://github.com/features/copilot/plans)
- [Документация](https://docs.github.com/en/copilot)

## Связанное

- [GitHub](/tools/github/) — платформа, на которой работает Copilot
- [Claude Code](/tools/claude-code/) — альтернатива в терминале
- [Cursor](/tools/cursor/) — альтернатива как отдельная IDE
- [Скилл](/concepts/skill/) — Prompt Files = аналог скиллов
