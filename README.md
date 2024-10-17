![example workflow](https://github.com/NikTihomirovv/kittygram_final/actions/workflows/main.yml/badge.svg)

# Описание проекта
Kittygram - это сайт с возможностью создания небольших постов о своих домашних животных, а именно котиков. Вы можете прикрепить фотографию своего питомца, указать небольшое описание в посте, а также выбрать достижение, которое смог получить ваш любимец.

# Стек
* Python 3.9
* Django 3.2.3
* djangorestframework 3.12.4
* Nginx
* Docker

# Как развернуть проект
Как развернуть проект с помощью Docker.
1. Создать директорию: ```python mkdir kittygram```
2. Перейти в нее: cd kittygram
3. Поместить в директорию файл: **docker-compose.production.yml**
4. Выполнить команду: docker compose -f docker-compose.production.yml up
5. Собрать статику: docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
6. Копировать статику: docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/ 
7. Выполнить миграции: docker compose -f docker-compose.production.yml exec backend python manage.py migrate

# Как заполнить env файл
Пример заполнения:
POSTGRES_USER= Пользователь БД.
POSTGRES_PASSWORD= Пароль от БД.
POSTGRES_DB= Имя контейнера с БД.

DB_HOST= Имя БД.
DB_PORT= Порт для БД.

SECRET_KEY= Ключ для настроек в джанго проекте.
ALLOWED_HOSTS= Список доступных хостов. Пример: '127.0.0.1, ' 

# Автор
Автор проекта - Тихомиров Никита - https://github.com/NikTihomirovv
