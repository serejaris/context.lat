---
title: "Скиллы (Skills)"
description: "Переиспользуемые промпты в формате markdown — программирование агента на естественном языке"
date: 2026-03-16
category: "Продвинутый"
difficulty: "Начинающий"
weight: 15
---

## Определение

Скиллы — переиспользуемые промпты в формате файлов `skill.md`, хранящиеся в папке `.claude/skills/`. Это программирование агента на естественном языке: один раз описываешь процедуру — агент выполняет её по команде. Аналог SOP (Standard Operating Procedure) для AI-агентов.

Работают в Claude Code, Cursor, VS Code.

## Два уровня

- **Глобальные** (`~/.claude/skills/`) — доступны во всех проектах
- **Локальные** (`.claude/skills/` в проекте) — специфичны для проекта

## Примеры

- Процедура публикации поста в Telegram-канал
- Code review по чеклисту
- Генерация отчёта по шаблону
- Деплой с проверками

## Скиллы vs промпты

| | Промпт | Скилл |
|---|---|---|
| Хранение | В голове / clipboard | В файле проекта |
| Переиспользование | Копирование | Команда `/skill-name` |
| Контекст | Нужно каждый раз задавать | Встроен в файл |
| Версионирование | Нет | Через git |

## Ссылки

- [Claude Code Skills — Anthropic](https://docs.anthropic.com/en/docs/claude-code/memory#slash-commands)
- [Cursor Rules — документация](https://docs.cursor.com/context/rules-for-ai)
- [Superpowers — библиотека скиллов](https://github.com/obra/superpowers)
