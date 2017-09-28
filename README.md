# Blog Party USA

This project will provide an introduction to Express and server-side rendering using the JS templating engine Pug. We'll use [Node], [Express], and [MongoDB] to build an application that allows users to view and create blog posts.

[Node]: https://nodejs.org/en/about/
[Express]: http://expressjs.com/
[MongoDB]: https://www.mongodb.com/what-is-mongodb

## Getting Started

npm install express as a dependency and nodemon as a devDependency.

### [Dependency vs. DevDependency]: https://stackoverflow.com/a/22004559/4462871 :confused:

## Hello Express

Make an `app.js` file and require `express` at the top. Express will export as default a function which takes no arguments and returns our app object where we will define various properties.

### [app.get]: http://expressjs.com/en/4x/api.html#app.get.method

We can route HTTP verbs in our app using the following structure:

```javascript

app.HTTPVerb("Path/being/visited", function middlewareCB (requestObject, responseObject) {})

```

The second argument, represented as `middlewareCB`, is very flexible but we'll start simple. The [response] object provides many useful methods. To start, pass a string to its [end] method. We've now completed a very basic web application that will respond with that string whenever we visit the path provided as the first argument.

We need to tell this application on which port it should [listen] for incoming requests. I chose 3000.

Putting it all together...

```javascript

const express = require('express')
const app = express()

app.get('/', (req, res) => res.end('hey what is good?'))

app.listen(3000, () => console.log('i am listening on port 3000'))

```

Let's update our package.json's `scripts` property to have a key of `start` pointing to `nodemon app.js`. This will allow us to use `npm start` to run our application with `nodemon`, which prevents the need to restart the server every time we make changes.

`npm start` and visit `localhost:3000` in your browser. Cool!

[response]: http://expressjs.com/en/4x/api.html#res
[end]: http://expressjs.com/en/4x/api.html#res.end
[listen]: http://expressjs.com/en/4x/api.html#app.listen



