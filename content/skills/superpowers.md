---
title: "Superpowers"
description: "Agentic skills framework от Jesse Vincent — превращает Claude Code из генератора кода в дисциплинированного senior-разработчика с TDD, планированием и code review"
date: 2026-02-09
category: "Фреймворк"
tool: "Claude Code"
weight: 1
---

## Что это

Superpowers — open-source плагин для Claude Code (43.7k+ звёзд на GitHub), который решает главную проблему AI-агентов: они пишут код раньше, чем думают. Вместо этого Superpowers навязывает структурированный workflow: сначала brainstorm, потом план, потом TDD, потом code review.

Автор — Jesse Vincent ([@obra](https://github.com/obra)). С января 2026 плагин в официальном маркетплейсе Anthropic.

## Установка

```bash
# Через маркетплейс (рекомендуется)
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace

# Или через Discover
/plugin → Discover → "superpowers" → Install
```

После установки перезапустите Claude Code. В начале сессии появится `SessionStart:startup hook succeeded: Success`.

## Workflow

Superpowers работает через 7 фаз:

### 1. Brainstorming
Вместо немедленного кодинга Claude задаёт вопросы: что вы реально пытаетесь сделать, какие есть ограничения, какие альтернативы рассмотрены. Сократический метод.

### 2. Git Worktrees
Изолированные рабочие ветки. Основной код не трогается до финальной интеграции.

### 3. Planning
Задача разбивается на микро-таски по 2-5 минут. Каждый таск — с конкретными файлами и acceptance criteria. План "достаточно понятный для junior-разработчика без контекста проекта".

### 4. Subagent-Driven Development
Параллельные суб-агенты работают над независимыми задачами одновременно. Ускорение в 3-4 раза на больших задачах.

### 5. Test-Driven Development
Принудительный RED → GREEN → REFACTOR цикл. Тесты пишутся до реализации. Покрытие обычно 85-95%.

### 6. Code Review
Автоматическая проверка качества: безопасность (OWASP Top 10), производительность, масштабируемость, документация.

### 7. Branch Completion
Финальная интеграция: merge, PR или cleanup. Выбор за вами.

## Команды

| Команда | Что делает |
|---------|-----------|
| `/superpowers:brainstorm` | Запускает сократический диалог |
| `/superpowers:write-plan` | Генерирует детальный план |
| `/superpowers:execute-plan` | Запускает параллельное выполнение |
| `/superpowers:systematic-debugging` | Структурированный дебаг |
| `/superpowers:test-driven-development` | Принудительный TDD |
| `/superpowers:requesting-code-review` | Запрос code review |

## Включённые skills

- **brainstorming** — исследование идеи до кода
- **writing-plans** — создание детальных планов
- **executing-plans** — параллельное выполнение с review
- **test-driven-development** — TDD с RED/GREEN/REFACTOR
- **systematic-debugging** — методичный поиск и фикс багов
- **requesting-code-review** — запрос проверки
- **receiving-code-review** — обработка фидбека
- **verification-before-completion** — проверка перед заявлением "готово"
- **using-git-worktrees** — изоляция через worktrees
- **dispatching-parallel-agents** — параллельная работа суб-агентов
- **subagent-driven-development** — делегирование задач
- **finishing-a-development-branch** — завершение ветки

## Когда использовать

**Подходит:**
- Сложные фичи и рефакторинги
- Проекты с требованиями к качеству и тестам
- Работа над существующими кодовыми базами
- Командная разработка с code review

**Не подходит:**
- Одноразовые скрипты и быстрые фиксы
- Прототипы на выброс
- Задачи на несколько строк кода

## Ссылки

- [GitHub](https://github.com/obra/superpowers) — 43.7k звёзд
- [Маркетплейс Anthropic](https://claude.com/plugins/superpowers)
- [Блог автора](https://blog.jessevincentart.com/) — Jesse Vincent
