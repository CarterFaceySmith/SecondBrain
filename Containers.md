Light-weight [[Virtual Machines]], they share the same underlying OS kernel and can therefore only run flavours of the same OS.

## Namespaces and cgroups

Namespaces are used to limit the views, taken to mean the resources available, they stand for control groups.

A [[Kernel]] feature that limits the application to a specific set of resources, partitions a set of tasks.

### How do containers come into this?

[[Docker]] uses the containers to port across environments, reducing code writting time and production time by removing unnecessary configuration hurdles.

[[Docker]] caches the layers the first time building them, e.g. Golang, Apache, then only builds all layers the first deployment, there's no point reinstalling the base environment (Ubuntu, Golang, etc).