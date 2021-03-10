# Django Heroku Starter Template

An utterly fantastic project starter template for Django 3.1.

## Features

- Production-ready configuration for Static Files, Database Settings, Gunicorn, etc.
- Enhancements to Django's static file serving functionality via WhiteNoise.
- Latest Python 3.9 runtime environment.

## How to Use

To use this project, follow these steps:

1. Create your working environment.
2. Install Django (`$ pipenv install django`)
3. Create a new project using this template

## Creating Your Project

Using this template to create a new Django app is easy::

    $ django-admin.py startproject --template=https://github.com/mr-vaibh/django-heroku-template/archive/main.zip --name=Procfile djangoproject .

(If this doesn't work on windows, replace `django-admin.py` with `django-admin`)

You can replace ``djangoproject`` with your desired project name.

## For Static/Media files management
[https://docs.djangoproject.com/en/3.1/howto/static-files/](https://docs.djangoproject.com/en/3.1/howto/static-files/)

## For .ENV environment variable
https://help.pythonanywhere.com/pages/environment-variables-for-web-apps/

Write this before calling `get_wsgi_application` in _wsgi.py_

    import os
    from dotenv import load_dotenv
    project_folder = os.path.expanduser('~/my-project-dir')  # adjust as appropriate
    load_dotenv(os.path.join(project_folder, '.env'))

Usage in module

    import os
    SECRET_KEY = os.environ["SECRET_KEY"]

---

## Deployment to Heroku

    $ git init
    $ git add -A
    $ git commit -m "Initial commit"

    $ heroku create
    $ git push heroku master

    $ heroku run python manage.py migrate

See also, a [ready-made application](https://github.com/heroku/python-getting-started), ready to deploy.


## License: MIT

## Further Reading

- [Gunicorn](https://warehouse.python.org/project/gunicorn/)
- [WhiteNoise](https://warehouse.python.org/project/whitenoise/)
- [dj-database-url](https://warehouse.python.org/project/dj-database-url/)
