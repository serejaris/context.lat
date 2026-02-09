---
title: "GitHub MCP"
description: "MCP сервер для работы с GitHub: issues, PR, репозитории прямо из AI"
date: 2026-02-09
provider: "GitHub / Anthropic"
protocol: "MCP"
website: "https://github.com/modelcontextprotocol/servers/tree/main/src/github"
tags: ["github", "git", "issues", "pr"]
features:
  - "Создание и поиск issues"
  - "Работа с Pull Requests"
  - "Управление репозиториями"
  - "Code search"
  - "Работа с файлами в репо"
weight: 1
---

## Что это

GitHub MCP сервер позволяет AI-инструментам напрямую работать с GitHub: создавать issues, искать код, управлять PR — всё через естественный язык.

## Возможности

- Создание, поиск и обновление Issues
- Создание и ревью Pull Requests
- Поиск по коду в репозиториях
- Чтение и запись файлов
- Управление branches и forks

## Как подключить

В Claude Code добавьте в настройки MCP:
```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "your-token"
      }
    }
  }
}
```

## Примеры использования

- "Создай issue с описанием бага"
- "Найди все открытые PR в репо"
- "Покажи последние коммиты в main"
