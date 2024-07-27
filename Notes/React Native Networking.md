## Fetch

The `fetch` function is a top-level API to make [[HTTP]] requests. It is a promise-based API for handling [[Networking]] requests. It allows you to fetch resources (typically [[JSON]] data) from a provided URL.

### Fetch Example

```jsx
fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then((response) => response.json())
  .then((json) => console.log(json))
  .catch((error) => console.error(error));
```

### POST Request

To make a POST request using fetch, you need to provide an additional object with the `method`, `headers`, and `body` properties:

```jsx
fetch('https://jsonplaceholder.typicode.com/todos', {
  method: 'POST',
  headers: {
    'Accept': 'application/json',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    title: 'New Task',
    completed: false
  })
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));
```

## Axios

[[Axios]] is a popular and widely-used library for making HTTP requests in [[JavaScript]] applications. It’s promise-based and provides a simple-to-use API.

## [[Websockets]] in React Native

### Setting Up a WebSocket Connection

In React Native, you can use the `WebSocket` API to establish a WebSocket connection with the server. 

```js
const webSocket = new WebSocket('ws://my-websocket-server.com');
```

### Receiving and Sending Messages

You can handle the different events associated with a WebSocket connection by attaching event listeners to the `WebSocket` instance.

#### Handling Connection

```js
webSocket.onopen = (event) => {
  console.log('WebSocket connection opened:', event);
};
```

#### Handling Incoming Messages

```js
webSocket.onmessage = (event) => {
  console.log('Received from server:', event.data);
};
```

#### Sending Messages to the Server

```js
webSocket.send('Hello server');
```

#### Handling Connection Error and Closure

```js
webSocket.onerror = (event) => {
  console.log('WebSocket error:', event);
};

webSocket.onclose = (event) => {
  console.log('WebSocket connection closed:', event);
};
```

### Closing the WebSocket Connection

```js
webSocket.close();
```
