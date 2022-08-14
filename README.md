![Yamdb Workflow Status](https://github.com/lapanthera161/foodgram-project-react/actions/workflows/diploma_main.yml/badge.svg?branch=master&event=push)
# Foodgram, «Продуктовый помощник»

## Описание

«Продуктовый помощник»: это ресурс, на котором пользователи публикуют рецепты, добавляют чужие рецепты в избранное и подписываются на публикации других авторов. 

Проект развернут по адресу: http://51.250.19.35/


# Шаблон наполнения .env (не включен в текущий репозиторий) расположенный по пути infra/.env 
``` 
DB_ENGINE=django.db.backends.postgresql 
DB_NAME=postgres 
POSTGRES_USER=postgres 
POSTGRES_PASSWORD=postgres 
DB_HOST=db 
DB_PORT=5432 
``` 
## Как запустить проект в Docker контейнере


- Установите Docker.

Параметры запуска описаны в файлах `docker-compose.yml` и `nginx.conf` которые находятся в директории `infra/`

- Запустите docker compose:

```bash
docker-compose up -d --build
```  

  > После сборки появляются 3 контейнера:
  >
  > 1. контейнер базы данных **db**
  > 2. контейнер приложения **backend**
  > 3. контейнер web-сервера **nginx**
  >
- Выполните миграции:

```bash
docker-compose exec backend python manage.py migrate
```

- Запустите процесс загрузки ингредиентов:

```bash
docker-compose exec backend python manage.py load_ingrs
```

- Запустите процесс загрузки тегов:

```bash
docker-compose exec backend python manage.py load_tags
```

- Создайте суперпользователя:

```bash
docker-compose exec backend python manage.py createsuperuser
```

- Заупстите процесс сбора статики:

```bash
docker-compose exec backend python manage.py collectstatic --no-input
```


# Шаблон наполнения .env (не включен в текущий репозиторий) расположенный по пути infra/.env 
``` 
DB_ENGINE=django.db.backends.postgresql 
DB_NAME=postgres 
POSTGRES_USER=postgres 
POSTGRES_PASSWORD=postgres 
DB_HOST=db 
DB_PORT=5432 
```

### admin

```login
ei.govorova@yandex.ru
```
```pass
12345q
```