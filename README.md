# Samvera GeoLinkedData
## Docker Environment

Deploying the stack locally:
```
docker swarm init
docker stack deploy -c docker-compose.yml geolinkeddata
```

Deactivating the stack locally:
```
docker stack rm geolinkeddata
docker swarm leave --force
```
