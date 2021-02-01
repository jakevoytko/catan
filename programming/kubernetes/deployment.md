# Deployment
Deployments define the desired state for `Pod`s and `ReplicaSet`s. Changing the desired state
of a deployment causes the changes to be reflected in the underlying pods and replicas.

A simple deployment might specify a container, ports exposed by the containers, a specification of how
many replicas of that container should run, selector labels for that container, and a name for the deployment.

More advanced functionality, like canaries, rollouts, etc. can also be specified.

# Links
- [Deployment documentation](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#updating-a-deployment)
- [Deployment API documentation](https://kubernetes.io/docs/reference/kubernetes-api/workloads-resources/deployment-v1/)

