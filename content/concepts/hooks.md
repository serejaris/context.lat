---
title: "Хуки (Hooks)"
description: "Детерминированные обработчики событий в Claude Code — гарантированное выполнение, в отличие от промптов"
date: 2026-03-16
category: "Продвинутый"
difficulty: "Средний"
weight: 8
tags: ["claude-code", "автоматизация"]
---

## Определение

Хуки — shell-команды или скрипты, привязанные к событиям жизненного цикла [Claude Code](/tools/claude-code/): до запуска инструмента, после сохранения файла, при завершении сессии. Ключевое отличие от инструкций в промпте: хуки исполняются гарантированно. LLM может проигнорировать правило из [CLAUDE.md](/concepts/claude-md/), посчитав его необязательным — хук проигнорировать нельзя.

Это позволяет добавлять к вероятностному поведению агента детерминированные точки контроля.

## Как настроить

Хуки настраиваются в `.claude/settings.json`:

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "write_to_file",
        "command": "npx eslint --fix $FILE"
      }
    ],
    "PostSession": [
      {
        "command": "gh issue comment $ISSUE --body 'Session complete: $SUMMARY'"
      }
    ]
  }
}
```

## Примеры рабочих хуков

### Фиксация прогресса в GitHub Issues

```json
{
  "hooks": {
    "PostSession": [
      {
        "command": "gh issue comment $CURRENT_ISSUE --body \"Итоги сессии: $SESSION_SUMMARY\""
      }
    ]
  }
}
```

Решает проблему потери контекста между сессиями — не нужно помнить писать заметки, хук делает это автоматически.

### Линтер после каждого изменения

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "write_to_file",
        "command": "npx eslint --fix $FILE"
      }
    ]
  }
}
```

### Проверка безопасности перед коммитом

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "git_commit",
        "command": "git diff --staged | grep -qE '(API_KEY|SECRET|PASSWORD)' && exit 1 || exit 0"
      }
    ]
  }
}
```

## CLAUDE.md vs Hooks

| | [CLAUDE.md](/concepts/claude-md/) | Hooks |
|---|---|---|
| Исполнение | Вероятностное (LLM решает) | Детерминированное (всегда) |
| Формат | Markdown-инструкции | Shell-команды |
| Контроль | Рекомендации | Гарантии |
| Задачи | Стиль, архитектура, контекст | Тесты, линтинг, фиксация |
| Когда использовать | Предпочтения и правила | Критичные действия |

**Правило:** то, что должно выполняться всегда — в хуки. То, что может быть гибким — в CLAUDE.md.

## В курсе

| Урок | Контекст |
|------|----------|
| Урок 3 | Хуки упоминаются как механизм автоматического обновления документации после сессии |
| Урок 4 | Хуки разбираются в блоке про детерминированность: CLAUDE.md задаёт рекомендации, хуки — гарантируют выполнение. Пример: фиксация прогресса в GitHub Issues после каждой сессии |

## Ссылки

- [Automate workflows with hooks — Anthropic](https://code.claude.com/docs/en/hooks-guide)
- [Claude Code Hooks Mastery — YUV.AI](https://yuv.ai/blog/claude-code-hooks-mastery)

## Связанное

- [CLAUDE.md](/concepts/claude-md/) — вероятностные правила (хуки — детерминированные)
- [Claude Code](/tools/claude-code/) — платформа, где работают хуки
- [Skills](/concepts/skill/) — переиспользуемые промпты (хуки — переиспользуемые команды)
- [Compact](/concepts/compact/) — хуки решают проблему потери контекста при compact
