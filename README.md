# yamdb_final
yamdb_final

![workflow yamdb](https://github.com/SimonKabb/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

## Адрес сайта

http://158.160.12.39/redoc/

## Пример запроса

http://158.160.12.39/api/v1/titles/

## Описание

Сайт является - базой отзывов о фильмах, книгах и музыке. Пользователи могут оставлять рецензии на произведения, а также комментировать эти рецензии. Администрация добавляет новые произведения и категории (книга, фильм, музыка и т.д.) Также присутствует файл docker-compose, позволяющий , быстро развернуть контейнер базы данных (PostgreSQL), контейнер проекта django + gunicorn и контейнер nginx

## Как запустить

### Необходимое ПО

Docker: https://www.docker.com/get-started 
Docker-compose: https://docs.docker.com/compose/install/

### Инструкция по запуску

Для запуска необходимо из корневой папки проекта ввести в консоль(bash или zsh) команду:

docker-compose up --build
Затем узнать id контейнера, для этого вводим

docker container ls

docker exec -it <CONTAINER ID> sh
И делаем миграцию БД, и сбор статики

python manage.py migrate
python manage.py collectstatic
При желании можно загрузить тестовую бд с контентом

python manage.py loaddata fixtures.json


## Как пользоваться
После запуска проекта, подробную инструкцию можно будет посмотреть по адресу http://0.0.0.0/redoc/