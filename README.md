# devcontainers

Collection of [Development Containers](https://containers.dev/) for Fedora (Atomic) and rootless podman.

## Pre-requisites

 - Flatpak [com.visualstudio.code.tool.podman](https://github.com/flathub/com.visualstudio.code.tool.podman) extension
 - The `podman.socket` service needs to be running at the user level:
    ```
    $ systemctl --user enable --now podman.socket
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
 - Allow VSCode to access `xdg-run/podman` in filesystem permissions:
    ```
    $ flatpak override --user --filesystem=xdg-run/podman:ro com.visualstudio.code
    ```
 - In VSCode `settings.json`:
    ```
    {
      "dev.containers.mountWaylandSocket": false,
      "remote.containers.dockerPath": "podman-remote"
    }
    ```
