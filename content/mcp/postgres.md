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
tags: ["mcp", "автоматизация"]
---

## Что это

PostgreSQL [MCP сервер](/concepts/mcp/) позволяет AI работать с базой данных: выполнять SQL-запросы, анализировать схему, исследовать данные. По умолчанию работает в read-only режиме — агент может читать, но не изменять данные.

## Как подключить

В [Claude Code](/tools/claude-code/):

```bash
claude mcp add postgres -- npx -y @modelcontextprotocol/server-postgres postgresql://user:pass@localhost:5432/mydb
```

Или через JSON-конфиг:

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

## Примеры использования

**Анализ схемы:**
```
→ "Покажи структуру базы данных"
→ Агент: list_tables → describe_table для каждой → возвращает схему с типами и связями
```

**Исследование данных:**
```
→ "Сколько пользователей зарегистрировалось за последнюю неделю?"
→ Агент: SELECT COUNT(*) FROM users WHERE created_at > NOW() - INTERVAL '7 days'
→ Ответ: 42 новых пользователя
```

**Дебаг:**
```
→ "Почему у пользователя @ivan нет подписки?"
→ Агент: проверяет users → subscriptions → payments → находит незавершённую оплату
```

## Безопасность

- **Read-only по умолчанию** — агент не может `DELETE`, `UPDATE`, `DROP`
- **Connection string** — используйте отдельного пользователя БД с минимальными правами
- **Не для продакшена** — подключайте к staging/dev копии, не к live БД
- **Пароли** — не коммитьте connection string в Git. Используйте переменные окружения

## Когда нужен

- Исследование существующей БД: «объясни эту схему»
- Аналитика: агент сам пишет SQL-запросы по вопросу на естественном языке
- Дебаг: поиск проблемных записей через запросы

## Ссылки

- [GitHub: postgres MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/postgres)
- [MCP Servers Registry](https://github.com/modelcontextprotocol/servers)

## Связанное

- [MCP](/concepts/mcp/) — протокол подключения
- [Supabase](/tools/supabase/) — hosted PostgreSQL с дополнительными сервисами
- [Claude Code](/tools/claude-code/) — агент, через который работает MCP
- [GitHub MCP](/mcp/github/) — аналогичный сервер для работы с GitHub
