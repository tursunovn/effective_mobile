# Effective Mobile Docker Project

## Описание
Простое веб-приложение на Python с обратным прокси через Nginx.  
Проект демонстрирует работу Docker и Docker Compose с двумя сервисами: backend и nginx.

## Структура проекта

em/
├── backend/
│ ├── Dockerfile
│ └── app.py
├── nginx/
│ └── nginx.conf
├── docker-compose.yml
└── README.md



## Как запустить проект
1. Перейти в корень проекта:
```bash
cd em

docker compose up --build


curl http://localhost:8080

ожидаемый ответ:

Hello from Effective Mobile!


Как работает схема

Nginx принимает HTTP-запросы на порту 80 внутри контейнера (8080 на хосте)

Все запросы на / проксируются на backend-сервис (Python http.server)

Backend возвращает простой текст: "Hello from Effective Mobile!"



Схема:


[User] → [Nginx (8080:80)] → [Backend (em-backend:8080)]

или:

       ┌─────────┐
       │  User   │
       └────┬────┘
            │ HTTP Request (port 8080)
       ┌────▼────┐
       │  Nginx  │
       │(8080:80)│
       └────┬────┘
            │ Proxy_pass
       ┌────▼──────────┐
       │ em-backend    │
       │(Python server)│
       └───────────────┘




## Технологии
- Docker
- Docker Compose
- Python 3.12 (http.server)
- Nginx 1.25-alpine

