![example workflow](https://github.com/balahoncevg/kittygram_final/actions/workflows/main.yml/badge.svg)

# Social Network for Cats – Kittygram  

## Project Description:  

### Brief Description:  
The Kittygram project allows you to create profiles for your pets. Each profile can include a photo of the cat, its name, birth year, color, and achievements (if any).  

**In Russian:**  
Проект Kittygram позволяет вам создавать карточки для ваших домашних любимцев. К каждой карточке можно прикрепить фото котика, его имя и год рождения, выбрать цвет и указать его достижения, если такие есть.  

---

### Technologies Used:  

**Backend**:  
- Python 3.10  
- Django 3.2.3  
- Django REST Framework 2.12.4  

**Frontend**:  
- JavaScript  
- HTML  

The project is deployed using **Nginx** and **Docker**.  

**In Russian:**  
Бэкенд написан с использованием следующих технологий:  
- Python 3.10  
- Django 3.2.3  
- DjangoRestFramework 2.12.4  

Фронтенд написан с использованием следующих технологий:  
- JavaScript  
- HTML  

Запуск проекта осуществляется с помощью nginx и docker.  

---

## Project Link:  

**In Russian:**  
Ссылка на проект:


https://kittygram.ddns.net  

---

## Launch Details:  

### How to Launch the Project:  

Clone the repository (if using `docker-compose.yml`) and navigate into it via the command line, or copy only the `docker-compose.production.yml` file:  

**In Russian:**  
Клонировать репозиторий(если используется docker-compose.yml) и перейти в него в командной строке или скопировать только файл docker-compose.production.yml:  

```bash  
git clone https://github.com/balahoncevg/kittygram_final.git  
```  

```bash  
cd kittygram_final  
```  

Run the following commands in sequence:  

**In Russian:**  
Выполнить последовательно команды:  

**Note:**  
To launch the project, you can use either `docker-compose.production.yml` (as shown in the example) or `docker-compose.yml`.  

**In Russian:**  
Примечание: для запуска можно использовать файлы docker-compose.production.yml (как в примере) и docker-compose.yml.  

```bash  
sudo docker compose -f docker-compose.production.yml pull  
sudo docker compose -f docker-compose.production.yml down  
sudo docker compose -f docker-compose.production.yml up -d  
```  

Run migrations and collect static files:  

**In Russian:**  
Выполнить миграции и собрать статические файлы:  

```bash  
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate  
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic  
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/static_backend/. /backend_static/static/  
```  

---

### Differences Between `docker-compose.yml` and `docker-compose.production.yml`:  

**In English:**  
- `docker-compose.yml` creates Docker images based on project files. Suitable for local development with the project copied to your device. Used for making updates or debugging.  
- `docker-compose.production.yml` is designed for use on remote servers. It doesn't build Docker images but pulls them from DockerHub. It does not rely on local project files and is intended for end-user deployment.  

**In Russian:**  
- `docker-compose.yml` позволяет создавать docker образы на основе файлов проекта. Подходит для запуска с устройства, на котором есть копия проекта. Используется для разработки - внесения изменений и исправлений.  
- `docker-compose.production.yml` создан для использования на удаленном сервере. Не создает docker образы, а загружает их с DockerHub, не использует локальные файлы проекта. Подходит для пользовательского запуска.  

---

## Usage:  

To fully utilize the project, register on the site (create a login and password). After registration, users can create and view cat profiles.  

To create a cat profile, click the "Add Cat" button, upload a photo, and provide the required details (achievements are optional). Created profiles can be deleted or edited.  

**In Russian:**  
Для полноценного использования проекта необходимо зарегистрироваться на сайте (создать логин и пароль). После этого пользователю станут доступны возможности создавать и просматривать карточки котиков.  

Для создания карточки котика необходимо нажать на кнопку "Добавить кота", после чего загрузить фото в анкету и указать необходимые данные (достижения являются необязательными). Созданные карточки можно удалять и редактировать.  

---

## About the Author:  

**In English:**  
A Yandex.Practicum student specializing in Python Backend development.  

**In Russian:**  
Студент Яндекс.Практикума на направлении Python Backend.  
