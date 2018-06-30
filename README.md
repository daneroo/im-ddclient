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

# alternative
```
docker run -it --rm  --name=ddclient -v $(pwd)/config:/config linuxserver/ddclient
```