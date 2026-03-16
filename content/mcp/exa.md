---
title: "Exa MCP"
description: "MCP сервер для поиска в интернете. Семантический поиск для AI"
date: 2026-02-09
provider: "Exa"
protocol: "MCP"
website: "https://github.com/exa-labs/exa-mcp-server"
features:
  - "Семантический поиск"
  - "Поиск кода и документации"
  - "Исследование компаний"
  - "Контент оптимизирован для LLM"
weight: 5
tags: ["mcp", "автоматизация"]
---

## Что это

Exa MCP сервер даёт AI возможность искать информацию в интернете. В отличие от обычного поиска, Exa оптимизирован для AI — возвращает чистый контент, готовый к обработке. В отличие от встроенного `fetch` в [Claude Code](/tools/claude-code/), Exa не ломает [контекстное окно](/concepts/context/) мусором из HTML.

## Как подключить

```bash
claude mcp add exa -- npx -y exa-mcp-server
```

Нужен API-ключ (1000 бесплатных кредитов при регистрации на [exa.ai](https://exa.ai)):

```json
{
  "mcpServers": {
    "exa": {
      "command": "npx",
      "args": ["-y", "exa-mcp-server"],
      "env": {
        "EXA_API_KEY": "your-api-key"
      }
    }
  }
}
```

## Примеры использования

**Ресёрч для контент-[пайплайна](/concepts/pipeline/):**
```
→ "Найди топ-5 тем по вайбкодингу за последнюю неделю"
→ Агент: exa_search("vibe coding trends 2026", date_filter="last_week")
→ Результат: 5 статей с заголовками, summary и ссылками
```

**Поиск документации:**
```
→ "Найди документацию по React Server Components"
→ Агент: exa_search("React Server Components documentation")
→ Результат: официальные доки + лучшие туториалы
```

**Исследование конкурентов:**
```
→ "Исследуй компанию Anthropic: последние продукты и новости"
→ Агент: exa_search("Anthropic 2026 products news")
→ Результат: структурированный обзор из актуальных источников
```

## Exa vs fetch vs Perplexity

| Критерий | Exa MCP | fetch (встроенный) | [Perplexity](/tools/perplexity/) |
|----------|---------|-------------------|------|
| Использование | Автоматический поиск агентом | Загрузка конкретной страницы | Ручной ресёрч в браузере |
| Результат | Чистый контент для LLM | Сырой HTML (ломает контекст) | Ответ с источниками |
| Скорость | Sub-200ms (Exa Instant) | Зависит от сайта | 2-5 секунд |
| Стоимость | $5/1000 запросов | Бесплатно | $20/мес |

## В курсе

| Урок | Контекст |
|------|----------|
| Урок 3 | Студентка научила Claude Code использовать Exa вместо стандартного fetch для поиска информации при создании контента |
| Урок 4 | Подключается как MCP-сервер: 1000 бесплатных кредитов, $5-10/мес для реальных задач. Рекомендован вместо fetch |

Подробный гайд с примерами и best practices — в [статье про MCP Exa](/guides/mcp-exa-guide/).

## Ссылки

- [GitHub: exa-mcp-server](https://github.com/exa-labs/exa-mcp-server)
- [Exa Docs](https://exa.ai/docs)
- [Exa Pricing](https://exa.ai/pricing)

## Связанное

- [MCP](/concepts/mcp/) — протокол подключения
- [Гайд по Exa MCP](/guides/mcp-exa-guide/) — подробная инструкция с примерами
- [Context7](/mcp/context7/) — альтернатива для документации библиотек
- [Perplexity](/tools/perplexity/) — ручной AI-поиск для ресёрча
- [Pipeline](/concepts/pipeline/) — Exa как часть контент-пайплайна
