# Effective Mobile Docker Project

## Описание
Простое веб-приложение на Python с обратным прокси через Nginx.

## Структура проекта


em/
├── backend
│   ├── app.py
│   └── Dockerfile
├── docker-compose.yml
├── nginx
│   └── nginx.conf
└── README.md



## Запуск проекта
1. Собрать и поднять контейнеры:

/em ```bash
docker compose up --build

