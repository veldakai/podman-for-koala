# Simple date
A "Hello World" example that returns current date.

```bash
podman run --rm alpine:latest /bin/sh -c "date"
```
## How It Works:
1. `podman run [image] [command]` creates a new container and [runs the command inside the container](https://docs.podman.io/en/latest/markdown/podman-run.1.html). If image is not available locally, it will fetch it from docker registry.
1. `-rm` removes the container after execution
1. `alpine:latest` is the name of the image, in this case small lightweight base image.
1. `/bin/sh -c "date"` a command to run inside the container. We just ask shell to execute `date` command

