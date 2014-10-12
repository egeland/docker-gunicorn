docker-gunicorn-python3-flask
---------------

Docker gunicorn server image source. This is based on `ubuntu:trusty` image.
The parent of this Docker file and associated files was `devoto13/gunicorn` - https://github.com/devoto13/docker-gunicorn.git

This version installs the python3 version of gunicorn, as well as:

* flask
* SQLAlchemy
* Flask-SQLAlchemy 
* the postgresql driver (psychopg2)
* coverage
* nose
* Mako
* Flask-Script
* Flask-Migrate
* Flask-HTTPAuth

Image
-----

Build this repository:

```
$ git clone https://github.com/egeland/docker-gunicorn.git
$ cd docker-gunicorn/
$ docker build -t YOURUSERNAME/gunicorn .
```

Change `YOURUSERNAME` to your Docker index username. :)

Container
---------

This image uses volumes and environment variables to control the gunicorn server
configuration.

Volumes:

* `/root/app/logs`: Logs from the container using it.

You pass with `-v` docker option. Don't forget to use absolute path here.

Environment variable:

* `APP_WSGI`: WSGI application to run.
* `APP_NAME`: Application label.
* `APP_WORKERS`: Number of workers to run.

You pass with `-e` docker option.

Usage
-----

Image intended to be used as base image for another `Dockerfile`. Take a look at the `example/` directory.
