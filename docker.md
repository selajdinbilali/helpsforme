# Docker useful commands

## Build an image
The .dockerfile must be in the folder where you execute the command.
```
docker build -f toto.dockerfile . -t toto
```

## Run a container and sync the folder you are in (useful in webdev)
```
docker run -v `pwd`:/var/www --name=toto -d -p 8080:80 toto:latest
```

## Bash into your docker
The container must be already launched.
```
docker exec -ty toto bash
```


## Stop a container (before deleting it)
```
docker stop toto
```
```
docker rm toto
```

## Some cleaning (Dangerous)
### Delete every Docker containers
### Must be run first because images are attached to containers
```
docker rm -f $(docker ps -a -q)
```
# Delete every Docker image
```
docker rmi -f $(docker images -q)
```
