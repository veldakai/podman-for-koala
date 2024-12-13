# Podman for Koala
Podman experiments for learning


## Getting started
Install Podman using [official documentation](https://podman.io/docs/installation).

Note: Linux installation doesn't need virtual machine, containers run natively. Check specific instruction for [production deployment on Linux](https://podman.io/docs/installation#installing-on-linux).


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
