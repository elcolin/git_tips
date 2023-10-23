# Docker
## Launch Docker
On **Linux**

    sudo systemctl start docker
## Build Image
**TODO**
## Remove Image
**TODO**
## Launch Container
**TODO**
## Stop Container
**TODO**
# docker-compose
Build image + launch

    docker-compose -f docker-compose.yml up -d --build
## Frequent errors

### Pulling image

    => ERROR [angular internal] load metadata for docker.io/library/node:16                                                                                 0.4s
    ------
     > [angular internal] load metadata for docker.io/library/node:16:
    ------
    failed to solve: node:16: error getting credentials - err: exit status 1, out: ``
    make: *** [reload] Error 17

 ### Solution
 
     rm  ~/.docker/config.json
