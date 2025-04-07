# jenkins-setup

docker compose -f docker-compose.yml-no-secure build | tee build-log-redhat-host-v1.0.0.log
docker compose -f docker-compose.yml-no-secure up -d
docker compose -f docker-compose.yml-no-secure down -v
