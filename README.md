# docker-build-wrapper
Docker build wrapper for system upgrades

## Usage

Set build-arg ```DISTRO``` to the desired docker image (e.g. ```alpine:3```) when building to create a new image with latest system updates.

### docker-compose

To build an alpine based image:

```
version: "2.4"

myservice:
    image: egoaty/build-wrapper:alpine3
    build:
      context: https://github.com/egoaty/docker-build-wrapper.git
      dockerfile: Dockerfile-alpine
      args:
        DISTRO: alpine:3
    [...]
```

### docker CLI

To build an alpine based image:

```
docker build -t egoaty/build-wrapper:alpine3 --build-arg DISTRO=alpine:3 .
```

