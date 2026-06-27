# SDUI Resource Project Instructions

## О проекте
Этот репозиторий содержит Server-Driven UI (SDUI) JSON-ресурсы для Flutter-приложения odds_project.

Библиотека скилов и агентов доступна через submodule: `.github/standards/`

- **Базовые скилы** (общие): `.github/standards/base/skills/`
- **Проектные скилы** (odds_project_resource): `.github/standards/projects/odds_project_resource/skills/`
- **Агенты**: `.github/standards/projects/odds_project_resource/agents/`
- **Обновление**: `git submodule update --remote .github/standards`

## Структура
- `app/assets/ui_resources/init_response.json` — контракты и транспорт
- `app/assets/ui_resources/{locale}/` — ресурсы для каждой локали:
  - `feeds/` — конфигурация источников данных
  - `menu_items/` — пункты меню
  - `structure/` — shell-структура приложения
  - `theme/` — дизайн-токены (Material 3 color scheme)
  - `ui/` — UI-описания экранов (home, matches, news, offers)

## Локали
- `en/` — английский
- `ru/` — русский
- `mx/` — мексиканский испанский

**Важно:** всегда синхронизируй изменения между всеми тремя локалями.

## Деплой
- Автоматический при пуше в `main` (GitHub Actions)
- Целевой сервер: `141.105.64.214:/www/parser_project/resours/app/lg/v2/ui_resources/`
- Вручную: SCP с ключом `id_ed25519_hostkey_141_105_64_214`

## Flutter-фреймворк
Приложение использует **Stac** (Server-Driven UI for Flutter).
- GitHub: https://github.com/StacDev/stac
- Pub.dev: https://pub.dev/packages/stac
- Документация: https://docs.stac.dev

## Доступные агенты
- **SDUI UI/UX Agent** (`.github/standards/projects/odds_project_resource/agents/sdui-ui-agent.agent.md`) — для работы с SDUI ресурсами
- **SDUI UI/UX Agent (локальный резерв)** (`.github/agents/sdui-ui-agent.agent.md`)

## Доступные скилы
- `sdui-json-schema` — SDUI JSON формат и виджеты
- `sdui-deployment` — деплой на сервер
- `stac-framework` — официальный Stac SDK (виджеты, парсеры, рендеринг, инициализация)
- Базовые скилы из `base/skills/` — автоматически доступны через submodule

## Язык
- Ответы и комментарии — на русском языке
- JSON-файлы — на английском (контент для пользователей)
