An architectural pattern modelled on business concepts, small and fully autonomous with a distributed nature.

Generally comprises multiple services that feed into a gateway then to the user or programmer.

## Important Aspects

### [[Service Mesh]]

### API Gateway
- A server that acts as the single entry point into a microservices system
- Encapsulates the internal system architecture and provides an API to query that is tailored to each client

### Service Registry
- Database that contains the network location of service instances
- E.g. [[etcd]]

#### The Issue of Finding Service Locations: Service Discovery
- API Gateway required to know the network location of service instances, but each microservice application is assigned a dynamic IP

##### Client-side Discovery
- Client queries a service registry then uses a load-balancing algorithm to select one of the available instances and makes a request
- Straightforward and load intelligent but couples the client to the service registry

##### Server-side Discovery
- Client makes a request to a service via a load balancer
- Load balancer queries the service registry and routes each request to an available service instance
- Good because it abstracts the discovery away from the client but it does require a load balancer

#### Resilience

#### Deployment Strategies

#### Rolling Updates
- Ramped - slow rollout: Number of instances of old version is decreased and new is increased until correct number of instances is reached
- Blue/Green: Green version is deployed alongside Blue version, after testing update the load balancer to send traffic to the new version
- Canary: Routing a subset of users to a new functionality
- A/B: Distributing traffic amongst versions based on a few parameters


See also:
- [[Cloud Computing]]






