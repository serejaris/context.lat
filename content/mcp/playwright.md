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
tags: ["mcp", "тестирование"]
---

## Что это

Playwright MCP сервер позволяет AI управлять браузером: открывать страницы, кликать по элементам, заполнять формы, делать скриншоты. Агент видит страницу через accessibility snapshot — структурированное описание элементов, оптимизированное для [LLM](/concepts/llm/).

## Как подключить

```bash
claude mcp add playwright -- npx -y @playwright/mcp@latest
```

Или через JSON-конфиг:

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

**Тестирование UI после деплоя:**
```
→ "Открой https://myapp.com, залогинься с тестовым аккаунтом,
   проверь что дашборд загружается и показывает данные"

→ Агент: navigate → fill login form → click submit →
  snapshot dashboard → проверяет наличие элементов
→ Результат: "Дашборд загружается, 5 виджетов отображаются корректно"
```

**Скрапинг данных:**
```
→ "Собери заголовки и цены из каталога на странице"

→ Агент: navigate → snapshot → извлекает данные из accessibility tree
→ Результат: структурированный список с заголовками и ценами
```

**Проверка вёрстки:**
```
→ "Сделай скриншот главной страницы на мобильном разрешении"

→ Агент: resize viewport 375x812 → navigate → screenshot
→ Возвращает скриншот для визуальной проверки
```

## Ключевые инструменты

| Инструмент | Что делает |
|-----------|-----------|
| `navigate` | Открыть URL |
| `click` | Кликнуть по элементу |
| `fill` | Заполнить поле ввода |
| `screenshot` | Скриншот страницы или элемента |
| `snapshot` | Accessibility-дерево для анализа |
| `evaluate` | Выполнить JavaScript на странице |

## Когда использовать

- **E2E тесты**: агент сам пишет и запускает тестовые сценарии
- **Скрапинг**: извлечение данных из страниц без написания скриптов
- **Проверка деплоя**: автоматическая проверка UI после каждого пуша
- **Заполнение форм**: автоматизация рутинных действий в веб-интерфейсах

## Ссылки

- [GitHub: playwright-mcp](https://github.com/microsoft/playwright-mcp)
- [Playwright Docs](https://playwright.dev)

## Связанное

- [MCP](/concepts/mcp/) — протокол подключения
- [Тестирование с AI](/guides/testing-with-ai/) — гайд по тестированию
- [Claude Code](/tools/claude-code/) — агент, через который работает MCP
- [Дебаг с AI](/guides/debugging-with-ai/) — Playwright помогает визуально верифицировать результат
