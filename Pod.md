A group of [[Containers]], it provides an environment with a unique IP, shared memory, volumes, etc. for the [[Containers]].

Containers inside the Pod can use ports on the Pod's localhost interface.

You can setup a network of Pods using [[Kubernetes]] so that they can reach each other via their IPs without Network Address Translation (whatever the fuck that is).

cgroups specify the resource limits of Pods, and normally the limits of a Pod are the aggregated limits of the containers plus possibly some Pod overhead.

## Pod Scaling

### Vertical Pod Autoscaler
Calculates the resource requests for Pods based on usage.

Includes:
- Deployment/StatefulSet
- Update Policy rules
- Resource Policy rules
- Recommendation based on historica and current resource usage

### Horizontal Pod Autoscaler
Modifies the desired number of replicas within declared bounds.

