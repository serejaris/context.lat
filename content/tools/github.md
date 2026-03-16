---
title: "GitHub"
description: "Хостинг кода с Issues, Projects и автодеплоем — командный центр вайбкодера"
date: 2026-03-16
provider: "Microsoft"
item_type: "Платформа"
pricing:
  free: true
  from: "$0 (free tier)"
  tiers:
    - name: "Free"
      price: "$0"
    - name: "Pro"
      price: "$4/мес"
    - name: "Team"
      price: "$4/user/мес"
website: "https://github.com"
features:
  - "Хостинг кода"
  - "Issues для задач"
  - "Projects для канбан-досок"
  - "Actions для автоматизации"
  - "Copilot для AI-ассистирования"
weight: 6
category: "Инфраструктура"
category_weight: 4
---

## Обзор

GitHub — платформа для хостинга кода, управления задачами и автоматизации. Для вайбкодера GitHub — командный центр: Issues хранят контекст между сессиями агента, Projects организуют задачи, Actions автоматизируют деплой.

## Для AI-агентов

GitHub Issues — persistent storage для контекста агента между сессиями. В отличие от текстовых файлов, Issues доступны через API, поддерживают фильтрацию и лейблы. Агент фиксирует прогресс в Issues через `gh` CLI и возвращается к контексту при следующем запуске.

## Ключевые связки

- **GitHub + Railway** — пуш в репо -> автодеплой на сервер
- **GitHub + Claude Code** — агент создаёт репо, пушит код, управляет Issues
- **GitHub Projects** — канбан-доска, управляемая агентом через GraphQL API

## Для кого

Для всех, кто работает с кодом. Бесплатного тарифа достаточно для большинства индивидуальных проектов.
