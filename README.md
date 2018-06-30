# ddclient
My setup for `spdyn.de` using docker-compose

Running on `dirac`
Using image from [linuxserver/docker-ddclient](https://github.com/linuxserver/docker-ddclient)

## Setup
create `congig/ddclient.con`, from one of the samples in `config/`

## Run
```
docker-compose up -d
docker-compose logs -f ddclient
```

Check to see if running:
```
docker exec -it im-ddclient_ddclient_1 bash

root@6828e8d2a7d7:/$ ps auxww
PID   USER     TIME   COMMAND
    1 root       0:00 s6-svscan -t0 /var/run/s6/services
   33 root       0:00 s6-supervise s6-fdholderd
  213 root       0:00 s6-supervise inotify_modify
  214 root       0:00 s6-supervise ddclient
  217 root       0:00 bash ./run
  218 abc        0:00 ddclient - sleeping for 160 seconds
  224 root       0:00 inotifywait -e modify /config/ddclient.conf
  237 root       0:00 bash
  247 root       0:00 ps auxww

```

# alternative
```
docker run -it --rm  --name=ddclient -v $(pwd)/config:/config linuxserver/ddclient
```