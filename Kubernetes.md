Welcome to the wonderful world of [[Containers]] orchestration.

Let's say, hypothetically, you have a tonne of [[Docker]] containers to deploy and manage, would you do this manually? Hell nah, sounds like a massive pain.

Enter *Kubernetes* (unless you wanna use shit like Azure Container Service, Amazon ECS, Docker Swarm etc., you got options bro).

So more or less, Kubernetes and services like it are two things, a cluster for running applications, and an orchestrator of cloud-native microservice apps. 

Generally applications are managed declaratively via a YAML file config.

Based on host-level [[Virtualisation]].

## The Two Parts

### Cluster
A bunch of [[Node]]s, and a control plane which provides API, scheduler and persistent storage for the cluster.

### Orchestrator
The services to run and coordinate microservice applications in the following general pattern:
1. Write microservice
2. Package each service in a [[Containers]]
3. Wrap each container in its own [[Pod]]
4. Deploy [[Pod]] to the cluster via resource manager

## Services Provided
- Container placement: Manages selection of container(s) host
- Resource monitoring at all levels
- Container health checks
- Container scaling based on requirements
- Networking of containers: Efficient microservice communication
- Persistent storage management

## [[Cloud Native Applications]]

## Cluster Scaling

### Cluster Autoscaler
Adapts the number of nodes of the Kubernetes cluster and runs on the master node.

Scaling implemented through the cloud provider interface.

Includes a scaling policy to govern how it is done.


