# `rules_docker`

## Providing custom configurations for containers

Use `container_pull` in the WORKSPACE to include the container that you'd like to use.
Configure a `container_image` using your desired file as base.

```bash
container_image (
  name = my_container_custom_config,
  base = "@public_repo//image",
  directory = "/usr/local/etc",
  files = ["my.conf"],
  entrypoint = "container_command -other -flags -and -probably --config=/usr/local/etc/my.conf",
)
```

Use `docker inspect` to look up the correct entrypoint / command, and make modifications to suit
your own personal needs.