---
title: "Raycast"
description: "Лаунчер для macOS с AI-ассистентом и автоматизацией рабочих процессов"
date: 2026-03-16
provider: "Raycast"
item_type: "Приложение"
pricing:
  free: true
  from: "$0 (free tier)"
  tiers:
    - name: "Free"
      price: "$0"
    - name: "Pro"
      price: "$8/мес"
    - name: "Teams"
      price: "$12/мес"
website: "https://www.raycast.com"
features:
  - "Быстрый запуск приложений"
  - "AI-ассистент"
  - "Сниппеты и quicklinks"
  - "Расширения и автоматизация"
weight: 14
category: "Локальные инструменты"
category_weight: 5
tags: ["автоматизация", "промпты"]
---

## Обзор

Raycast — лаунчер для macOS, замена Spotlight. Помимо быстрого запуска приложений, включает AI-ассистент, сниппеты для шаблонов, автоматизацию и экосистему расширений. Для вайбкодера — дополнительный слой оркестрации рабочего стола.

## Быстрый старт

1. Скачать с [raycast.com](https://www.raycast.com) (macOS)
2. Заменить Spotlight: System Settings → Keyboard Shortcuts → убрать Cmd+Space от Spotlight
3. Настроить Raycast на Cmd+Space
4. Готово — быстрый доступ ко всему через один хоткей

## Возможности для вайбкодера

### Сниппеты — шаблоны промптов

Горячие клавиши для часто используемых промптов:

```
Триггер: ;meta
Текст: "Я хочу создать [проект]. Задай мне 5 уточняющих
        вопросов, прежде чем генерировать финальный промпт."
```

Набираете `;meta` в любом приложении — текст разворачивается в полный промпт.

### Quicklinks — быстрый доступ

- GitHub Issues: `gh://issues` → открывает проект в один клик
- Документация: `docs://supabase` → прямой переход к нужным докам
- Проекты: `code://myapp` → открывает проект в [Cursor](/tools/cursor/)

### AI Chat

Встроенный AI-чат с доступом к [Claude](/models/claude/), [GPT](/models/gpt/) и другим моделям. Быстрый вопрос без открытия браузера — Cmd+Space → Tab → вопрос.

### Расширения

- [GitHub](https://www.raycast.com/raycast/github) — issues, PR, нотификации
- Notion — заметки и задачи
- Jira — тикеты
- 1000+ расширений в [Raycast Store](https://www.raycast.com/store)

## В курсе

| Урок | Контекст |
|------|----------|
| Урок 3 | Дополнительный слой оркестрации: быстрые команды, сниппеты для промптов, запуск агентных сценариев |

## Ссылки

- [Raycast](https://www.raycast.com)
- [Raycast Store](https://www.raycast.com/store)

## Связанное

- [Claude Code](/tools/claude-code/) — терминальный агент, запускаемый через Raycast
- [Метапромптинг](/concepts/metaprompting/) — сниппеты для шаблонов промптов
- [CLAUDE.md](/concepts/claude-md/) — сниппеты могут хранить фрагменты правил
