[![Build Status](https://drone.402.at/api/badges/402/satis-go-docker/status.svg)](https://drone.402.at/402/satis-go-docker)


## docker-compose usage

```yml
version: '3.8'

services:
  satis-go:
    container_name: satis-go
    image: nedaya/satis-go:latest
    volumes:
      - composer_data:/composer
      - satis_go_data:/opt/satis-go/data
    restart: always
    environment:
      - SATIS_GO_REPO_NAME="<name>"
    networks:
      - <network>
volumes:
  composer_data:
    driver: local
    driver_opts:
      type: nfs4
      o: addr=192.168.0.5,rw,nolock
      device: ":/home/pi/storage/DockerVolumes/402/composer"
  satis_go_data:
...
networks:
...
```