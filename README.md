# Kittygram — сервис анкет котиков

![CI/CD](https://github.com/NChikurov/kittygram_final/actions/workflows/main.yml/badge.svg)

**Kittygram** — веб-приложение, где пользователи могут публиковать анкеты своих котов: добавлять имя, породу и фотографию. Проект развёрнут в контейнерах и использует CI/CD для автоматического деплоя.

---

## Функциональность

- Регистрация и авторизация пользователей
- Создание, просмотр и удаление анкет котов
- Загрузка изображений питомцев
- Выбор породы из списка
- API для работы с анкетами

---

## Стек технологий

- Python 3.9
- Django + Django REST Framework
- PostgreSQL
- Docker
- Gunicorn
- Nginx

---

## Как развернуть проект

### Клонируйте репозиторий:

```bash
git clone https://github.com/username/kittygram_final.git
cd kittygram_final

Создайте .env в корне проекта:

SECRET_KEY=ваш_секретный_ключ
DEBUG=False
ALLOWED_HOSTS=ваш_домен.com
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432

Соберите и запустите контейнеры:

docker-compose up -d --build

Примените миграции и соберите статику:

docker-compose exec backend python manage.py migrate
docker-compose exec backend python manage.py collectstatic --noinput

После запуска проект будет доступен по адресу http(s)://ваш_домен.com
