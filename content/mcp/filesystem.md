---
title: "Filesystem MCP"
description: "MCP сервер для безопасной работы с файловой системой"
date: 2026-02-09
provider: "Anthropic"
protocol: "MCP"
website: "https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem"
features:
  - "Чтение и запись файлов"
  - "Создание директорий"
  - "Поиск файлов"
  - "Безопасный sandbox"
  - "Настраиваемые разрешения"
weight: 2
---

## Что это

Filesystem MCP сервер даёт AI-инструментам контролируемый доступ к файловой системе. Работает в sandbox — AI может читать и писать файлы только в разрешённых директориях.

## Возможности

- Чтение и запись файлов
- Создание и удаление директорий
- Перемещение и переименование файлов
- Поиск по имени и содержимому
- Получение метаданных файлов

## Как подключить

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/allowed/dir"]
    }
  }
}
```

## Безопасность

Сервер ограничивает доступ только указанными директориями. AI не может выйти за пределы sandbox.
