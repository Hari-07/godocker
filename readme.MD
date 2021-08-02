# Simple container from scratch in Go
To run a single commad inside the container
```bash
go run main.go run <command>
```

To open terminal inside container
```bash
go run main.go run /bin/bash
```

_This container does not support images, so we must manually create an ubuntu file system for usage by the container, and set is as root_

## Steps to create an empty filesystem using Docker

```bash
docker run -d --rm --name ubuntufs ubuntu sleep 1000
docker export ubuntufs -o ubuntufs.tar
docker stop ubuntufs
tar xf ubuntufs.tar -C <location of container root>
```