## Master Node Components
- Kube-apiserver: Rest interface for the control plane and datastore, authenticates/authorises
- Cluster store: Currently [[Kubernetes]] uses [[etcd]] to store cluster data
- Controller manager: Launch/Control independent control loops for nodes, endpoints, replicasets, etc.
- kube-scheduler: Selects a node for newly created pods to run on based on availability and suitability
- API Server RESTful endpoint at port 443

### Sub-node Components
- Kubelet: Node-level manager, receives new pod assignments from the apiserver, manages node lifecycle
- Container runtime: Performs container-related tasks, uses a plugin model called the Container Runtime Interface (CRI)
- Kube-proxy: Manages local cluster networking and ensures each node gets an IP and is adequately routed/load balanced

### Control Loop of Each Node
1. Observe current state
2. Determine differences
3. Reconcile differences
4. Obtain desired state
5. Repeat