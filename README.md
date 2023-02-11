# code-server-deploy

Based on https://github.com/coder/deploy-code-server/tree/main/deploy-container

```
docker run -p 127.0.0.1:8080:8080 \
  -v "$PWD/project:/home/coder/project" \
  -u "$(id -u):$(id -g)" \
  -e "DOCKER_USER=$USER" \
  -e "PASSWORD=12345" \
  -it bencdr/code-server-deploy-container:latest
```

## docker-compose
- docker-compose.yml

Start:
```
docker compose up
```

Stop and clean-up:
```
docker compose down --rmi 'all' --volumes
```

## Kubernetes
- code-server-claim0-persistentvolumeclaim.yaml
- code-server-deployment.yaml
- code-server-service.yaml

Start:
```
kubectl apply -f .
```

Stop and clean-up:
```
kubectl delete -f .
```
