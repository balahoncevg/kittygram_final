![example workflow](https://github.com/balahoncevg/kittygram_final/actions/workflows/main.yml/badge.svg)

# Социальная сеть для котиков Kittygram

## Описание проекта:

### Краткое описание:

Проект Kittygram позволяет вам создавать карточки для ваших домашних любимцев. К каждой карточке можно прикрепить фото котика, его имя и год рождения, выбрать цвет и указать его достижения, если такие есть.

### Использованные технологии:

Бэкенд написан с использованием следующих технологий:

Python 3.10, Django 3.2.3, DjangoRestFramework 2.12.4

Фронтенд написан с использованием следующих технологий:

javascript, HTML

Запуск проекта осуществляется с помощью nginx и docker

## Ссылка на проект:

https://kittygram.ddns.net

## Подробности запуска:

### Как запустить проект:

Клонировать репозиторий(если используется docker-compose.yml) и перейти в него в командной строке или скопировать только файл docker-compose.production.yml:

```
git clone https://github.com/balahoncevg/kittygram_final.git
```

```
cd kittygram_final
```

Выполнить последовательно команды:

Примечание:
для запуска можно использовать файлы docker-compose.production.yml(как в примере) и docker-compose.yml

```
sudo docker compose -f docker-compose.production.yml pull
sudo docker compose -f docker-compose.production.yml down
sudo docker compose -f docker-compose.production.yml up -d
```

Выполнить миграции и собрать статические файлы:

```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/static_backend/. /backend_static/static/
```

### Различия между docker-compose.yml и docker-compose.production.yml:

docker-compose.yml позволяет создавать docker образы на основе файлов пректа. Подходит для запуска с устройства, на котором есть копия проекта. Используется для разработки - внесения изменений и исправлений.

docker-compose.production.yml создана для использования на удаленном сервере. Не создает docker образы, а загружает их с DockerHub, не использует локальные файлы пректа. Подходит для пользовательского запуска

## Использование:

Для полноценного использования пректа необходимо зарегестрироваться на сайте (создать логи и пароль). После этого ползователю станут доступны возможности создавать и просматривать карточки котиков. для создания карточки котика необходимо нажать на кнопку "Добавить кота", после чего загрузить фото в анкету и указать необходимые данные (достижения являются необязательными). Созданые карточки можно удалать и редактировать.

## Об авторе:

Студент Яндекс.Практикума на нарпралении Python Backend