# Run MapReader on Isambard-AI

This document helps you to run triton on [Isambard-AI](https://docs.isambard.ac.uk/specs/#system-specifications-isambard-ai-phase-1).

## Prep

1. Get familar with [Podman-HPC at Isambard](https://docs.isambard.ac.uk/user-documentation/guides/containers/podman-hpc/).

2. Get this branch

```bash
git clone https://github.com/owhere/triton.git
git checkout isambard
cd triton/container
```
## Build and Run the image

### Build the image

```bash
podman-hpc build -t triton .
```

### Run in an interactive shell
```bash
podman-hpc run -it --gpu --rm --name triton \
  localhost/triton:latest /bin/bash
```

## Pulll the image

If you have issues to build the image, please pull it from the [docker hub](https://hub.docker.com/repository/docker/oxfordfun/triton/tags)

```bash
podman-hpc pull oxfordfun/triton:105ed39
```
