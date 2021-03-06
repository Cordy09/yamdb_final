# Проект YaMDb

## Описание

Проект yamdb позволяет пользователям оставлять Отзывы на Произведения разных категорий и жанров ("Девятый Вал" Айвазовского или на Аргентинское Танго, например). Пользователи могут оценить призведение по 10-бальной шкале и узнать как в среднем оценили произведение другие пользователи. Если чей-то Отзыв вызовет желание высказаться, Пользователь может оставить к нему Комментарий.


## Как запустить проект

#### Клонировать репозиторий и перейти в него в командной строке

```shell
git clone https://github.com/Cordy09/api_yamdb.git
cd api_yamdb/api_yamdb
```

#### Cоздать и активировать виртуальное окружение

```shell
python3 -m venv env
source env/bin/activate
```

#### Установить зависимости из файла requirements.txt

```shell
python3 -m pip install --upgrade pip
pip install -r requirements.txt
```

#### Выполнить миграции

```shell
python3 manage.py migrate
```

#### Заполнить базу данных файлами

```shell
python3 manage.py csv
```

#### Запустить проект

```shell
python3 manage.py runserver
```

## Регистрация нового пользователя

*Запрос confirmstion_code:*

* http://84.252.142.107:81/api/v1/auth/signup/ - указанием username и email

*Получение токена:*

* http://84.252.142.107:81/api/v1/auth/token/ - указанием username и confirmation_code, который был отправлен в письме на указанную почту

*Персональная страница:*

* http://84.252.142.107:81/api/v1/users/me/ - получение информации о своем профиле(GET) и изменение личных данных(PATCH)

*Произведения:*

* http://84.252.142.107:81/api/v1/titles/ - список всех произведений
* http://84.252.142.107:81/api/v1/titles//{id}/ - информация о конкретном

*Категории произведений:*

* http://84.252.142.107:81/api/v1/categories/ - все категории произведений (GET-запрос)

*Жанры:*

* http://84.252.142.107:81/api/v1/genres/ - все жанры произведений (GET-запрос)

*Отзывы:*

* http://84.252.142.107:81/api/v1/titles/{title_id}/reviews/ - все отзывы к конкретному произведению(GET) и добавление отзыва(POST с указанием  text и score)
* http://84.252.142.107:81/api/v1/titles/{title_id}/reviews/{id}/ - получение определенного отзыва к конкретному произведению

*Комментарии:*

* http://84.252.142.107:81/api/v1/titles/{title_id}/reviews/{review_id}/comments/ - все комментарии к Отзыву(GET) и добавление комментария(POST)
* http://84.252.142.107:81/api/v1/titles/{title_id}/reviews/{review_id}/comments/{comment_id}/ - получение определенного комментария к конкретному отзыву

![example workflow](https://github.com/Cordy09/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)