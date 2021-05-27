![yamdb_final](https://github.com/Riyce/yamdb_final/actions/workflows/yamdb_workflow.yaml/badge.svg)
<h1> YamDB </h1>
YamDB - проект предназанченный для размещения отзывов на фильмы, музыкальные произведения и книги. <br>У авторизованных пользователей есть возможность оставлять собстенные отзывы к произведениям и комментировать уже существующие.
<hr>
В данном репозитории представлен проект YamDB с возможностью запуска в контейнеах Docker со всеми необходимыми зависимостями.
<hr>

Создайте для проекта директорию:
`mkdir <название директории>`
<br>И сразу перейдите в нее:
`cd <название директории>` <br>
<br>Чтобы загрузить проект необходмо выполнить команду:<br>
`git clone https://github.com/Riyce/infra_sp2`

<h4>
Для запуска проекта необходимо установить Docker.<br>
Инструкции по установке можно найти здесь - https://docs.docker.com/engine/install/ <br>
</h4>

Для развертывания контейнеров необходимо выполнить команду: `docker-compose up -d --build`
<br>Теперь проект доступен по адресу: http://127.0.0.1/
<br> Документация API доступна по адресу: http://127.0.0.1/redoc/
<br> Для корректной работы с приложением необходимо выполнить миграции.
<br> По команде `docker-compose exec web bash` перед вами откроется оболочка Bash контейнера web.
<br> Далее, для выполнения миграций нужно последовательно выполнить следующие команды:
<li> python manage.py makemigrations api
<li> python manage.py migrate
<br> Для создания супрепользователя с доступом в админку выполните следующую команду:
<li> python manage.py createsuperuser
<br> Для заполнения базы данных тестовыми данными выполните следующую команду:
<li> python manage.py loaddata fixtures.json
<br> Для выгрузки данных из базы данных проекта выполните следующую команду:
<li> python manage.py dumpdata > <имя файла>.json
<br> Для выхода из оболочки Bash контейнера просто пропишите команду:
<li> exit
<br> Для остановки работы всех контейнеров выполните команду:
<li> docker-compose stop
<br> Для удаления контейнеров выполните команду:
<li> docker-compose down