A REST API (also known as RESTful API) is an application programming interface (API or web API) that conforms to the constraints of REST architectural style and allows for interaction with RESTful web services.

## What the fuck is REST?

It's a set of architectural constraints. They can be implemented in many ways.

In order for an API to be considered RESTful, it has to conform to these criteria:
	-   A client-server architecture made up of clients, servers, and resources, with requests managed through [[HTTP]] actions.
	-   [Stateless](https://www.redhat.com/en/topics/cloud-native-apps/stateful-vs-stateless) client-server communication, meaning no client information is stored between get requests and each request is separate and unconnected.
	-   Cacheable data that streamlines client-server interactions.
	-   A uniform interface between components so that information is transferred in a standard form. This requires that:
    -   resources requested are identifiable and separate from the representations sent to the client.
    -   resources can be manipulated by the client via the representation they receive because the representation contains enough information to do so.
    -   self-descriptive messages returned to the client have enough information to describe how the client should process it.
    -   hypertext/hypermedia is available, meaning that after accessing a resource the client should be able to use hyperlinks to find all other currently available actions they can take.
	-   A layered system that organizes each type of server (those responsible for security, load-balancing, etc.) involved the retrieval of requested information into hierarchies, invisible to the client.
	-   Code-on-demand (optional): the ability to send executable code from the server to the client when requested, extending client functionality.

### How do we implement this?
Many ways son.

1. [[Monolithic]]
2. Service Oriented Architecture
3. [[Microservices]]

## When designing a full-stack application how do we monitor that shit?

- Infrastructure monitoriing:
	- Servers, Docker, Kubernetes, Application
- Metrics
	- CPU, Network, etc.
- Logs
	- Multiple sources and formats

See also:
- [[Computer Science Fundamentals]]
- [[Continuous Integration and Deployment]]
- [[Interface Architecture]]