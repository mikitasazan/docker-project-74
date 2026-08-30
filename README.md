## JS Fastify Blog в Docker Compose

[![Actions Status](https://github.com/mikitasazan/docker-project-74/actions/workflows/hexlet-check.yml/badge.svg)](https://github.com/mikitasazan/docker-project-74/actions)

Учебный проект по упаковке Fastify-блога в Docker Compose. Приложение лежит в
`app/`, Caddy работает как reverse proxy, а SQLite используется для локального
запуска без внешней базы.

## Требования

- Docker Engine с Compose v2;
- 2 ГБ свободной памяти для сборки Node.js-зависимостей.

## Запуск

```bash
docker compose up --build
```

Откройте http://localhost:8080 после запуска. Остановите сервис:

```bash
docker compose down
```

Для проверки reverse proxy используйте профиль из override-файла:

```bash
docker compose -f docker-compose.yml -f docker-compose.override.yml up --build
```

В этом режиме Caddy доступен на порту 80 и передаёт запросы в приложение.

## Команды приложения

```bash
cd app
make install
make db-migrate
make lint
make test
make build
```

Переменные базы данных задаются через `app/.env`; пример находится в
`app/.env.example`. Продакшен-сборка использует `app/Dockerfile`, а локальная
разработка — `docker-compose.override.yml`. Makefile использует
`npx pnpm@11.20.0`, поэтому глобально устанавливать pnpm не требуется.
