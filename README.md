# Instruction for Docker Deployment 

## Installation

Requirements:

- Default requirements mentioned above.
- Docker Latest
- PostgreSQL Latest

Follow these steps:
- Install `virtualenv` with `pip install virtualenv`
- Create an env in this folder called `ENV` (naming is important) `virtualenv ./env`
- Make a file name `.env.docker` add add
```sh
POSTGRES_USER=postgres
POSTGRES_PASSWORD=giveapassword
POSTGRES_DB=postgres
```

## Up and Run

 - Docker Build
```sh
docker-compose up -d --build
```
- Lets Browse [http://0.0.0.0:8080](http://0.0.0.0:8080)
- Migration
```sh
docker-compose exec server python manage.py migrate --noinput
```
- Collect Statics 
```sh
docker-compose exec server python manage.py collectstatic --no-input --clear
```
- Check Logs
```sh
docker-compose logs -f
``` 
- Container down
```sh
docker-compose down
```
