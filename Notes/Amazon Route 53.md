Scalable [[Domain Name System (DNS)]] web service, used to route end users to internet applications by translating names (google.com) into [[IP Address]]es.

## Supported Routing

- Simple: Used in single-server environments
- Weighted round-robin: Assign weights to resource record sets to specify frequency
- Latency: Help improve global applications
- Geolocation: Route traffic based on location of users
- Geoproximity: Route traffic based on location of resources
- Failover: Fail over to a backup site if your primary site becomes unreachable
- Multivalue answer: Responds to DNS queries with up to eight healthy records selected at random