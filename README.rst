QUDA PROJECT / DOCKER EDITION
=======================

.. image:: https://travis-ci.org/pydanny/cookiecutter-django.svg?branch=master
    :target: https://travis-ci.org/pydanny/cookiecutter-django?branch=master
    :alt: Build Status

.. image:: https://img.shields.io/badge/cookiecutter-Join%20on%20Slack-green?style=flat&logo=slack
    :target: https://join.slack.com/t/cookie-cutter/shared_invite/enQtNzI0Mzg5NjE5Nzk5LTRlYWI2YTZhYmQ4YmU1Y2Q2NmE1ZjkwOGM0NDQyNTIwY2M4ZTgyNDVkNjMxMDdhZGI5ZGE5YmJjM2M3ODJlY2U

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
    :target: https://github.com/ambv/black
    :alt: Code style: black

Features
---------

* For Django 3.0
* For Vue-Clie 4.2
* Works with Python 3.8
* Renders Django projects with 100% starting test coverage
* 12-Factor_ based settings via django-environ_
* Secure by default. We believe in SSL.
* Optimized development and production settings
* Docker support using docker-compose_ for development and production (using Traefik_ with LetsEncrypt_ support)
* Customizable SQLite_, RedisDB_ & MongoDB_ version

Integrations
---------------------

*These features can be enabled during initial project setup.*

* Configuration for Celery_ and Flower_ (the latter in Docker setup only)
* Integration with Sentry_ for error logging

.. _django-environ: https://github.com/joke2k/django-environ
.. _12-Factor: http://12factor.net/
.. _Celery: http://www.celeryproject.org/
.. _Flower: https://github.com/mher/flower
.. _Sentry: https://sentry.io/welcome/
.. _docker-compose: https://github.com/docker/compose
.. _Traefik: https://traefik.io/
.. _SQLite: https://www.sqlite.org/
.. _RedisDB: https://redis.io/
.. _MongoDB: https://www.mongodb.com/es
.. _LetsEncrypt: https://letsencrypt.org/

Prerequisites
-------------

* NODE.JS; if you don't have it yet, follow the `installation node instructions`_;
* Docker; if you don't have it yet, follow the `installation instructions`_;

.. _`installation node instructions`: https://nodejs.org
.. _`installation instructions`: https://docs.docker.com/install/#supported-platforms
.. _`installation guide`: https://docs.docker.com/compose/install/


Build the Stack
---------------

This can take a while, especially the first time you run this particular command on your development system::

    $ docker-compose -f local.yml build

Generally, if you want to emulate production environment use ``production.yml`` instead. And this is true for any other actions you might need to perform: whenever a switch is required, just do it!

Execute Management Commands
---------------------------

As with any shell command that we wish to run in our container, this is done using the ``docker-compose -f local.yml run --rm`` command: ::

    $ docker-compose -f local.yml run --rm django python manage.py migrate
    $ docker-compose -f local.yml run --rm django python manage.py createsuperuser
    $ cd frontend
    $ npm i

Here, ``django`` is the target service we are executing the commands against.

Run the Stack
-------------

This brings up both Django and PostgreSQL. The first time it is run it might take a while to get started, but subsequent runs will occur quickly.

Open a terminal at the project root and run the following for local development::

    $ docker-compose -f local.yml up
    $ cd frontend
    $ npm run serve

Run on

    http://localhost:8000/graphql/

