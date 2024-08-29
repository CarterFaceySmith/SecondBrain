
A runtime environment for [[JavaScript]] code, working on a single thread using non-blocking IO calls.

## The Event Loop

With Node, each [[Threads]] handles multiple requests via something called the event loop, adding them to an event queue. The event loop iterates over the queue (now a list of events and node callbacks of completed operations) before executing. 

## Use Cases

- Real-time applications
- Anything fast and scalable

You wouldn't really use it for simple shit, or for CPU-heavy jobs (it only uses a single CPU core, heavier operations would block incoming requests, rendering the biggest advantage of node useless).

## The Holy NPM (Node Package Manager)

Installs node programs and modules, all goes into a node_modules folder in your project and is autoconfigured by a package.json file.

Syntax e.g. ```npm install express```

### The package.json file is your saviour

Defines everything, from main file name, to dependencies, to start scripts.

## Important Elements of Node.js

### 1. Non-Blocking I/O

Node.js operates on a non-blocking, event-driven architecture. This means it can handle multiple operations concurrently without waiting for any one operation to complete before starting another.

### 2. Single Programming Language

Node.js uses JavaScript for both server-side and client-side programming, providing a unified language environment for developers.

### 3. Event-Driven Architecture

Node.js utilizes an event-driven model where operations are handled using events and callbacks, which is ideal for I/O-heavy applications.

### 4. npm (Node Package Manager)

npm is the default package manager for Node.js, enabling you to install and manage third-party libraries and tools. Express.js, along with many other libraries, is available through npm.

### 5. V8 Engine

Node.js uses the V8 JavaScript engine developed by Google, which compiles JavaScript directly to native machine code, providing high performance for JavaScript execution.

### 6. Asynchronous Programming

Node.js supports asynchronous programming using callbacks, promises, and async/await, making it suitable for handling tasks that take time, such as reading files or making network requests.