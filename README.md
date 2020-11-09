# Dockerizing Django with Postgres, Gunicorn, and Nginx
## Instruction for Docker Deployment 

## Installation

Requirements:
- Docker Latest

Follow these steps:
- Make a file name `.env.docker` add for postgres
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
