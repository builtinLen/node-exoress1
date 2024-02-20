### Conceptual Exercise

Answer the following questions below:

- What are some ways of managing asynchronous code in JavaScript?

  async/await and .then are some ways of managing asynchronous code.

- What is a Promise?

A Promise represents the eventual completion or failure of an asynchronous operation and its resulting value. 

- What are the differences between an async function and a regular function?

An async function can contain await, which allows you to pause execution until a promise resolves or rejects. Regular functions do not have this capability.

- What is the difference between Node.js and Express.js?

Node.js is a server environment that allows developers to run JavaScript on servers, while Express.js is a web application framework for Node.js. It simplifies the process of building web applications.

- What is the error-first callback pattern?

A common pattern used by many developers when working with callbacks, especially those that involve errors, is to pass an additional argument as the first parameter of the callback function. 

- What is middleware?

A piece of software that processes requests sent to a server before a route handler, which defines how the server should respond to each request.

- What does the `next` function do? 

The next function moves on to the next applicable line or function. It allows you to pass control from one piece of middleware to another, allowing for modularity.



- What are some issues with the following code? (consider all aspects: performance, structure, naming, etc)

```js
async function getUsers() {
  const elie = await $.getJSON('https://api.github.com/users/elie');
  const joel = await $.getJSON('https://api.github.com/users/joelburton');
  const matt = await $.getJSON('https://api.github.com/users/mmmaaatttttt');

  return [elie, matt, joel];
}
```

The issue with this code lies in its sequential execution nature. The functions `$.getJSON()` are not executed concurrently but rather one after another. 
The issue with this code lies in its structure and execution order. The functions `$.getJSON ()` are executed one after another using promises which means that they will be executed sequentially instead of concurrent.
The issue with this code is that it makes three separate API requests to GitHub's user profile. 