


# Базовый образ
FROM python:3.12-slim

# Создаем пользователя
RUN useradd -m appuser

# Рабочая директория
WORKDIR /app

# Копируем приложение
COPY app.py .

# Меняем пользователя
USER appuser

# Документируем порт
EXPOSE 8080

# CMD запускает сервер
CMD ["python", "app.py"]

# Healthcheck для контейнера
HEALTHCHECK --interval=10s --timeout=3s --start-period=5s --retries=3 \
  CMD curl -f http://localhost:8080/ || exit 1

