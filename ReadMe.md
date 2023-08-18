#build
docker compose -f local.yml up --build -d --remove-orphans

#check all logs services
docker compose -f local.yml logs

#check specified logs service
docker compose -f local.yml logs api

#check specified volume
docker volume inspect src_local_postgres_data

#if there ar update
docker compose -f local.yml down

#Purging all unused or dangling images, container, volumes, and networks
docker system prune -a
docker volume prune -a

#get lists container
docker ps -a -q

#backup db
docker compose -f local.yml exec postgres backup
docker compose -f local.yml exec postgres backups
docker compose -f local.yml exec postgres restore filename