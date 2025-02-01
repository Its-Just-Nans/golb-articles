# Docker

## Options

- `-it`: interactive

```sh
docker run -it debian
```

- `-e`: environnement variable

```sh
docker run -e FOO=bar debian
```

- `-v`: volume

```sh
docker run -v $(pwd):/mnt debian
```

- `-d`: detached

```sh
docker run -d  debian
```

## Build

```sh
docker build -t my_debian .
# then
docker run my_debian
```

> `-t`: tag the image

## Known bug on MacOs Apple Silicon

You need to add `--platform linux/amd64` (for example) to use the amd64 because by default, it use the platform of the computer (`arm64`)

You need to add this option during `docker build` and `docker run` commands

## Run nginx on docker

It's useful to add

```dockerfile
CMD ["nginx", "-g", "'daemon off;'"]
```

to force nginx to run in foreground (and not in background)

## Clean stuff

```sh
docker system prune -a --volumes
```

## Links

- [https://www.i3s.unice.fr/~urvoy/docs/VICC/3_vicc.pdf](https://www.i3s.unice.fr/~urvoy/docs/VICC/3_vicc.pdf)
