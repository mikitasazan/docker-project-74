PNPM ?= npx --yes pnpm@11.20.0

setup: install db-migrate

install:
	$(PNPM) install

db-migrate:
	$(PNPM) run migrate

build:
	$(PNPM) run build

prepare-env:
	cp -n .env.example .env

start:
	NODE_ENV=production $(PNPM) run start

dev:
	pnpm exec concurrently "make start-frontend" "make start-backend"

start-backend:
	npm start -- --watch --verbose-watch --ignore-watch='node_modules .git .sqlite'

start-frontend:
	$(PNPM) exec webpack --watch --progress

lint:
	$(PNPM) --silent run lint
	$(PNPM) --silent run format:check

lint-fix:
	$(PNPM) --silent run lint:fix

test:
	NODE_ENV=test $(PNPM) --silent test
