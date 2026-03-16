---
title: "GitHub CLI (gh)"
description: "Официальный CLI для GitHub — Issues, PR и репозитории из терминала"
date: 2026-03-16
provider: "GitHub"
item_type: "CLI"
pricing:
  free: true
  from: "$0"
website: "https://cli.github.com"
features:
  - "Управление Issues и PR"
  - "Создание репозиториев"
  - "Просмотр Actions"
  - "GraphQL API"
weight: 9
category: "CLI и плагины"
category_weight: 2
---

## Обзор

`gh` — официальная утилита GitHub для терминала. Для AI-агента это критически важный инструмент: агент не может открыть браузер, но может запустить `gh repo create` или `gh issue list`.

## Установка

```bash
brew install gh
gh auth login
```

## Ключевые команды

```bash
# Репозитории
gh repo create my-project --public
gh repo clone owner/repo

# Issues
gh issue create --title "Bug" --body "Description"
gh issue list --state open

# Pull Requests
gh pr create --title "Feature" --body "Details"
gh pr list
```

## Для AI-агентов

GitHub CLI даёт агенту полный контроль над GitHub: создание репозиториев, пуш кода, управление Issues. В связке с GitHub Projects агент может автоматически фиксировать прогресс и создавать задачи.

## Для кого

Для разработчиков, живущих в терминале, и для AI-агентов, которым нужен доступ к GitHub без браузера.
