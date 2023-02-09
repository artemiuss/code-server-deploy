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


## Kubernetes
- code-server-claim0-persistentvolumeclaim.yaml
- code-server-deployment.yaml
- code-server-service.yaml