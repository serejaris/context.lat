---
title: "Claude vs GPT vs Gemini"
description: "Сравнение AI-моделей для кодинга: бенчмарки, цены, контекстное окно, сильные стороны"
date: 2026-03-16
category: "Сравнения"
difficulty: "Начинающий"
weight: 11
tags: ["модели", "anthropic", "openai", "google"]
comparison: true
compared_tools:
  - claude
  - gpt
  - gemini
---

## Зачем сравнивать

Модель — двигатель любого AI-инструмента. Cursor, Claude Code, Windsurf, v0 — все используют LLM под капотом. От выбора модели зависит качество кода, скорость ответа и стоимость. Три главных провайдера: Anthropic (Claude), OpenAI (GPT), Google (Gemini). Плюс открытая альтернатива — DeepSeek.

## Сравнение

| Критерий | [Claude](/models/claude/) | [GPT](/models/gpt/) | [Gemini](/tools/gemini/) |
|----------|--------|-----|--------|
| Провайдер | Anthropic | OpenAI | Google |
| Флагман | Opus 4.6 | GPT-4o / o3 | 2.5 Pro |
| SWE-bench | 80.9% | — | 77.4% |
| Контекст | 1M токенов | 128K (4o) | 2M токенов |
| Free tier | Нет ($20/мес Pro) | Да (GPT-4o free) | Да (AI Studio) |
| Подписка | Pro $20, Max $100-200 | Plus $20, Pro $200 | AI Pro $19.99 |
| API цена (флагман) | $15/1M (Opus) | $2.50/1M (4o) | $1.25/1M (2.5 Pro) |
| Быстрая модель | Haiku $0.25/1M | GPT-4o-mini | Flash $0.15/1M |
| Сильная сторона | Кодинг, агентность, extended thinking | Экосистема, мультимодальность, Codex | Контекст, цена, визуальные артефакты |
| Где доступна | claude.ai, API, Claude Code, Cursor | ChatGPT, API, Codex, Cursor | Gemini, AI Studio, Cursor |

## Open-source альтернатива: DeepSeek

[DeepSeek](/models/deepseek/) стоит отдельно — это полностью открытая модель, которую можно запускать локально.

| Критерий | DeepSeek V3 | DeepSeek R1 |
|----------|-------------|-------------|
| Тип | Общего назначения | Reasoning |
| Параметры | 671B (MoE) | Специализированная |
| API цена | $0.27/1M input | $0.55/1M input |
| Self-hosted | Бесплатно | Бесплатно |

Для тех, кто ценит приватность данных или хочет минимизировать расходы на API.

## Вывод

**[Claude](/models/claude/)** — лучший для кодинга по бенчмаркам. SWE-bench 80.9%, extended thinking для сложных задач, нативная агентность в Claude Code. Если пишешь код — Claude первый выбор.

**[GPT](/models/gpt/)** — самая широкая экосистема и бесплатный доступ. ChatGPT знают все, GPTs и плагины, Codex для фоновой работы. Лучший старт для новичков благодаря free tier.

**[Gemini](/tools/gemini/)** — максимальный контекст (2M токенов) и самые низкие цены на API. Визуально богатые артефакты по умолчанию. Хорош для работы с большими документами и кодовыми базами при ограниченном бюджете.

**[DeepSeek](/models/deepseek/)** — open-source альтернатива с впечатляющим reasoning. Запуск локально или самый дешёвый API среди топовых моделей.

## Связанное

- [Claude](/models/claude/) — подробный обзор
- [GPT](/models/gpt/) — подробный обзор
- [Gemini](/tools/gemini/) — подробный обзор
- [DeepSeek](/models/deepseek/) — подробный обзор
- [С чего начать вайбкодинг](/guides/getting-started/) — выбор инструмента
- [Cursor vs Claude Code vs Windsurf](/guides/cursor-vs-claude-code-vs-windsurf/) — сравнение инструментов, которые используют эти модели
