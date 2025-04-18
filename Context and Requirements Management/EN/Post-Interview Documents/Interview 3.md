# Introduction

**Version:** 1.1

**Last Edit:** 13/04/2025

**Last Editor:** Kirill Korikov

**Owner:** Kirill Korikov

**Approval Status:** Not subject to approvals

**Type:** Post-interview

**Description:** This document is a summary of interview with the customer.

**Dependencies:**
 - [Generic Document Template](DocumentTemplates\EN\Generic Document Template.md)

# Justifications
This document exists as a record of the interview with the customer.

# Content

## Customer feedback on demo  
- Согласован график регулярных демо (раз в две недели) для демонстрации прогресса.  
- Первое демо удовлетворило клиента

## New requirements  
- **Функциональные требования**:  
  - Баланс между **качеством ответов** и **скоростью генерации**.  
  - REST API для интеграции с тестовым окружением (например, Telegram-бот).  
  - Система оценки ответов:  
    - Балльная шкала (1-10) + чек-лист критериев.  
    - Пример формы-опросника для тестировщиков.  
- **Технические требования**:  
  - Развертывание на VPS/VDS **без GPU** (предварительное решение).  

## Changes to old requirements  
- **Аппаратные требования**: Отказ от GPU (NVIDIA 4090) в пользу VPS/VDS.  
- **Сроки**: Уточнение этапов:  
  - MVP к началу апреля (поддержка 3-4 разработчиков).  
  - Финальный продукт — к концу мая.  

## New requests  
**What future artifacts did the customer request?**  
- Пример формы для оценки ответов модели.  

**What we requested from the customer?**  
- Подтверждение двухнедельного цикла встреч.  
- Банк из 10-20 тестовых вопросов от команды ОМП.  

## New information  
### Организационные детали:  
- **Тестирование**:  
  - Использование Google Forms или Telegram-бота для сбора оценок.  
- **Стейкхолдеры**:  
  - Евсеев Сергей: ключевой контакт по документации.  
- **Таймлайн**:  
  - Общий срок проекта: 3-4 месяца.  
  - Демо-сессии каждые две недели.  
- **Аппаратные ресурсы**:  
  - Решение о выделении машины ожидается на следующей неделе.  
  - Высокая вероятность использования CPU-серверов (без GPU).  

# Changelog
- v1.1. 13/04/2025 Kirill Korikov updated the document to the new template.