# Docker PHP

This project uses a sample app name `myapp` and user name `toto`

## Usage

First, build app:

```
$ docker-compose build app
```

Then, run app:

```
$ docker-compose up -d
```

## Composer

Install dependencies:

```
$ docker-compose exec app rm -rf vendor composer.lock
$ docker-compose exec app composer install
```

## Commands

To launch a bash command on Docker:

```
$ docker-compose exec app php -v
```

### Old Composer version

Replace `latest` for `2.2` in `COPY --from=composer:latest /usr/bin/composer /usr/bin/composer` in `Dockerfile`

## PHP

### Old PHP versions

Replace `8.2` for `7.1` in `FROM php:8.2-fpm` in `Dockerfile`

## MySQL

Don't forget to add a `.env` file in your project based on `.env.example` file of this repository.

### Old MySQL version

Replace `image: mysql:8.0` for `5.7` in `docker-composer.yml`

If using an Apple Mac M1/M2 chip, adds `platform: linux/x86_64`

## Resources

* https://www.digitalocean.com/community/tutorials/how-to-install-and-set-up-laravel-with-docker-compose-on-ubuntu-22-04
