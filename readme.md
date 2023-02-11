# django-celery
Asynchronous Tasks With Django and Celery desenvolvido durante o tutorial da realpython.com

Esse pequeno projeto foi desenvolvimento acompanhando esse [tutorial](https://realpython.com/asynchronous-tasks-with-django-and-celery/) da realpython.com

Meu propósito é estudar o Celery a aprender com organizar tarefas assíncronas.

## Conteiners services
On your terminal, execute the command to run the docker-compose locally:

`docker-compose -f docker-compose-local.yml up --build`


Two conteiners will be up and running. These conteiners are descibed on docker-compose.yml.
- web
- redis

## Other Commands

After setting up the conteiners, execute the following commands:

`docker-compose -f docker-compose-local.yml exec web python manage.py makemigrations` 

`docker-compose -f docker-compose-local.yml exec web python manage.py migrate`

At this point, the application will be running.

## Celery worker

To start celery worker, run these commands:
`docker-compose -f docker-compose-local.yml exec web python -m celery -A django-celery worker`

`docker-compose -f docker-compose-local.yml exec web python -m celery -A django-celery worker -l info`