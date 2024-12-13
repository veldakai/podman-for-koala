# Podman for Koala
Notes from learning applicaiton containerization.

## Containers
Containers in Linux provide a **lightweight form of virtualization that isolates applications and their dependencies** from the host system and other containers.  **Containerized applications behave as if they are running on their own dedicated system**. 

This isolation is achieved through [namespaces](https://en.wikipedia.org/wiki/Linux_namespaces) (e.g., PID, network, and file system) to separate resources, and [cgroups](https://en.wikipedia.org/wiki/Cgroups) to limit resource usage like CPU, memory, and disk.

## Runtime engines
Runtime engines are essential for running containerized application as they handle container creation and execution. They follow [OCI standards](https://opencontainers.org/) and manage container lifecycles, isolation, and resource allocation. Common container runtime engines: containerd, runc, crun, CRI-O.

Runtime engines are used by **container management tools** like [**Podman**](https://podman.io/), [Docker](https://www.docker.com/) or [Kubertnetes](https://kubernetes.io/), which provide higher level management interface to manage containers and develop container images.

## Container images

A **container image is a read-only**, reusable blueprint containing the application's code, runtime, libraries, and dependencies. **Images are composed of layers**, where each layer represents a filesystem delta, enabling efficient storage and updates.

**When you run a container, runtime engine creates a container instance, which is a writable layer added on top of the image**. This reusability of images and layers reduces duplication and allows rapid scaling of containerized applications.


## Development environment
Since MacOS and Windows aren't Linux, we need to have Linux virtual machine to develop containers. Setting up local VM and interfacing with it is abstracted by development tools like Podman Desktop or Docker Desktop.

Install Podman Desktop using [official documentation](https://podman.io/docs/installation).


### MacOS installation
```bash
# install desktop for GUI
brew install podman-desktop
# install command line tools
brew install podman

# start Linux VM and verify installation or do so in PodmanDesktop
podman machine init
podman machine start
podman info
```

When you done working, stop the VM machine either by quitting Desktop or
```bash
podman machine stop
```


## Solutions
- [Get current date](solutions/01-simpe-date/README.md)
