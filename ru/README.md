# Building a UI Framework — неофициальный перевод на русский

Перевод документа **«Building a UI Framework»** (Ian Hickson, 2025, первое издание).

- Оригинал: https://software.hixie.ch/ui-frameworks
- Анонс автора: https://ln.hixie.ch/?start=1761249101&count=1
- Автор оригинала: Ian Hickson (ian@hixie.ch). Документ написан при финансировании Futurewei Technologies.

Это неофициальный любительский перевод. Автор оригинала не имеет отношения к переводу и не проверял его.
Все права на исходный текст принадлежат автору. Если вы автор и хотите, чтобы перевод был изменён или удалён —
напишите в issues, сделаю сразу.

Структура повторяет оригинал: части, главы и подзаголовки идут в том же порядке.
Технические термины по умолчанию оставлены по-английски; переводятся только те, у которых есть живое русское соответствие.

## Оглавление


### Building a UI Framework

- [Введение](01-introduction.md)
  - Об авторе

### Вводная часть

- [Приложения](02-background.md)
- [Архитектуры приложений](02-background.md)
  - Без данных, только UI
  - Данные и UI вперемешку, без абстракций
  - Разделение данных и UI (Model – View)
  - Логика в модели (разделение логики и UI)
  - Событийная модель
  - Модель уведомляет слушателей (pub/sub)
  - Изолированные данные и UI (Model – View – Controller)
  - Представление уведомляет слушателей
  - Привязка данных (Model – View – View Model/Binder)
  - Двусторонняя привязка
  - Entity – Component – System
  - Клиент – сервер
  - Установленные приложения
  - Эфемерные приложения
  - Server-side rendering
  - Разделение стиля и семантики
- [Что такое UI-фреймворк?](02-background.md)
  - Составные части UI-фреймворка
  - Общие понятия
- [Пространство проектирования](02-background.md)
- [Требования](02-background.md)
  - Графический пользовательский интерфейс
  - Поддержка нескольких платформ
  - Платформенные соглашения
  - Ввод и вывод
  - Возможности компоновки

### Цели

- [Цель: максимизировать developer adoption](04-goal-developer-adoption.md)
  - Определение конкурентного ландшафта
  - Обзор популярных фреймворков
  - Факторы, влияющие на developer adoption
  - Расширение общего множества разработчиков
  - Потенциал
  - Оценка успеха
- [Цель: максимизировать производительность](05-goal-performance.md)
  - Time to first frame
  - Interframe performance
  - Pipeline latency
  - Проектирование с учётом производительности
  - Потенциал
  - Оценка успеха
- [Цель: максимизировать диапазон возможных визуальных эффектов](06-goal-display-effects.md)
  - Типы эффектов
  - Потенциал
  - Оценка успеха
- [Цель: минимизировать энергопотребление](07-goal-power-consumption.md)
  - Проектирование
  - Потенциал
  - Оценка успеха

### Проектные решения

- [Юзабилити-тестирование](09-usability-testing.md)
  - Методологии юзабилити-тестирования
  - Риски
  - Формирование культуры тестирования проектных решений
- [Composition](10-composition.md)
  - Type-agnosticism in composition
- [Immediate-mode UI vs retained-mode UI](11-immediate-vs-retained.md)
  - Pure retained-mode UI
  - Pure immediate-mode UI
  - Immediate-mode UI API with a retained-mode layout backend
  - Separate approaches for layout and UI
  - Uniform approach for layout and UI, layered over a separate render object backend
  - Merged immediate-mode UI and retained-mode layout backend
- [Деревья](12-trees.md)
  - Modeling trees
  - Managing children
  - Storing child-specific data
  - Managing parents
  - Node lifetimes
  - Dirty tracking and depth sorting
  - Tree context
- [Как соответствовать соглашениям платформы](13-platform-conventions.md)
  - Rendering через системные API
  - Использование настоящих элементов управления ОС
  - Имитация
  - Вывод
- [Theming](14-theming.md)
  - Определить подмножество свойств как themeable
  - Property bags
  - Styling language
  - Composition
  - Extension
  - Смешанный подход
- [Platform integration](15-platform-integration.md)
  - Поддержка «из коробки»
- [Ориентация на веб](16-targeting-the-web.md)
  - Поисковая оптимизация (SEO)
- [Языки программирования](17-programming-languages.md)
  - Использование существующего популярного языка
  - Использование языка, позволяющего сделать фреймворк независимым от языка через привязки
  - Создание или адаптация языка, хорошо подходящего для задачи
  - Выбор языка реализации среды
- [Система сборки](18-build-system.md)
  - Format
  - Scope
  - Cross-compiling
- [Сообщения об ошибках](19-error-messages.md)
  - Usefulness
  - Target audience
- [Открытость](20-openness.md)
  - Source availability
  - Development processes
- [Опыт «из коробки»](21-out-of-the-box.md)
  - Installation
  - Dependencies
  - Deferment
  - Templates
  - First target platform
- [State-of-the-art возможности](22-state-of-the-art-features.md)
  - Stateful hot reload
  - Over-the-air updates
  - Server-driven UI
  - Color spaces и различные color depths
  - Vertical text
  - Concurrency
- [Graphics backend](23-graphics-backend.md)
  - Backend technologies
  - Приоритеты производительности
  - Leveraging modern GPUs
- [Render objects](24-render-objects.md)
  - Область охвата
  - Coordinate space
  - Painting и compositing
  - Интеграция со слоями composition или immediate-mode UI
- [IDE](25-ide.md)
- [Проектирование API](26-api-design.md)
  - Устранение ошибок
  - Сохраняйте ортогональность концепций
  - Единообразные naming conventions
  - Следуйте другим фреймворкам
  - Избегайте рекламы в API
  - Рассмотрите введение явного облегчённого процесса API review
  - Основная аудитория API — не эксперт
  - Делайте производительность очевидной
- [Язык программирования](27-programming-language.md)
  - Стоимость
  - Высокоуровневые цели
  - Общий подход
  - Парадигмы программирования
  - Возможности языка
  - Экосистема
  - Чего в языке не будет
  - Долгосрочная стратегия

### Внутреннее устройство фреймворка

- [Компоновка (layout)](29-layout.md)
  - Вводная часть
  - Ограничения и геометрия
  - API
  - Автоматическая генерация компонентов компоновки
- [Painting](30-painting.md)
  - Обзор
  - API
- [Описание UI](31-ui-description.md)
  - Выражение UI
  - Виды виджетов
  - Keying
  - Tree grafting
  - Projection
- [Accessibility](32-accessibility.md)
- [Ввод](33-input.md)
  - Gestures
  - Колёсики мыши и тачпады
  - Клавиатуры
- [Фокус](34-focus.md)
  - Навигация по focus
  - Выбор мышью и касанием
  - Web
- [Текстовый ввод](35-text-input.md)
  - Курсор
  - Выделение
  - Другие важные возможности текстовых полей
  - Реализация
- [Tooling](36-tooling.md)
- [Анимация](37-animation.md)
- [Документация](38-documentation.md)
  - Содержание
  - Тестирование
  - Бесполезная документация
  - Диаграммы
  - Использование документации как проверки на здравый смысл (sanity check)
- [Безопасность цепочки поставок (supply chain security)](39-supply-chain-security.md)
- [Обновление SDK](40-updating-the-sdk.md)
- [Аналитика](41-analytics.md)

### Операционная стратегия

- [Культура команды](43-team-culture.md)
  - Миссия
  - Ценности
  - Влияние решений
  - Опросы
  - Dogfooding
- [Коммуникации](44-communications.md)
  - Репутация
  - Кодекс поведения
  - Issue database
  - Построение сообщества
  - Контент
- [Финансирование](45-funding.md)
  - Лицензирование
  - Support contracts
  - Bundled
  - First-party клиент
  - Эффекты второго порядка
  - Краудфандинг
  - Без финансирования
- [Политика](46-politics.md)
  - Внешняя политика
  - Внутренняя политика
- [Давление](47-pressures.md)
  - Найдите время сделать правильно
  - Не делайте вовсе, если не можете сделать правильно
  - Выпускать рано, выпускать часто
  - Тестируйте
  - Deflake
- [Начальная стратегия](48-initial-strategy.md)
  - Целевая платформа
  - Структура команды и финансирование
- [Безопасность](49-security.md)
  - Шум
- [Тестовая инфраструктура](50-testing-infrastructure.md)

### Заключение

- [Фреймворк на Python](52-python-based-framework.md)
  - Стоимость
  - Риск
  - Потенциал
- [Новый фреймворк на основе юзабилити-исследований](53-usability-research-framework.md)
  - Стоимость
  - Риск
  - Потенциал
- [Заключительные мысли](54-final-thoughts.md)

### Благодарности

