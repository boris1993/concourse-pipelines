# BOINC Client

A customized BOINC client Docker image.

Additional dependencies installed:

- libgomp1 - SiDock@Home

## Usage

- Docker command

```shell
$ docker volume create boinc
$ docker run \
  --name boinc \
  --net=host \
  --restart always \
  -d \
  -v boinc:/var/lib/boinc \
  -e BOINC_GUI_RPC_PASSWORD=A_V3rY_s3cRET_p@ssW0rD \
  -e BOINC_CMD_LINE_OPTIONS=--allow_remote_gui_rpc \
  -e BOINC_REMOTE_HOST=0.0.0.0 \
  boris1993/boinc:latest
```

- Docker compose

```yaml
version: '3'

services:
  boinc:
    image: boris1993/boinc:latest
    container_name: boinc
    restart: always
    network_mode: host
    pid: host
    environment:
      BOINC_GUI_RPC_PASSWORD: A_V3rY_s3cRET_p@ssW0rD
      BOINC_CMD_LINE_OPTIONS: --allow_remote_gui_rpc
      BOINC_REMOTE_HOST: 0.0.0.0
    volumes:
      - boinc:/var/lib/boinc

volumes:
    boinc:
```
