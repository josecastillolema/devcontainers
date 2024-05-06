# devcontainers

Collection of [Development Containers] for Fedora (Atomic) and rootless podman.

## Pre-requisites

 - Flatpak [com.visualstudio.code.tool.podman](https://github.com/flathub/com.visualstudio.code.tool.podman)
 - In VSCode `settings.json`:
    ```
    {
      "dev.containers.mountWaylandSocket": false,
      "remote.containers.dockerPath": "podman-remote"
    }
    ```
 - In `~.config/containers/containers.conf`:
    ```
    [containers]
    env = [
      "BUILDAH_FORMAT=docker"
    ]
    label = false
    userns = "keep-id"
    ```