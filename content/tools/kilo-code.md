---
title: "Kilo Code"
description: "Open source AI-агент для VS Code — бесплатная альтернатива Cursor с любыми моделями"
date: 2026-03-16
provider: "Kilo"
item_type: "Плагин"
pricing:
  free: true
  from: "$0 (свой API-ключ)"
  tiers:
    - name: "Свой ключ"
      price: "$0 + API costs"
    - name: "Kilo Pass"
      price: "от $19/мес"
website: "https://kilo.ai"
features:
  - "Open source (форк Cline)"
  - "Подключение любых моделей"
  - "Свой API-ключ или Kilo Pass"
  - "Поддержка новых моделей через OpenRouter"
weight: 7
category: "IDE и редакторы"
category_weight: 2
tags: ["ide", "промпты"]
---

## Обзор

Kilo Code — open source расширение для VS Code, форк Cline. Подключается к любым моделям через свой API-ключ или Kilo Pass. Работает как бесплатная альтернатива [Cursor](/tools/cursor/) с доступом к новейшим моделям через OpenRouter.

На Уроке 2, когда Cursor упал под нагрузкой, группа переключилась на VS Code + Kilo Code — и продолжила работу.

## Быстрый старт

1. Установить VS Code
2. Установить расширение Kilo Code из маркетплейса
3. Подключить модель:
   - **OpenRouter**: вставить API-ключ → выбрать модель (Claude, GPT, Kimi K2.5)
   - **Kilo Pass**: подписка от $19/мес, модели включены

4. Открыть панель Kilo Code и описать задачу:

```
Создай скрипт для публикации постов в Telegram-канал.
Python, aiogram, читать посты из папки drafts/.
```

## Когда использовать

| Ситуация | Почему Kilo Code |
|----------|-----------------|
| Cursor упал | Резервный вариант в VS Code |
| Нужны новые модели | GLM 5.0, Kimi K2.5 через OpenRouter |
| Бюджет ограничен | Бесплатно со своим API-ключом |
| Уже используешь VS Code | Не нужно переезжать в другой редактор |

## Сравнение с альтернативами

| Критерий | Kilo Code | [Cursor](/tools/cursor/) | GitHub Copilot |
|----------|-----------|--------|----------------|
| Цена | $0 + API | $20/мес | $10/мес |
| Базовый редактор | VS Code | VS Code (форк) | VS Code |
| Модели | Любые через OpenRouter | Claude, GPT, Gemini | Claude Opus 4.6 и др. |
| Open source | Да | Нет | Нет |
| Расширения VS Code | 100% совместимость | ~95% | 100% |

## В курсе

| Урок | Контекст |
|------|----------|
| Урок 2 | Резервный вариант, когда Cursor упал. Студенты переключились на VS Code + Kilo Code и продолжили создание Telegram-бота |

## Ссылки

- [Kilo Code](https://kilo.ai)
- [GitHub](https://github.com/kilocode/kilo-code)
- [OpenRouter — маркетплейс моделей](https://openrouter.ai)

## Связанное

- [Cursor](/tools/cursor/) — платная альтернатива
- [Claude Code](/tools/claude-code/) — терминальная альтернатива
- [Windsurf](/tools/windsurf/) — ещё одна AI-IDE
- [GitHub Copilot](/tools/github-copilot/) — встроенный в VS Code
