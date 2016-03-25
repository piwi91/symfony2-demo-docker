Symfony Demo Application - Dockerized
=====================================

## Requirements

* Docker
* Docker Compose

## Usage

Clone this repository to your local machine and build the docker containers.

`docker-compose build`

Boot them up!

`docker-compose up -d`

Install composer dependencies

`docker-compose run application composer install`

Add `symfony3.dev` to you hosts file pointing to the docker container. If you run boot2docker, find out the ip by running `docker-machine ip`.

Go to `http://symfony3.dev:8080/app_dev.php` :-)