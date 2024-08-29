A [[Backend]] [[JavaScript]] [[Web Programming]] framework for [[Node.js]].

Commonly used as middleware or an API, for routing of client requests to a particular endpoint URI (path) and a specific [[HTTP]] request method (GET, PUT, POST, DELETE).

## Setup and Rendering

Initialise and run Express (Definitely want to install and run nodemon too):

server.js
```js
const express = require("express")
const app = express()

app.use(express.static("public")) // takes folder name to serve file from
app.use(express.urlencoded({ extended: true }))
app.use(express.json())

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

## Express Middleware In-depth

```js
app.use(logger)

function logger(req, res, next) {
  console.log(req.originalUrl)
  next()
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
[Learn Express Js in 35 Minutes - Web Dev Simplified](https://www.youtube.com/watch?v=SccSCuHhOw0)