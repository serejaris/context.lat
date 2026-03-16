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
tags: ["mcp", "anthropic"]
---

## Что это

Filesystem [MCP сервер](/concepts/mcp/) даёт AI-инструментам контролируемый доступ к файловой системе. Работает в sandbox — AI может читать и писать файлы только в разрешённых директориях.

## Когда нужен (и когда нет)

**Нужен** для инструментов без встроенного доступа к файлам: [ChatGPT](/tools/chatgpt/), Custom GPTs, другие чат-боты, подключенные через MCP.

**Не нужен** для [Claude Code](/tools/claude-code/) — у него уже есть прямой доступ к файловой системе. Подключение Filesystem MCP к Claude Code добавит дублирующий инструмент и займёт место в [контексте](/concepts/context/).

## Как подключить

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/Users/me/projects"]
    }
  }
}
```

Можно указать несколько директорий:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y", "@modelcontextprotocol/server-filesystem",
        "/Users/me/projects",
        "/Users/me/Documents/notes"
      ]
    }
  }
}
```

## Доступные операции

| Инструмент | Что делает |
|-----------|-----------|
| `read_file` | Прочитать содержимое файла |
| `write_file` | Записать содержимое в файл |
| `list_directory` | Показать содержимое папки |
| `create_directory` | Создать новую директорию |
| `move_file` | Переместить или переименовать |
| `search_files` | Поиск по имени файла |
| `get_file_info` | Метаданные: размер, дата изменения |

## Безопасность

- Сервер ограничивает доступ только указанными директориями
- AI не может выйти за пределы sandbox (нет `../` escape)
- Для read-only доступа: используйте пользователя ОС без прав на запись

## Ссылки

- [GitHub: filesystem MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem)
- [MCP Servers Registry](https://github.com/modelcontextprotocol/servers)

## Связанное

- [MCP](/concepts/mcp/) — протокол подключения
- [Claude Code](/tools/claude-code/) — уже имеет доступ к файлам (MCP не нужен)
- [GitHub MCP](/mcp/github/) — для работы с кодом в репозиториях вместо локальных файлов
