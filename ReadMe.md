#build
docker compose -f local.yml up --build -d --remove-orphans

#check all logs services
docker compose -f local.yml logs

#check specified logs service
docker compose -f local.yml logs api

#check specified volume
docker volume inspect src_local_postgres_data