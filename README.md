ctfd
---

Configure and run CTFd as Docker container into systemd.service.


### Links:
- <https://ctfd.io>
- <https://github.com/CTFd/CTFd>
- <https://hub.docker.com/r/ctfd/ctfd>
- <https://github.com/CTFd/CTFd/blob/master/CTFd/config.ini>


### Variables:
- **`ctfd_docker_image`** *(type=string, default="ctfd/ctfd:latest")* - Docker image for using into systemd.service.

- **`ctfd_docker_network`** *(type=string, default="bridge")* - Docker network used as `docker run --network=...`.
- **`ctfd_docker_publish_ports`** *(type=list, default=[])* - List of publish a container’s ports to the host as `docker run --publish=...`.

- **`ctfd_docker_envs`** *(type=list, default=[])* - List of objects in format `{KEY: value}` for set in container as environment variables.
- **`ctfd_docker_labels`** *(type=list, default=[])* - List of objects in format `{key: value}` for set in container as meta data labels.

- **`ctfd_secret_key`** *(type=string, mandatory)* - The secret value used to creation sessions and sign strings.

- **`ctfd_gunicorn_workers`** *(type=number, default=2)* - The number of worker processes. This number should generally be between 2-4 workers per core in the server.
- **`ctfd_gunicorn_bind_addr`** *(type=string, default=":8000")* - Specify a server socket to bind. Server sockets can be any of `$(HOST)`, `$(HOST):$(PORT)`, `:$(PORT)`, `fd://$(FD)` or `unix:$(PATH)`.
- **`ctfd_gunicorn_log_level`** *(type=string, default="error")* - The granularity of Error log outputs. Valid level names are: `debug`, `info`, `warning`, `error`, `critical`.
