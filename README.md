# Описание проекта

## Функциональное описание проекта 
- Доступна регистрация / авторизация
- Добавление нового кота с выбором фотографии, достижений. Есть поля 
для ввода: имя, год рождения
- Изменение данных о коте
- Удаление информации о коте
- Панель администратора

## Стек технологий

### Backend
Python Django

Libraries:
- Django==3.2.3
- djangorestframework==3.12.4
- djoser==2.1.0
- gunicorn==20.1.0
- webcolors==1.11.1
- psycopg2-binary==2.9.3
- Pillow==9.0.0
- pytest==6.2.4
- pytest-django==4.4.0
- pytest-pythonpath==0.7.3
- PyYAML==6.0

### Frontend
JavaScript React

## Развёртка проекта
Для развёртки проекта достаточно выполнить следующие команды:
```shell
docker compose up --build -d
```

```shell
docker container exec kittygram_final-backend-1 python manage.py migrate
```

Также необходимо добавить значения в файл .env
```dotenv
POSTGRES_USER=
POSTGRES_PASSWORD=
POSTGRES_DB=

DB_HOST=db
DB_PORT=5432

SECRET_KEY=
ALLOWED_HOSTS=
```

#  Как работать с репозиторием финального задания

## Что нужно сделать

Настроить запуск проекта Kittygram в контейнерах и CI/CD с помощью GitHub Actions

## Как проверить работу с помощью автотестов

В корне репозитория создайте файл tests.yml со следующим содержимым:
```yaml
repo_owner: ваш_логин_на_гитхабе
kittygram_domain: полная ссылка (https://доменное_имя) на ваш проект Kittygram
taski_domain: полная ссылка (https://доменное_имя) на ваш проект Taski
dockerhub_username: ваш_логин_на_докерхабе
```

Скопируйте содержимое файла `.github/workflows/main.yml` в файл `kittygram_workflow.yml` в корневой директории проекта.

Для локального запуска тестов создайте виртуальное окружение, установите в него зависимости из backend/requirements.txt и запустите в корневой директории проекта `pytest`.

## Чек-лист для проверки перед отправкой задания

- Проект Taski доступен по доменному имени, указанному в `tests.yml`.
- Проект Kittygram доступен по доменному имени, указанному в `tests.yml`.
- Пуш в ветку main запускает тестирование и деплой Kittygram, а после успешного деплоя вам приходит сообщение в телеграм.
- В корне проекта есть файл `kittygram_workflow.yml`.
