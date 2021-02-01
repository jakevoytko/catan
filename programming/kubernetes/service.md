# Service
Two things: a backend, and a network policy defining how they get accessed.

## Backends

There are a few ways to access the backends. The only one I've used so far are selectors,
which allow you to explicitly pick which pods to use. This isn't the only way, though.

## IP addresses
You can manually specify IP addresses using the `clusterIP` field on the spec.

## Exposing the service
Services can be used to access pods. There are different types that have different behaviors.

- `LoadBalancer`: Expose the service externally. Automatically creates underlying `NodePort` and `ClusterIP` services. Per the documentation, this is built with cloud services in mind that offer load balancers of their own, but they offer an nginx-powered one also.

# Links
- [Official service documentation](https://kubernetes.io/docs/concepts/services-networking/service/)
- [Service API documentation](https://kubernetes.io/docs/reference/kubernetes-api/services-resources/service-v1/)