# rules_k8s

## Running rules_k8s with Docker Desktop

This assumes the following:

- Bazel is building a container that will run in the cluster, named `bazel:my_container`
- You already have Docker Desktop installed and running the Kubernetes environment

1. Run the Docker registry.

```bash
docker run -d -p 5000:5000 --restart=always --name registry registry:2
```

2. Set up a `k8s_object` to deploy your container

```bazel
k8s_object(
    name = "dev_deployment",
    cluster = "docker-desktop",
    images = {
        "localhost:5000/bazel:my_container": ":my_container",
    },
    kind = "deployment",
    template = ":deployment.yaml",
)
```

3. In `deployment.yaml`, reference the container

```yaml
image: localhost:5000/bazel:geo.codes_container
```

4. Optional: Make a rollup `k8s_objects`

```bazel
k8s_objects(
    name = "dev",
    objects = [
        ":dev_deployment",
        ":dev_service",
    ],
)
```

5. Build the container and deploy to your local Kubernetes

```bash
bazel run :dev.apply
```

Rerunning this command will update the container.

6. Stop the container

```bash
bazel run :dev.delete
```

7. Optional: cleanup

```bash
docker ps
docker stop 2d0cbd19bbbd # Image from registry:2
docker system prune -a # Aggressive removal of now-unused dev images. Be careful
```

## Cleaning up the `kube-system` namespace

I ran fluentd collectors in a DaemonSet. I can't find a way to get it to un-apply the changes
that I make to containers outside of the specific namespace I set up for logging, so I have
manual delete steps for those particular collectors.
