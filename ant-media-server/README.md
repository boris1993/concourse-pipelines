# Ant Media Server Community Edition

An non-official Docker image for Ant Media Server Community Edition.

The image is built on my self hosted Concourse instance. You can checkout the build pipeline [here](https://github.com/boris1993/concourse-pipelines/ant-media-server/pipeline.yaml).

## Usage

- Docker command

```bash
$ docker volume create ant-media-server
$ docker run \
  --name ant-media-server \
  -d \
  -v ant-media-server:/usr/local/antmedia/ \
  --net=host \
  boris1993/ant-media-server:latest
```

- Docker compose

```yaml
version: '3'

services:
  ant-media-server:
    image: boris1993/ant-media-server:latest
    restart: always
    container_name: ant-media-server
    network_mode: host
    volumes:
      - ant-media-server:/usr/local/antmedia/

volumes:
  ant-media-server:
```
