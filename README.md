# Samvera Repository Services for Linked Geo. Metadata
Environment for Fedora Commons, Apache Solr, and GraphDB using Docker

## Docker Compose

### Deploy the stack
```
docker-compose up
```

## Taking down the stack
```
docker-compose down
```

## Docker Swarm

### Initialize Docker Swarm
```
docker swarm init
```

### Deploy the stack
```
docker stack deploy -c docker-compose.yml linkedgeometadata
```

### View the services
```
docker stack services linkedgeometadata
```

*How do I find the IP addresses for the node on my Swarm?*
```
% docker node ls
ID                            HOSTNAME        STATUS              AVAILABILITY        MANAGER STATUS
ujo56gr97w21j073pg3vdz433 *   docker-desktop      Ready               Active              Leader              19.03.2
```

```
% docker node inspect --format '{{.Status.Addr}}' docker-desktop
```
_Please see https://success.docker.com/article/how-can-i-find-node-ips for more information._

*The environment is now ready for usage by Samvera applications (developed using
Hyrax or Valkyrie, for example).*

## Taking down the stack
```
docker stack rm linkedgeometadata
```

## Taking down the Swarm
```
docker swarm leave --force
```
