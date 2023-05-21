
A runtime environment for [[JavaScript]] code, working on a single thread using non-blocking IO calls.

## The Event Loop

With Node, each [[Threads]] handles multiple requests via something called the event loop, adding them to an event queue. The event loop iterates over the queue (now a list of events and node callbacks of completed operations) before executing. 

## Use Cases

- Real-time applications
- Anything fast and scalable

You wouldn't really use it for simple shit, or for CPU-heavy jobs (it only uses a single CPU core, heavier operations would block incoing requests, rendering the biggest advantage of node useless).

## The Holy NPM (Node Package Manager)

Installs node programs and modules, all goes into a node_modules folder in your project and is autoconfigured by a package.json file.

Syntax e.g. ```npm install express```

### The package.json file is your saviour

Defines everything, from main file name, to dependencies, to start scripts.