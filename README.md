# Docker - Elasticsearch Logstash Kibana

## hosts

add line.

```
127.0.0.1 elasticsearch
```

## docker version

```
Client:
 Version:	17.12.0-ce
 API version:	1.35
 Go version:	go1.9.2
 Git commit:	c97c6d6
 Built:	Wed Dec 27 20:03:51 2017
 OS/Arch:	darwin/amd64

Server:
 Engine:
  Version:	17.12.0-ce
  API version:	1.35 (minimum version 1.12)
  Go version:	go1.9.2
  Git commit:	c97c6d6
  Built:	Wed Dec 27 20:12:29 2017
  OS/Arch:	linux/amd64
  Experimental:	true
```
## build

```
docker-compose build
```

## up

```
docker-compose up
```

## Create kibana index pattern

```
curl -XPOST -D- 'http://localhost:5601/api/saved_objects/index-pattern' \
    -H 'Content-Type: application/json' \
    -H 'kbn-version: 6.2.2' \
    -d '{"attributes":{"title":"logstash-*","timeFieldName":"@timestamp"}}'
```
## bulk insert log

```
 nc localhost 5000 < /path/to/logfile.log
```

## Kibana
```
http://localhost:5601/
```

