---
title: "GitHub"
description: "Хостинг кода с Issues, Projects и автодеплоем — командный центр вайбкодера"
date: 2026-03-16
provider: "Microsoft"
item_type: "Платформа"
pricing:
  free: true
  from: "$0 (free tier)"
  tiers:
    - name: "Free"
      price: "$0"
    - name: "Pro"
      price: "$4/мес"
    - name: "Team"
      price: "$4/user/мес"
website: "https://github.com"
features:
  - "Хостинг кода"
  - "Issues для задач"
  - "Projects для канбан-досок"
  - "Actions для автоматизации"
  - "Copilot для AI-ассистирования"
weight: 6
category: "Инфраструктура"
category_weight: 4
tags: ["автоматизация", "агенты"]
---

## Обзор

GitHub — платформа для хостинга кода, управления задачами и автоматизации. Для вайбкодера GitHub — командный центр: Issues хранят контекст между сессиями агента, Projects организуют задачи, Actions автоматизируют деплой. Не просто «Dropbox для кода» — это persistent storage для [агентского цикла](/concepts/agentic-loop/).

## Быстрый старт

Агент создаёт репозиторий сам через CLI:

```bash
gh repo create myapp --private --clone
cd myapp
# агент начинает работу
```

Или из [Claude Code](/tools/claude-code/):

```
→ "Создай GitHub-репозиторий для проекта и запуши текущий код"
→ Агент: gh repo create → git init → git add → git push
```

## Ключевые связки

### GitHub + AI-агент

[Claude Code](/tools/claude-code/) работает с GitHub через `gh` CLI:

```
→ "Создай issue с описанием задачи"
→ Агент: gh issue create --title "Добавить авторизацию" --body "..."
```

Issues — persistent storage контекста. Агент фиксирует прогресс в Issues и возвращается к нему при следующем запуске.

### GitHub + Railway (автодеплой)

```
git push origin main
→ Railway обнаруживает push → автодеплой → приложение обновлено
```

Каждый пуш в main = автоматическое обновление production.

### GitHub + AI-билдеры

Синхронизация между [v0](/tools/v0/), [Replit](/tools/replit/), [Lovable](/tools/lovable/):

1. Создать проект в AI-билдере
2. Экспортировать в GitHub
3. Продолжить работу в [Cursor](/tools/cursor/) или [Claude Code](/tools/claude-code/)

### GitHub Projects

Канбан-доска, управляемая агентом:

```
→ "Создай доску для проекта, добавь задачи из консилиума агентов"
→ Агент: gh project create → gh project item-add (для каждой задачи)
```

## В курсе

| Урок | Контекст |
|------|----------|
| Урок 2 | Обязательная регистрация. GitHub как «Dropbox для кода» — синхронизация между AI-билдерами |
| Урок 3 | Агент создаёт репозиторий из Claude Code. Railway привязывается к репо — каждый пуш = автодеплой |
| Урок 4 | GitHub как командный центр: Issues для persistent storage, Projects для задач консилиума, мастер-репозиторий как индекс проектов |

## Ссылки

- [GitHub](https://github.com)
- [GitHub CLI](https://cli.github.com)
- [Тарифы](https://github.com/pricing)

## Связанное

- [GitHub Copilot](/tools/github-copilot/) — AI-агент внутри GitHub
- [GitHub MCP](/mcp/github/) — MCP-сервер для работы с GitHub из AI
- [Claude Code](/tools/claude-code/) — работает с GitHub через gh CLI
- [Личная корпорация](/concepts/personal-corp/) — GitHub как командный центр корпорации
