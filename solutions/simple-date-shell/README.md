# Simple date using shell
A "Hello World" example that returns current date using shell command `date`. It demonstrates how to run a shell command as isolated app inside a container. 

```sh
podman run alpine:latest date
```

Running the command multiple times will create a new container every time - new writable layer for each instance. It might require some cleanup:

```sh
# List all existing containers
podman container list -a
# Remove unwanted container
podman container rm [container-name-or-id]
```

## Recommended minimal command

Give your containers meaningful name, remove containers for one-time jobs, ask shell to launch complex commands.

```sh
podman run --rm --name [service.component] [image:label] [command] -c "[command-arguments]"
```

Example:
```sh
podman run --rm --name example.simple-date-shell alpine:latest /bin/sh -c "date"
```

## How it works
1. `podman run [image] [command]` creates a new container and [runs the command inside the container](https://docs.podman.io/en/latest/markdown/podman-run.1.html). If image is not available locally, it will fetch it from docker registry.
1. `-rm` removes the container after execution
1. `--name [container-name]` gives container a meangingfull name instead of random name. Introducing hiearchy is adviced to group containers virtualy together.
1. `alpine:latest` is the name of the image, in this case small lightweight base image, only 5MB in size. Among others it contains `sh` and `date` command and everything needed to execute them.
1. `/bin/sh -c "date"` a command to run inside the container and command arguments. We just ask shell to execute `date` command
