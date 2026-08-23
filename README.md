### Hexlet tests and linter status:
[![Actions Status](https://github.com/mikitasazan/docker-project-74/actions/workflows/hexlet-check.yml/badge.svg)](https://github.com/mikitasazan/docker-project-74/actions)
## JS Fastify Blog in Docker Compose

The `app/` directory contains the Fastify Blog application. Docker Compose
installs its dependencies and starts the development server on port 8080.

```bash
docker compose up --build
```

Open <http://localhost:8080> after the container starts. Stop the service with
`docker compose down`.
