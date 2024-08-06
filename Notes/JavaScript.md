A dynamically typed programming language used predominantly for web development.

## Core Concepts

- **DOM Manipulation:** Interacting with the [[Document Object Model (DOM)]] to dynamically modify HTML elements, attributes, and styles using JavaScript methods like `getElementById`, `querySelector`, `appendChild`, etc.

- **Event Handling:** Capturing and responding to user interactions (e.g., clicks, mouse movements, keypresses) by attaching event listeners to DOM elements using methods like `addEventListener`.

- **[[Asynchronous Programming]]**: Using asynchronous techniques like callbacks, [[JavaScript Promises]], or async/await to manage non-blocking operations such as fetching data from servers (AJAX), performing animations, or handling user input.

- **Cross-Browser Compatibility:** Writing JavaScript code that works consistently across different web browsers by considering variations in JavaScript implementations, DOM APIs, and CSS rendering engines.

## Going Deeper - JavaScript Language Tools

### 1. Dynamic Typing

JavaScript is dynamically typed, types are determined at runtime:

```js
let message = "Hello, world!";  // message is a string
message = 42;                   // now message is a number
```

### 2. First-Class Functions

Functions in JavaScript are first-class citizens, which means they can be treated like any other value. You can assign them to variables, pass them as arguments to other functions, and even return them from functions:

```js
function greet(name) {
    return `Hello, ${name}!`;
}

const sayHello = greet;
console.log(sayHello("Alice"));  // Output: Hello, Alice!
```

### 3. Event-Driven

```js
document.getElementById('myButton').addEventListener('click', () => {
    alert('Button clicked!');
});
```

### 4. Asynchronous

See [[JavaScript Promises]].

### 5. Prototype-based [[Inheritance]]

Objects can inherit properties and methods from other objects via prototypes:

```js
const person = {
    greet() {
        console.log('Hello!');
    }
};

const friend = Object.create(person);
friend.greet();  // Output: Hello!
```

### 6. Closures

[[Functions]] that allow for access to variables outside their scope even after that scope has finished executing.

```js
function makeCounter() {
    let count = 0;
    return function() {
        count += 1;
        return count;
    };
}

const counter = makeCounter();
console.log(counter());  // Output: 1
console.log(counter());  // Output: 2
```

## ES6 JavaScript

Modern JavaScript, starting from ECMAScript 6 (ES6), introduced  new features:

- **Arrow Functions**: Shorter syntax for function expressions
- **Template Literals**: Enhanced string literals with embedded expressions
- **Destructuring**: Easy extraction of values from arrays and objects
- **Modules**: Support for modular code with `import` and `export`

```js
// Arrow Function
const add = (a, b) => a + b;

// Template Literal
const name = "World";
console.log(`Hello, ${name}!`);

// Destructuring
const [x, y] = [10, 20];
const {firstName, lastName} = {firstName: "John", lastName: "Doe"};
```


See also:
- [[Web Programming]]