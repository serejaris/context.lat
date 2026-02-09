---
title: "Playwright MCP"
description: "MCP сервер для браузерной автоматизации. Тестирование и скрапинг через AI"
date: 2026-02-09
provider: "Microsoft"
protocol: "MCP"
website: "https://github.com/microsoft/playwright-mcp"
features:
  - "Навигация по страницам"
  - "Клики, ввод текста, формы"
  - "Скриншоты"
  - "Accessibility snapshots"
  - "Console logs и network"
weight: 3
---

## Что это

Playwright MCP сервер позволяет AI управлять браузером: открывать страницы, кликать по элементам, заполнять формы, делать скриншоты.

## Возможности

- Открытие URL и навигация
- Взаимодействие с элементами (клик, ввод, выбор)
- Скриншоты страниц и элементов
- Accessibility snapshot — структура страницы для AI
- Мониторинг console logs и сетевых запросов

## Как подключить

```json
{
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": ["-y", "@playwright/mcp@latest"]
    }
  }
}
```

## Примеры использования

- Автоматическое тестирование UI
- Скрапинг данных с веб-страниц
- Проверка вёрстки и доступности
- Заполнение форм
