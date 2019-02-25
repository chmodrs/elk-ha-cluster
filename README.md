# elk-swarm-cluster

Deploy ELK stack in Docker Swarm Cluster

1- Create an overlay network called elk

```
# docker network create --attachable -d overlay elk
```

2- Run stack

```
# docker stack deploy -c docker-compose.yml elk
```

