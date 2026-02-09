---
title: "PostgreSQL MCP"
description: "MCP сервер для работы с PostgreSQL. SQL-запросы и анализ схемы через AI"
date: 2026-02-09
provider: "Community"
protocol: "MCP"
website: "https://github.com/modelcontextprotocol/servers/tree/main/src/postgres"
features:
  - "Выполнение SQL-запросов"
  - "Анализ схемы базы данных"
  - "Просмотр таблиц и колонок"
  - "Read-only режим по умолчанию"
weight: 4
---

## Что это

PostgreSQL MCP сервер позволяет AI работать с базой данных: выполнять SQL-запросы, анализировать схему, исследовать данные.

## Возможности

- Выполнение SQL-запросов
- Просмотр списка таблиц и их структуры
- Анализ индексов и связей
- Безопасный read-only режим

## Как подключить

```json
{
  "mcpServers": {
    "postgres": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-postgres", "postgresql://user:pass@localhost:5432/db"]
    }
  }
}
```

## Безопасность

По умолчанию работает в read-only режиме — AI может читать данные, но не может их изменять или удалять.
