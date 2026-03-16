---
title: "Zed"
description: "Сверхбыстрый редактор на Rust с встроенным AI-ассистентом"
date: 2026-02-09
provider: "Zed Industries"
item_type: "IDE"
pricing:
  free: true
  from: "$0 (бесплатный)"
  tiers:
    - name: "Free"
      price: "$0"
    - name: "Pro (AI)"
      price: "$20/мес"
website: "https://zed.dev/"
features:
  - "Написан на Rust — молниеносный"
  - "Open-source"
  - "Встроенный AI-ассистент"
  - "Мультиплеер для парного кодинга"
  - "Кастомные контексты для AI"
weight: 9
category: "IDE"
category_weight: 1
tags: ["ide", "промпты"]
---

## Обзор

Zed — редактор кода нового поколения, написанный на Rust. Открывает проекты мгновенно, без лагов даже на больших кодовых базах. Встроенный AI-ассистент, мультиплеер для совместного кодинга, полностью open-source.

## Быстрый старт

1. Скачать с [zed.dev](https://zed.dev) (macOS или Linux)
2. Открыть проект: `zed ~/my-project`
3. Для AI: Cmd+Enter → чат с ассистентом

## Ключевые возможности

- **Скорость**: написан на Rust, нет Electron-оверхеда (VS Code, Cursor работают на Electron)
- **AI-ассистент**: работает с [Claude](/models/claude/), [GPT](/models/gpt/) и другими моделями
- **Мультиплеер**: совместное редактирование в реальном времени — как Google Docs для кода
- **Кастомные контексты**: можно определить контексты для AI, аналог [CLAUDE.md](/concepts/claude-md/)
- **Open-source**: полностью открытый код

## Zed vs Cursor vs VS Code

| Критерий | Zed | [Cursor](/tools/cursor/) | VS Code |
|----------|-----|--------------------------|---------|
| Скорость | Мгновенно (Rust) | Средне (Electron) | Средне (Electron) |
| AI | Встроенный | Встроенный (сильнее) | Через плагины |
| Agent mode | Нет (пока) | Да | Через Copilot |
| Open-source | Да | Нет | Частично |
| Мультиплеер | Да | Нет | Live Share |
| Платформы | macOS, Linux | macOS, Windows, Linux | Все |

## Когда выбрать Zed

- Скорость редактора критична — большие проекты, частое переключение файлов
- Цените open-source
- Нужен мультиплеер для парного кодинга
- Используете [Claude Code](/tools/claude-code/) как основной агент (IDE нужна только для навигации)

## Когда НЕ выбирать Zed

- Нужен мощный agent mode — у [Cursor](/tools/cursor/) сильнее
- Windows — Zed пока не поддерживает
- Нужна экосистема расширений VS Code
- Привыкли к конкретным плагинам VS Code — в Zed своя экосистема расширений

## Zed + Claude Code

Частый паттерн: Zed для навигации по коду (мгновенно открывает файлы), [Claude Code](/tools/claude-code/) в терминале для агентной работы. Редактор нужен только для чтения — агент пишет сам.

## Ссылки

- [Zed](https://zed.dev)
- [GitHub](https://github.com/zed-industries/zed)

## Связанное

- [Cursor](/tools/cursor/) — альтернатива с более мощным AI
- [Claude Code](/tools/claude-code/) — CLI-агент, работает из любого редактора
- [GitHub Copilot](/tools/github-copilot/) — AI-плагин для VS Code
