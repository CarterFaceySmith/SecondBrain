A [[Backend]] [[JavaScript]] [[Web Programming]] framework for [[Node.js]].

Commonly used as middleware or an API, for routing of client requests to a particular endpoint URI (path) and a specific [[HTTP]] request method (GET, PUT, POST, DELETE).

## Setup and Rendering

Initialise and run Express (Definitely want to install and run `nodemon` too):

server.js
```js
const express = require("express")
const app = express()

app.use(express.static("public")) // takes folder name to serve file from
app.use(express.urlencoded({ extended: true })) 
app.use(express.json()) // Enables parsing of JSON data

app.set("view engine", "ejs")

const userRouter = require("./routes/users")

app.use("/users", userRouter)

app.listen(3000)
```

views/users/new.ejs
```ejs
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <form action="/users" method="POST">
    <label>First Name
      <input type="text" name="firstName" value="<%= locals.firstName %>" />
    </label>
    <button type="submit">Submit</button>
  </form>
</body>
</html>
```

## Routing

Create a routes folder and a .js file for any route you need, these can be imported to your main.js  via `const router = express.Router()`.

Remember routes are evaluated *in order of definition*, if you redefine a route somewhere below an existing one it won't work.

Routes can be fixed or dynamic, the difference being what arguments they do or do not take, for example a fixed route is one that takes no parameter and returns a list of users, a dynamic route is one that takes some ID and only returns the user that matches that.

routes/users.js
```js
const express = require("express")
const router = express.Router()

router.use(logger)

router.get("/", (req, res) => {
  console.log(req.query.name)
  res.send("User List")
})

router.get("/new", (req, res) => {
  res.render("users/new")
})

router.post("/", (req, res) => {
  const isValid = false
  if (isValid) {
    users.push({ firstName: req.body.firstName })
    res.redirect(`/users/${users.length - 1}`)
  } else {
    console.log("Error")
    res.render("users/new", { firstName: req.body.firstName })
  }
})

router
  .route("/:id") // Dynamic route example
  .get((req, res) => {
    console.log(req.user)
    res.send(`Get User With ID ${req.params.id}`)
    // WITHOUT router.param middleware func below you could do as follows
    // let user = users.find(u => u.id === parseInt(req.params.id))
    // if (!user) return res.status(404).send('No user found for ID ${req.params.id}')
  })
  .put((req, res) => {
    res.send(`Update User With ID ${req.params.id}`)
  })
  .delete((req, res) => {
    res.send(`Delete User With ID ${req.params.id}`)
  })

const users = [{ name: "Kyle" }, { name: "Sally" }]
router.param("id", (req, res, next, id) => {
// Saying whenever you go to a route with an id param, run this code
  req.user = users[id]
  next() // Runs the next thing in line after this function is called
})

function logger(req, res, next) {
  console.log(req.originalUrl)
  next()
}

module.exports = router
```

## Express Middleware

You can define middleware as functions to run between each function call of your core node application, below is an example that logs the URI of the last request and then continues the code via `next()`.

```js
app.use(logger)

function logger(req, res, next) {
  console.log(req.originalUrl)
  next()
}
```

## Input Validation with Joi

You can import the Joi module and use it within routes to validate POST parameter inputs or the like and increase security.

Example:
```js
const schema = Joi.object({
	name: Joi.string().min(3).required()
});

const res = Joi.validate(req.body, schema);
console.log(res);
```

Standard Validation Example:
```js
const { error } = validateCourse(req.body);
if (error) return res.status(400).send(error.details[0].message);

function validateCourse(course) {
	const schema = Joi.object({
		name: Joi.string().min(3).required()
	});

	const res = Joi.validate(req.body, schema);
}
```

## Integrating Express with [[GraphQL]]

```js
const express = require('express');
const { graphqlHTTP } = require('express-graphql');
const { buildSchema } = require('graphql');

// Define the GraphQL schema
const schema = buildSchema(`
  type Query {
    getUser(id: ID!): User
    listUsers: [User]
  }

  type Mutation {
    createUser(name: String!, age: Int!): User
    updateUser(id: ID!, name: String, age: Int): User
  }

  type User {
    id: ID!
    name: String!
    age: Int!
  }
`);

// Sample data
let users = [
  { id: '1', name: 'Alice', age: 25 },
  { id: '2', name: 'Bob', age: 30 },
];

// Define the root resolver
const root = {
  getUser: ({ id }) => {
    return users.find(user => user.id === id);
  },
  listUsers: () => {
    return users;
  },
  createUser: ({ name, age }) => {
    const newUser = { id: String(users.length + 1), name, age };
    users.push(newUser);
    return newUser;
  },
  updateUser: ({ id, name, age }) => {
    const user = users.find(user => user.id === id);
    if (user) {
      if (name) user.name = name;
      if (age !== undefined) user.age = age;
      return user;
    }
    throw new Error('User not found');
  }
};

// Create an Express application
const app = express();

// Set up the /graphql endpoint
app.use('/graphql', graphqlHTTP({
  schema: schema,
  rootValue: root,
  graphiql: true, // Enables the GraphiQL interface for testing queries
}));

// Start the server
app.listen(4000, () => {
  console.log('Server is running on http://localhost:4000/graphql');
});
```


See also:
- [Learn Express Js in 35 Minutes](https://www.youtube.com/watch?v=SccSCuHhOw0)
- [How to build a REST API with Node js & Express](https://www.youtube.com/watch?v=pKd0Rpw7O48)
- [Express JS Documentation](https://expressjs.com/en/guide/routing.html)
- [Nodemon NPM Page](https://www.npmjs.com/package/nodemon)
- [Node.js SQLite: Build a simple REST API with Express](https://geshan.com.np/blog/2021/10/nodejs-sqlite/)