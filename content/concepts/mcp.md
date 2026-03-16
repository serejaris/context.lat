---
title: "MCP (Model Context Protocol)"
description: "Открытый стандарт Anthropic для подключения AI-агентов к внешним инструментам, данным и сервисам"
date: 2026-03-16
category: "Основы"
difficulty: "Начинающий"
weight: 3
tags: ["mcp", "anthropic"]
---

## Определение

Model Context Protocol — открытый стандарт, опубликованный Anthropic в ноябре 2024 года, который стандартизирует способ подключения AI-агентов к внешним инструментам. До MCP каждая интеграция требовала кастомного кода; MCP предоставляет единый протокол: MCP-сервер описывает свои инструменты, агент (MCP-клиент) их обнаруживает и вызывает.

OpenAI и Google DeepMind приняли стандарт — он стал отраслевым.

## Как это работает

```
Claude Code (MCP-клиент)
    │
    ├── EXA MCP ─────── веб-поиск
    ├── Playwright MCP ─ управление браузером
    ├── Postgres MCP ─── запросы к БД
    └── GitHub MCP ───── issues, PR, repos
```

Без MCP [Claude Code](/tools/claude-code/) умеет читать/писать файлы и запускать команды. С MCP — управлять браузером, искать в интернете, обращаться к базам данных, работать с Notion и любым другим сервисом.

## Быстрый старт

### Подключить MCP-сервер

```bash
# Hosted (рекомендуется, без API-ключа)
claude mcp add --transport http exa https://mcp.exa.ai/mcp

# Локальный через npm
claude mcp add exa -- npx -y exa-mcp-server

# Проверить подключённые серверы
claude mcp list
```

### Использовать

После подключения агент сам решает, когда использовать MCP. Натыкается на ошибку → ищет через EXA. Нужно проверить вёрстку → открывает браузер через Playwright.

## Популярные MCP-серверы

| Сервер | Для чего | Страница |
|--------|---------|----------|
| [EXA](/mcp/exa/) | Веб-поиск по смыслу | Must-have |
| [Playwright](/mcp/playwright/) | Автоматизация браузера, тестирование | Для фронтенда |
| [Postgres](/mcp/postgres/) | Запросы к базе данных | Для бэкенда |
| [GitHub](/mcp/github/) | Issues, PR, repos | Для управления проектом |
| [Filesystem](/mcp/filesystem/) | Расширенная работа с файлами | Встроено в Claude Code |
| [Context7](/mcp/context7/) | Документация библиотек | Актуальные доки |

## Практический совет

**Не подключайте больше двух MCP-серверов одновременно.** Описания инструментов каждого сервера занимают место в [контекстном окне](/concepts/context/) — при трёх и более серверах это может съесть 10%+ контекста, ухудшая качество ответов.

Рекомендация: EXA + один специализированный сервер под задачу.

## В курсе

| Урок | Контекст |
|------|----------|
| Урок 4 | MCP — одна из трёх core-концепций урока (наряду со Skills и Rules). Подключение EXA и Chrome DevTools. Правило: максимум 2 MCP одновременно. Встроенный Fetch в Claude Code медленный и ломает контекст — EXA лучше |

## Ссылки

- [Introducing the Model Context Protocol — Anthropic](https://www.anthropic.com/news/model-context-protocol)
- [Спецификация MCP](https://modelcontextprotocol.io/specification/2025-11-25)
- [MCP Server Registry](https://modelcontextprotocol.io/servers)
- [Wikipedia: Model Context Protocol](https://en.wikipedia.org/wiki/Model_Context_Protocol)

## Связанное

- [Claude Code](/tools/claude-code/) — основной MCP-клиент
- [EXA MCP](/mcp/exa/) — must-have для веб-поиска
- [Playwright MCP](/mcp/playwright/) — автоматизация браузера
- [Контекст](/concepts/context/) — MCP-серверы занимают место в контекстном окне
- [Skills](/concepts/skill/) — скиллы используют MCP как инструменты
