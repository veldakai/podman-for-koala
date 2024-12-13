# Simple date using shell script
Container that returns current date using custom shell script instead of running `date` command.

RUN CONTAINER BUT DON'T DELETE
COPY SCRIPT TO CONTAINER
RUN COMMAND TO START THE SCRIPT
DELETE 

```bash
podman run --rm alpine:latest /bin/sh -c "date"
```
## How It Works:
1. `podman ` wregwg