# Kittygram

[![Kittygram Workflow](https://github.com/nnnastt/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/nnnastt/kittygram_final/actions/workflows/main.yml)

## 📖 Описание проекта

Kittygram - это социальная сеть для котиков. Пользователи могут:
- Создавать профили своих питомцев
- Делиться фотографиями

## 🛠 Технологии

- **Backend:** Django 5.1, Django REST Framework, PostgreSQL
- **Frontend:** React, Node.js
- **DevOps:** Docker, Docker Compose, Nginx, GitHub Actions
- **CI/CD:** GitHub Actions, Docker Hub

## 🚀 Как развернуть проект

### Предварительные требования
- Docker и Docker Compose
- Сервер с Ubuntu
- Домен (опционально)

### Локальный запуск

```bash
# Клонировать репозиторий
git clone https://github.com/nnnastt/kittygram_final.git
cd kittygram_final

# Создать .env файл
cat > .env << 'EOF'
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
POSTGRES_DB=kittygram
DB_HOST=db
DB_PORT=5432
DJANGO_SECRET_KEY=а тут секретик
DJANGO_DEBUG=True
DJANGO_ALLOWED_HOSTS=localhost,127.0.0.1
EOF

# Запустить контейнеры
docker compose up -d

# Выполнить миграции
docker compose exec backend python manage.py migrate

# Собрать статику
docker compose exec backend python manage.py collectstatic --noinput

## Автор
https://github.com/nnnastt
