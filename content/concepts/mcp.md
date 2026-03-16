---
title: "MCP (Model Context Protocol)"
description: "Открытый стандарт Anthropic для подключения AI-агентов к внешним инструментам, данным и сервисам"
date: 2026-03-16
category: "Основы"
difficulty: "Начинающий"
weight: 3
---

## Определение

Model Context Protocol — открытый стандарт, опубликованный Anthropic в ноябре 2024 года, который стандартизирует способ подключения AI-агентов к внешним инструментам. До MCP каждая интеграция требовала кастомного кода; MCP предоставляет единый протокол: MCP-сервер описывает свои инструменты, агент (MCP-клиент) их обнаруживает и вызывает.

Без MCP Claude Code умеет читать и писать файлы, запускать команды. С MCP — управлять браузером, делать веб-поиск, обращаться к базам данных, работать с Notion, GitHub и любым другим сервисом.

OpenAI и Google DeepMind приняли стандарт — он стал отраслевым.

## Как подключить MCP-сервер

```bash
# Hosted (рекомендуется, без API-ключа)
claude mcp add --transport http exa https://mcp.exa.ai/mcp

# Локальный через npm
claude mcp add exa -- npx -y exa-mcp-server

# Проверить подключённые серверы
claude mcp list
```

## Практический совет

Не подключайте больше двух MCP-серверов одновременно. Описания инструментов каждого сервера занимают место в контекстном окне — при трёх и более серверах это может съесть 10%+ контекста, ухудшая качество ответов.

## Ссылки

- [Introducing the Model Context Protocol — Anthropic](https://www.anthropic.com/news/model-context-protocol)
- [Спецификация MCP](https://modelcontextprotocol.io/specification/2025-11-25)
- [Wikipedia: Model Context Protocol](https://en.wikipedia.org/wiki/Model_Context_Protocol)
