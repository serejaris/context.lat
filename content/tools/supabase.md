---
title: "Supabase"
description: "Backend-as-a-Service: PostgreSQL база данных и авторизация для AI-билдеров"
date: 2026-03-16
provider: "Supabase"
item_type: "Платформа"
pricing:
  free: true
  from: "$0 (free tier)"
  tiers:
    - name: "Free"
      price: "$0"
    - name: "Pro"
      price: "$25/мес"
website: "https://supabase.com"
features:
  - "PostgreSQL база данных"
  - "Авторизация в один клик"
  - "Интеграция с V0, Lovable, Bolt"
  - "Real-time подписки"
weight: 11
category: "Инфраструктура"
category_weight: 4
tags: ["инфраструктура", "бэкенд"]
---

## Обзор

Supabase — backend-as-a-service на PostgreSQL. Добавляет базу данных и авторизацию к приложениям в AI-билдерах ([V0](/tools/v0/), [Lovable](/tools/lovable/), [Bolt](/tools/bolt/)) без написания бэкенд-кода. Бесплатный тариф подходит для MVP и учебных проектов.

## Быстрый старт

### Подключение к V0

1. Создать проект на [supabase.com](https://supabase.com) → получить **URL** и **anon key**
2. В V0: нажать кнопку подключения Supabase → вставить ключи
3. V0 автоматически настраивает схему таблиц
4. Авторизация через email/Google — подключается в один клик в настройках проекта Supabase

**Результат:** данные приложения (подписки, привычки, пользователи) хранятся в PostgreSQL на серверах Supabase. Приложение из одноразового прототипа превращается в полноценный продукт с базой данных.

### Подключение к Lovable / Bolt

Процесс аналогичный: создать проект → скопировать URL и ключ → вставить в настройках билдера. Все три AI-билдера имеют встроенную интеграцию с Supabase.

## Ключевые возможности

- **PostgreSQL** — полноценная реляционная база данных, не NoSQL-костыль
- **Auth** — авторизация через email, Google, GitHub, Apple в один клик
- **Real-time** — подписки на изменения в таблицах (для чатов, дашбордов)
- **Row Level Security (RLS)** — каждый пользователь видит только свои данные
- **Edge Functions** — серверные функции на Deno (TypeScript)
- **Storage** — хранение файлов (аватары, документы)

## Пример: трекер подписок

На Уроке 1 студенты создают трекер подписок в V0 и подключают Supabase:

```sql
-- Таблица подписок (создаётся автоматически через V0)
create table subscriptions (
  id uuid primary key default gen_random_uuid(),
  user_id uuid references auth.users,
  name text not null,
  price decimal not null,
  billing_cycle text default 'monthly',
  next_payment date,
  created_at timestamptz default now()
);

-- RLS: каждый видит только свои подписки
alter table subscriptions enable row level security;
create policy "Users see own subscriptions"
  on subscriptions for select
  using (auth.uid() = user_id);
```

## Тарифы

| План | Цена | Ограничения |
|------|------|-------------|
| Free | $0 | 2 проекта, 500MB БД, 1GB storage |
| Pro | $25/мес | 8GB БД, 100GB storage, daily backups |

Бесплатного тарифа достаточно для MVP и учебных проектов.

## В курсе

| Урок | Контекст |
|------|----------|
| Урок 1 | Подключение Supabase к V0 для добавления базы данных и авторизации к трекеру подписок |
| Урок 2 | Упомянут как инструмент синхронизации между AI-билдерами через GitHub |

## Ссылки

- [Supabase Documentation](https://supabase.com/docs)
- [Quick Start Guide](https://supabase.com/docs/guides/getting-started)
- [Интеграция с V0](https://supabase.com/docs/guides/getting-started/ai-prompts/nextjs)

## Связанное

- [V0](/tools/v0/) — AI-билдер, с которым Supabase интегрируется напрямую
- [Lovable](/tools/lovable/) — AI-билдер с интеграцией Supabase
- [Bolt](/tools/bolt/) — AI-билдер с интеграцией Supabase
- [PRD](/concepts/prd/) — в PRD указывается стек, включая Supabase
