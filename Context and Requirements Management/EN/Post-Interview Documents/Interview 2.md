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
**What was the customer feedback on the demo?**  
- Прямой обратной связи по демо не предоставлено.  

## New requirements  
**What new requirements were elicited?**  
- **Аппаратные требования**:  
  - GPU уровня NVIDIA 4090 (20-30 ГБ памяти).  
  - 0.25-0.5 ТБ оперативной памяти.  
- **Функциональные требования**:  
  - Чат-бот должен работать **на русском языке** (даже если документация содержит английские фрагменты).  
  - Решение должно быть proof-of-concept (не MVP), ориентировано на проверку реализуемости для ~10 разработчиков.  
  - Четкое описание интерфейсов взаимодействия с моделью (API, виджет и т.д.).  
- **Ограничения**:  
  - Запрет на использование внешних ресурсов во время работы (включая облачные сервисы).  
  - Обязательное подписание NDA для доступа к инфраструктуре.  

## Changes to old requirements  
**What changes are applied to old requirements (if any)?**  
- **Сужение масштаба**: Проект переориентирован на proof-of-concept вместо полноценного сервиса.  
- **Языковые требования**: Уточнено, что ответы должны быть строго на русском, несмотря на наличие англоязычных фрагментов в документации.  

## New requests  
**What future artifacts did the customer request?**  
- Техническое обоснование требований к железу/софту для согласования с IT-отделом.  
- Добавление GitLab-репозиториев в документацию продукта ([Demos](https://gitlab.com/omprussia/demos), [Examples](https://gitlab.com/omprussia/examples)).  

**What we requested from the customer?**  
- Доступ к публичной документации Aurora (раздел ["Руководства и примеры"](https://developer.auroraos.ru/doc/5.1.1/software_development/guides)).  
- Юридическое согласование доступа к данным.  

## New information  
**What new information is gained?**  
### Организационные детали:  
- **Стажировка**:  
  - Оплата делится на всю группу (часть ставки стажёра).  
  - Иностранные участники не могут быть официально трудоустроены.  
- **Документация**:  
  - Публичные репозитории GitLab содержат примеры кода и демо.  
  - Общий объём документации ~2000 файлов, но для начала достаточно 100-200 ключевых.  
- **Стейкхолдеры**:  
  - Камилла Котухова: руководитель проектов по образовательной среде.  
  - Рафаэль: ответственный за соглашения о доступе.  
- **Технические нюансы**:  
  - Рабочий график компании: 5/2 (учтено для взаимодействия с отделами).  
  - Возможность использования ресурсов Иннополиса для работы с моделями (требует уточнения).  
**What new information is gained?**  
- **Stakeholder roles**:  
  - Anastasiya Bozhko: Manages developer interaction/support (tools, feedback).  
  - Anastasiya Krukovets: Oversees student activity and R&D.  
  - Andrey Suvorov: Maintains dev portal and automation tools.  
  - Evseev Sergey: Documentation developer.  
  - Kirill: Director of the support department.  
- **Reference product**: Similar functionality to ChatPDF.  
- **Organizational notes**:  
  - Chatbot deployment must allow for custom documentation/content.  
  - Open-source licensing compliance is critical.  

# Changelog
- v1.1. 13/04/2025 Kirill Korikov updated the document to the new template.