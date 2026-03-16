---
title: "GitHub MCP"
description: "MCP сервер для работы с GitHub: issues, PR, репозитории прямо из AI"
date: 2026-02-09
provider: "GitHub / Anthropic"
protocol: "MCP"
website: "https://github.com/modelcontextprotocol/servers/tree/main/src/github"
features:
  - "Создание и поиск issues"
  - "Работа с Pull Requests"
  - "Управление репозиториями"
  - "Code search"
  - "Работа с файлами в репо"
weight: 1
tags: ["mcp", "автоматизация"]
---

## Что это

GitHub MCP сервер позволяет AI-инструментам напрямую работать с [GitHub](/tools/github/): создавать issues, искать код, управлять PR — всё через естественный язык.

## Когда нужен (и когда нет)

**Нужен** для инструментов без встроенной интеграции с GitHub: Custom GPTs, другие чат-боты, LLM-приложения.

**Не нужен** для [Claude Code](/tools/claude-code/) — он использует `gh` CLI напрямую, что мощнее и не занимает место в [контексте](/concepts/context/). Аналогично, [Codex](/tools/codex/) и [GitHub Copilot](/tools/github-copilot/) имеют нативную интеграцию.

## Как подключить

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_your_token"
      }
    }
  }
}
```

Для создания токена: GitHub Settings → Developer Settings → Personal Access Tokens → Fine-grained tokens. Минимальные права: `repo`, `issues`.

## Примеры использования

**Управление задачами:**
```
→ "Создай issue с описанием бага: кнопка оплаты не работает на мобильном"
→ Агент: create_issue(title, body, labels=["bug", "mobile"])
→ Результат: Issue #42 создан
```

**Code review:**
```
→ "Покажи все открытые PR в репо myapp"
→ Агент: list_pull_requests(state="open")
→ Результат: 3 открытых PR с описанием и статусом CI
```

**Поиск по коду:**
```
→ "Найди все места, где используется функция processPayment"
→ Агент: search_code("processPayment", repo="user/myapp")
→ Результат: 4 файла с точными строками
```

**Анализ активности:**
```
→ "Покажи последние коммиты в main за неделю"
→ Агент: list_commits(branch="main", since="7 days ago")
→ Результат: список коммитов с авторами и описаниями
```

## Доступные операции

| Инструмент | Что делает |
|-----------|-----------|
| `create_issue` | Создать issue |
| `list_issues` | Список issues с фильтрами |
| `create_pull_request` | Создать PR |
| `list_pull_requests` | Список PR |
| `search_code` | Поиск по коду |
| `get_file_contents` | Прочитать файл из репо |
| `push_files` | Закоммитить изменения |

## Ссылки

- [GitHub: github MCP](https://github.com/modelcontextprotocol/servers/tree/main/src/github)
- [MCP Servers Registry](https://github.com/modelcontextprotocol/servers)

## Связанное

- [MCP](/concepts/mcp/) — протокол подключения
- [GitHub](/tools/github/) — платформа, к которой подключается сервер
- [GitHub Copilot](/tools/github-copilot/) — нативная интеграция без MCP
- [Claude Code](/tools/claude-code/) — использует gh CLI вместо MCP
