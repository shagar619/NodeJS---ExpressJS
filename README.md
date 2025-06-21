<!-- markdownlint-disable MD012 MD026 MD001 MD022 MD032 MD029 MD019 MD034 MD031 MD047 MD040 MD009 MD058  -->


# Questions About Node JS

#### 🔹 What is Node.js?
Node.js is a JavaScript runtime environment that allows developers to run JavaScript code outside of a browser. It is built on top of the V8 JavaScript engine, which is used by Google Chrome and other web browsers. Node.js is used for building server-side applications, APIs, and real-time web applications.

#### 🚀 Key Features

- Asynchronous & Event-Driven: Non-blocking architecture handles multiple requests simultaneously.

- Single-threaded but Scalable: Uses an event loop for handling concurrent operations efficiently.

- Built-in Libraries: Offers core modules (like `http`, `fs`, `path`) to handle server, file, and network operations.

- NPM (Node Package Manager): Comes with the largest ecosystem of open-source libraries in the world.

#### 🛠️ Installing Node.js

you can install `Node.js` from the official website : https://nodejs.org/en/download/

To verify installation :

```bash
node -v
npm -v
```

#### 💡 Basic Example :

Simple HTTP server written in Node.js :

```javascript
// hello.js
const http = require('http');

const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('Hello, World!\n');
});

server.listen(3000, () => {
  console.log('Server is running at http://localhost:3000');
});
```

Run it using :

```bash
node hello.js
```

#### 📦 Using NPM Modules

You can install and use external libraries via `npm`.

Example : Create a simple web server using `Express`.

```bash
npm init -y
npm install express
```

```javascript
// server.js
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello from Express!');
});

app.listen(3000, () => {
  console.log('Express server running at http://localhost:3000');
});
```

#### ⚙️ Common Use Cases

- Building RESTful APIs

- Real-time applications (e.g., chats with Socket.IO)

- File handling scripts

- Automation tools and CLI apps

- Microservices and serverless apps

#### ❓Why is NodeJS single-threaded ?

NodeJS is single-threaded because it's based on the asynchronous, non-blocking nature of JavaScript. This design makes it simpler to develop and maintain, and it allows NodeJS to handle many concurrent requests efficiently.

#### ❓If NodeJS is single-threaded, then how does it handle concurrency?

NodeJS uses an event-driven, non-blocking I/O model to handle concurrency. It uses an event loop to handle asynchronous operations and manage the execution of code. This allows NodeJS to handle multiple concurrent requests without blocking the event loop, which improves performance and responsiveness.

#### ❓How does NodeJS handle I/O operations?

NodeJS uses an event-driven, non-blocking I/O model to handle I/O operations. It uses an event loop to handle asynchronous operations and manage the execution of code. This allows NodeJS to handle many concurrent I/O operations efficiently without blocking the event loop.

#### ❓Why is NodeJS preferred over other backend technologies like Java and PHP?

Here are some reasons why NodeJS is preferred:

- **Fast Performance**: NodeJS is known for its speed in handling I/O-heavy tasks.
- **NPM Ecosystem**: Node Package Manager offers over 50,000 bundles to help developers speed up development.
- **Real-Time Applications**: Perfect for data-intensive, real-time apps as it doesn't wait for APIs to return data.
- **Unified Codebase**: The Same code is used for both server and client, improving synchronization.
- **Easy for JavaScript Developers**: Since NodeJS is based on JavaScript, web developers can easily integrate it into their projects.
- **Cross-Platform**: NodeJS can run on multiple platforms, including Windows, macOS, and Linux.
- **Easy Deployment**: NodeJS is easy to deploy and maintain, making it a popular choice for web development.

---
---
---

## 🔹What is NPM?

NPM is a package manager for Node.js that allows developers to easily install, manage, and share packages of code. It is a free and open-source package management system that is used to install and manage packages for Node.js projects.

#### 🔑 Key Concepts

#### ✅ 1. Package

A package is a collection of reusable code that can be easily shared and used in other projects. It typically includes:

- JavaScript files

- `package.json` (metadata about the package)

- Optional documentation, configuration, and tests

#### ✅ 2. Registry

NPM connects to a central online registry at https://www.npmjs.com that hosts thousands of open-source

#### ✅ 3. Command Line Interface (CLI)

You interact with NPM through the terminal using commands like `npm install`, `npm init`, `npm update`, etc.

#### 📋 Common NPM Commands

| Command | Description |
|--------|-------------|
| `npm init` | Starts a new Node.js project by creating a `package.json` file |
| `npm init -y` | Initializes a project with default values (auto-generates `package.json`) |
| `npm install <package>` | Installs a specific package locally |
| `npm install -g <package>` | Installs a package globally |
| `npm install` | Installs all dependencies listed in `package.json` |
| `npm uninstall <package>` | Removes a package |
| `npm list` | Lists all locally installed packages |
| `npm list -g --depth=0` | Lists all globally installed packages |
| `npm outdated` | Lists outdated packages in your project |
| `npm update` | Updates all dependencies to their latest versions |
| `npm run <script>` | Runs a script defined in the `scripts` section of `package.json` |

#### Example :

```bash
# Initialize a new Node.js project (creates package.json)
npm init

# Initialize with default values (no prompts)
npm init -y

# Install a specific package (e.g., Express)
npm install express

# Install a package globally (e.g., Nodemon)
npm install -g nodemon

# Install all dependencies listed in package.json
npm install

# Uninstall a package
npm uninstall express

# List all installed packages (local)
npm list

# List all installed packages globally
npm list -g --depth=0

# Check for outdated packages
npm outdated

# Update all dependencies to the latest version
npm update

# Create a lock file and record exact package versions
npm install --package-lock

# Run a script defined in package.json (e.g., "start")
npm run start
```

#### 📦 Example : Installing a Package

```bash
# Install a specific package (e.g., axios)
npm install axios
```

This will :

- Download the `axios` package

- Add it to the `node_modules/` folder

- Add a dependency entry in `package.json`

```javascript
const axios = require('axios');

axios.get('https://api.github.com')
  .then(response => console.log(response.data))
  .catch(error => console.error(error));
```

```json
{
  "dependencies": {
    "axios": "^1.2.3"
  }
}
```

####  📁 Files NPM Uses

- `package.json` – Describes your project and its dependencies.

- `package-lock.json` – Records exact versions of installed packages to ensure consistency.

- `node_modules/` – Directory containing all installed packages.

#### 🌍 NPM in Practice

NPM enables:

- Code reuse across projects

- Dependency management in teams

- Easy setup of build tools, linters, test frameworks, and task runners

---
---
---

## 🔹What are the module in Node.js?

Node.js uses a module system to organize code into reusable modules. A module is a piece of code that can be imported and used in other parts of your application. Node.js provides several built-in modules, as well as a way to create custom modules.

#### 🧱 Types of Modules

#### 1. Built-in Modules

Node.js includes several modules out-of-the-box. No installation is needed.

| Module | Description |
|--------|-------------|
| `fs`   | File system operations |
| `http` | Create HTTP servers/clients |
| `path` | Handle file paths |
| `os`   | System information |
| `crypto` | Encryption and hashing |

**Example:**
```js
const fs = require('fs');
fs.writeFileSync('hello.txt', 'Hello from Node.js!');
```

#### 2. Local Modules

These are custom modules created within your project.

**Example :**
```js
module.exports = function(name) {
  return `Hello, ${name}!`;
};
```

```js
const greet = require('./greet');
console.log(greet('Alice')); // Output: Hello, Alice!
```

#### 3. Third-Party Modules

These are modules installed from the NPM registry.

**Install axios:**
```bash
npm install axios
```

**Use it:**
```js
const axios = require('axios');

axios.get('https://api.github.com')
  .then(res => console.log(res.data))
  .catch(err => console.error(err));
```

#### 🔄 Exporting and Importing Modules

**Export multiple functions:**
```js
// math.js
exports.add = (a, b) => a + b;
exports.sub = (a, b) => a - b;
```

**Import and use:**
```js
// app.js
const math = require('./math');
console.log(math.add(2, 3)); // 5
```

### 📘 ES Module Support

You can also use ES Modules (`import/export`) by:

- Renaming files to `.mjs`, or
- Adding `"type": "module"` to `package.json`

**Example :**
```js
export const add = (a, b) => a + b;
```

```js
import { add } from './math.mjs';
console.log(add(1, 2));
```

### 📌 Module Summary

| Type | Syntax | Example |
|------|--------|---------|
| Built-in | `require('fs')` | `fs.readFileSync()` |
| Local | `require('./module')` | Custom utility |
| Third-Party | `require('axios')` | Installed via NPM |

#### ❓What is the purpose of the `'require'` keyword in Node.js?
The `require` keyword in Node.js is used to import modules, which are reusable pieces of code that can be used in your application. It allows you to use the functionality provided by other developers in your project. For example, if you want to use a third-party library, you can use the `require` keyword to import it into your code.

```js
const axios = require('axios');
axios.get('https://api.example.com/data')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(error);
  });
```

#### ❓How to import a module in NodeJS?
We use the `require` module to import the External libraries in NodeJS. The result returned by `require()` is stored in a variable, which is used to invoke the functions using the dot notation.

---
---
---

## 🔹What is middleware?

**Middleware** in Node.js is a function that is executed between the **request** (`req`) and **response** (`res`) lifecycle of an HTTP **request** (`req`). It allows you to modify the **request** (`req`) or **response** (`res`) before it reaches the final destination. Middleware can be used for various purposes such as logging, authentication, error handling, and data transformation.

#### 🔁 Middleware Flow

```text
Request --> Middleware 1 --> Middleware 2 --> Route Handler --> Response
```

#### 🧱 Syntax

```js
app.use((req, res, next) => {
  console.log('This is a middleware function');
  next(); // Passes control to the next middleware
});
```

#### 📂 Types of Middleware

| Type | Description |
|------|-------------|
| Application-level | Middleware bound to an instance of `express()` |
| Router-level | Middleware bound to an instance of `express.Router()` |
| Built-in | Middleware provided by Express (e.g., `express.static`) |
| Third-party | Installed via NPM (e.g., `morgan`, `cors`) |
| Error-handling | Defined with **four** parameters: `(err, req, res, next)` |

---

#### 💡 Example: Application-Level Middleware

```js
const express = require('express');
const app = express();

// Middleware for logging every request
app.use((req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next(); // Pass control to the next middleware/route
});

app.get('/', (req, res) => {
  res.send('Hello, Middleware!');
});

app.listen(3000, () => {
  console.log('Server is running on port 3000');
});
```

#### 🧰 Example: Third-Party Middleware (`morgan`)

Install `morgan`:

```bash
npm install morgan
```

Use it in your app:

```js
const morgan = require('morgan');
app.use(morgan('dev')); // Logs HTTP requests
```

---

#### ⚠️ Error-Handling Middleware

```js
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send('Something went wrong!');
});
```

> ✅ Note: Error-handling middleware **must** have 4 parameters to be recognized by Express.

---

#### 📝 Summary

| Term | Description |
|------|-------------|
| `req` | HTTP Request object |
| `res` | HTTP Response object |
| `next()` | Moves control to the next middleware |
| `app.use()` | Registers middleware in the app |

Middleware functions are essential in Express for **logging, authentication, request parsing, error handling**, and more.

---
---
---

## 🔹What is control flow in Node.js?

Control flow in Node.js refers to the order in which code is executed. It involves the flow of execution through different parts of your application, such as functions, asynchronous operations, and event handling. In Node.js, control flow is managed by the event loop, which allows your program to handle multiple tasks concurrently without blocking the execution of other code.

#### 🧠 Why Control Flow Matters

JavaScript does **not wait** for an operation to complete. Instead, it moves on to the next line. That’s why control flow is important — to ensure that steps run in the correct sequence.

#### 📘 Common Asynchronous Patterns

#### 1. Callbacks

```js
const fs = require('fs');

fs.readFile('file.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data); // Executed after reading the file
});

console.log('Reading file...'); // Executed first
```

> ✅ Output:
```
Reading file...
<file content>
```

#### 2. Callback Hell (Pyramid of Doom)

```js
doSomething(function(result) {
  doSomethingElse(result, function(newResult) {
    doAnotherThing(newResult, function(finalResult) {
      console.log(finalResult);
    });
  });
});
```

> ❌ Hard to read and maintain

#### 3. Promises

```js
doSomething()
  .then(result => doSomethingElse(result))
  .then(newResult => doAnotherThing(newResult))
  .then(finalResult => console.log(finalResult))
  .catch(error => console.error(error));
```

> ✅ More manageable and readable than nested callbacks

#### 4. Async/Await (Modern Approach)

```js
async function run() {
  try {
    const result = await doSomething();
    const newResult = await doSomethingElse(result);
    const finalResult = await doAnotherThing(newResult);
    console.log(finalResult);
  } catch (err) {
    console.error(err);
  }
}
run();
```

> ✅ Cleaner syntax with built-in error handling using `try/catch`

#### 🔄 Example: Reading Files in Sequence

```js
const fs = require('fs').promises;

async function readFiles() {
  const file1 = await fs.readFile('a.txt', 'utf8');
  const file2 = await fs.readFile('b.txt', 'utf8');
  console.log(file1, file2);
}
readFiles();
```

#### 🧭 Summary

| Technique | Description |
|----------|-------------|
| **Callback** | First method used to handle async code |
| **Promises** | Chain-based async handling, cleaner than callbacks |
| **Async/Await** | ES2017+ syntax, best for readability and flow |
| **Control Flow** | Ensures steps run in correct order without blocking |

---
---
---

## 🔹What is package.json in NodeJS?

`package.json` is a file that contains metadata about your Node.js project, such as its name, version, dependencies, and scripts. It is used by the Node.js package manager, npm, to manage the project's dependencies and build process.

#### 🔧 Key Purposes of package.json :

- Project Metadata

- Dependency Management

- Script Definitions

- Package Publishing

- Project Configuration

#### 🧱 Basic Example

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "description": "A simple Node.js project",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": ["node", "example"],
  "author": "Your Name",
  "license": "MIT",
  "dependencies": {
    "express": "^4.17.1"
  }
}
```

## 📘 What is `package.json`?

`package.json` is the core configuration file in a Node.js project. It contains metadata about your project, including dependencies, scripts, version info, and more.

---

#### 📄 Key Fields

| Field              | Description |
|-------------------|-------------|
| **`name`**         | The name of your project or package. It must be lowercase and URL-safe. |
| **`version`**      | The version of your project following [Semantic Versioning](https://semver.org/), e.g., `1.0.0`. |
| **`description`**  | A brief explanation of what your project does. |
| **`main`**         | The entry point of your application (e.g., `index.js`). |
| **`scripts`**      | Defines command-line scripts that can be run using `npm run <script-name>`. |
| **`author`**       | Your name or organization as the author of the project. |
| **`license`**      | Type of license, such as `MIT`, `ISC`, or `UNLICENSED`. |
| **`dependencies`** | Packages your app needs to run (installed with `npm install`). |
| **`devDependencies`** | Packages only needed during development (e.g., testing tools, linters). |


#### 🔄 Common Commands Related to `package.json`

- `npm init` – Initializes a new `package.json` interactively.

- `npm init -y` – Creates a `package.json` with default values.

- `npm install <pkg>` – Installs and adds to `dependencies`.

- `npm install <pkg> --save-dev` – Installs and adds to `devDependencies`.

- `npm run <script>` – Executes a defined `script`.

- `npm install nodemon --save-dev` - Installs `nodemon` as a development dependency.

- `npm install express` - Installs `express` as a dependency.

- `npm update` - Updates all dependencies to their latest versions.

- `npm uninstall <pkg>` - Removes a package from `dependencies` or `devDependencies`.

- `npm uninstall express` - Removes `express` from `dependencies`.

---
---
---
#### ❓ What are the most commonly used libraries in NodeJS?

There are the two most commonly used libraries in NodeJs:

- **ExpressJS** : ExpressJS is a minimal and flexible web application framework for building robust APIs and web apps. It simplifies routing, middleware handling, and request/response management.
- **Mongoose** : An Object Data Modeling (ODM) library for MongoDB and NodeJS, it helps in managing data relationships, schema validation, and business logic.

#### ❓ What is the difference between `require` and `import` in NodeJS?

In NodeJS, `require` is used for importing modules, while `import` is used for importing modules in ES6 modules.
- **`require`** : Used to import modules in NodeJS. It is synchronous and loads the module synchronously.
- **`import`** : Used to import modules in ES6 modules. It is asynchronous and loads the module asynchronously.

---
---
---




## 🔹 How do you handle errors in NodeJS?

Error handling in Node.js is essential to building stable, secure, and reliable applications. Node.js uses both synchronous and asynchronous patterns, so error handling depends on the type of cod. you're writing.

#### 1. Try-Catch (for synchronous code or `async/await`)

```javascript
try {
    // Code that may throw an error
} catch (error) {
    // Handle the error
}
```
#### ✅ Use this for synchronous code or async/await functions.

#### 2. Async/Await with Try-Catch

```javascript
async function myFunction() {
    try {
        // Code that may throw an error
    } catch (error) {
        // Handle the error
    }
}
```
#### ✅ Use this for async/await functions.

#### 3. Callback Pattern (Error-First Callbacks)
Node.js uses an error-first callback pattern. The first argument in the callback is reserved for errors.

```javascript
fs.readFile('file.txt', 'utf8', (err, data) => {
  if (err) {
    return console.error('Error reading file:', err);
  }
  console.log(data);
});
```

#### 4. Event Emitters (`.on('error')`)
Some Node.js core modules (like streams) emit `error` events.

```javascript
const stream = fs.createReadStream('missing.txt');

stream.on('error', (err) => {
  console.error('Stream error:', err.message);
});
```

5. Global Error Handling (Use with caution)
- Uncaught exceptions

```javascript
process.on('uncaughtException', (err) => {
  console.error('Uncaught Exception:', err);
  process.exit(1); // Consider exiting the process
});
```
- Unhandled promise rejections

```javascript
process.on('unhandledRejection', (reason, promise) => {
  console.error('Unhandled Rejection:', reason);
});
  process.exit(1); // Consider exiting the process
});
```

6. Custom Error Classes
- For better error structure and control :

```javascript
class CustomError extends Error {
  constructor(message) {
    super(message);
    this.name = this.constructor.name; // Set the error name
  }
}
// Usage
try {
  throw new CustomError('Something went wrong!');
} catch (error) {
  console.error(error.name, error.message);
}
```


---
---
---


## 🔹What are promises in NodeJS?

Promises are a way to handle asynchronous operations in JavaScript, including Node.js. They represent a value that may be available now, or in the future, or never. Promises provide a cleaner alternative to the traditional callback approach.

Promises can be in one of three states:
- **Pending** : The initial state, neither fulfilled nor rejected.
- **Fulfilled** : The operation completed successfully.
- **Rejected** : The operation failed.

#### 🧠 Basic Syntax


```javascript
const myPromise = new Promise((resolve, reject) => {
  // Asynchronous task
  const success = true;

  if (success) {
    resolve('Task completed');
  } else {
    reject('Task failed');
  }
});

myPromise
  .then(result => {
    console.log('Success:', result);
  })
  .catch(error => {
    console.error('Error:', error);
  });

```

#### ✅ Using Promises with Async/Await

```javascript
function delay(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}

async function run() {
  console.log('Waiting...');
  await delay(1000); // pauses 1 second
  console.log('Done!');
}

run();
```

#### 📌 Built-in Promise-Based APIs in Node.js
Many modern Node.js APIs (like `fs.promises`) return Promises :


```javascript
const fs = require('fs/promises');

async function readFile() {
  try {
    const data = await fs.readFile('example.txt', 'utf8');
    console.log(data);
  } catch (err) {
    console.error('Error reading file:', err);
  }
}

readFile();
```

#### 📌 Promise.all

You can use `Promise.all` to run multiple promises in parallel and wait for all of them to complete:

```javascript
const promise1 = Promise.resolve('First promise resolved');
const promise2 = new Promise((resolve) => {
    setTimeout(() => {
        resolve('Second promise resolved');
    }, 1000);
});

Promise.all([promise1, promise2])
    .then(results => {
        console.log(results); // ['First promise resolved', 'Second promise resolved']
    })
    .catch(error => {
        console.error(error);
    });
```

#### 🧵 Wrapping a Callback in a Promise

```javascript
const fs = require('fs');

function readFilePromise(path) {
  return new Promise((resolve, reject) => {
    fs.readFile(path, 'utf8', (err, data) => {
      if (err) reject(err);
      else resolve(data);
    });
  });
}
```

#### 🧰 Common Promise Methods – Summary Table

| Method                  | Description                                                  |
|--------------------------|--------------------------------------------------------------|
| `then()`                | Handles the resolved value of a Promise                       |
| `catch()`               | Catches and handles any errors (rejected Promises)            |
| `finally()`             | Executes code after a Promise is settled (fulfilled or rejected) |
| `Promise.all()`         | Waits for all Promises to fulfill, or rejects if any fail     |
| `Promise.race()`        | Resolves/rejects as soon as the first Promise settles         |
| `Promise.allSettled()`  | Waits for all Promises to settle and returns all results      |
| `Promise.any()`         | Resolves when any Promise is fulfilled (ignores rejections)   |

### 🛠 Why Use Promises?
- **Avoid Callback Hell** : Promises help flatten the nested structure of callbacks, making code more readable.
- **Chaining** : You can chain multiple `.then()` calls for sequential operations.
- **Error Handling** : Promises provide a cleaner way to handle errors using `.catch()`.
- **Asynchronous Control Flow** : Promises allow you to manage asynchronous operations more effectively.


---
---
---

## 🔹What is event-driven programming in NodeJS?

In event-driven programming, the flow of the program is determined by events — such as user interactions, data arriving, or timers completing.

Node.js uses an event loop and an event emitter pattern to handle these events efficiently, making it highly scalable and non-blocking.

#### 🚦 Key Concepts
#### 1. **Events**
An event is a signal that something has happened (e.g., data received, connection opened, file read).

#### 2. **Listeners**
Functions that are attached to events and get executed when the event occurs.

#### 📦 Node.js EventEmitter Example
Node.js provides the `EventEmitter` class from the `events` module :

```javascript
const EventEmitter = require('events');

const emitter = new EventEmitter();

// Register a listener
emitter.on('greet', (name) => {
  console.log(`Hello, ${name}!`);
});

// Emit an event
emitter.emit('greet', 'Alice');
// Output: Hello, Alice!
```

#### ⚙️ How Node.js Uses Events Internally
Node.js is built on an event-driven architecture, which is used in:

- HTTP servers (handling requests)

- Streams (reading/writing files or network data)

- Sockets (real-time communication)

- Process events (`exit`, `uncaughtException`, etc.)

#### 🔁 The Event Loop

The event loop is the core of Node.js's asynchronous nature. It continuously checks for events and executes their associated listeners.
```javascript
const fs = require('fs');

fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data);
});

console.log('Reading file...');
```

#### ✅ Benefits of Event-Driven Programming in Node.js
- High concurrency with low overhead

- Non-blocking I/O

- Efficient resource usage

- Great for real-time apps (e.g., chat, games)

#### 🧪 Real-World Example: HTTP Server

```javascript
const http = require('http');

const server = http.createServer((req, res) => {
  res.end('Hello from server');
});

server.listen(3000, () => {
  console.log('Server running on port 3000');
});
```

---
---
---

## 🔹What are the different types of HTTP requests?

In HTTP (Hypertext Transfer Protocol), different types of requests (also called methods) define what action the client wants the server to perform on a resource.

#### 🌐 Common HTTP Request Methods

| Method     | Description                                       | Safe | Idempotent |
|------------|---------------------------------------------------|------|------------|
| `GET`      | Retrieve data from the server                     | ✅   | ✅         |
| `POST`     | Submit new data to the server                     | ❌   | ❌         |
| `PUT`      | Replace an entire resource                        | ❌   | ✅         |
| `PATCH`    | Update part of a resource                         | ❌   | ❌         |
| `DELETE`   | Remove a resource                                 | ❌   | ✅         |
| `HEAD`     | Retrieve headers only (no body)                   | ✅   | ✅         |
| `OPTIONS`  | Returns allowed HTTP methods for a resource       | ✅   | ✅         |


#### 1. **GET**

- Retrieves data from the server.

- Should have no side effects (i.e., not change data).

- Used for: reading articles, listing products, loading user data.

```javascript
const http = require('http');

http.createServer((req, res) => {
  if (req.method === 'GET') {
    res.writeHead(200, { 'Content-Type': 'text/plain' });
    res.end('Hello, World!');
  }
}).listen(3000, () => {
  console.log('Server running on port 3000');
});
```
#### 2. **POST**
- Submits new data to the server.
- Can create new resources or trigger actions.
- Used for: submitting forms, uploading files, creating new records.

```javascript
const http = require('http');

http.createServer((req, res) => {
  if (req.method === 'POST') {
    let body = '';
    req.on('data', chunk => {
      body += chunk.toString();
    });
    req.on('end', () => {
      res.writeHead(200, { 'Content-Type': 'application/json' });
      res.end(JSON.stringify({ message: 'Data received', data: body }));
    });
  }
}).listen(3000, () => {
  console.log('Server running on port 3000');
});
```
#### 3. **PUT**
- Replaces an entire resource with new data.
- Idempotent: multiple identical requests have the same effect as a single request.
- Used for: updating user profiles, replacing documents.

```javascript
const http = require('http');
http.createServer((req, res) => {
  if (req.method === 'PUT') {
    let body = '';
    req.on('data', chunk => {
      body += chunk.toString();
    });
    req.on('end', () => {
      res.writeHead(200, { 'Content-Type': 'application/json' });
      res.end(JSON.stringify({ message: 'Resource updated', data: body }));
    });
  }
}).listen(3000, () => {
  console.log('Server running on port 3000');
});
```
#### 4. **PATCH**
- Partially updates a resource.
- Not idempotent: multiple requests may have different effects.
- Used for: updating specific fields in a user profile, modifying parts of a document.

```javascript
const http = require('http');
http.createServer((req, res) => {
  if (req.method === 'PATCH') {
    let body = '';
    req.on('data', chunk => {
      body += chunk.toString();
    });
    req.on('end', () => {
      res.writeHead(200, { 'Content-Type': 'application/json' });
      res.end(JSON.stringify({ message: 'Resource partially updated', data: body }));
    });
  }
}).listen(3000, () => {
  console.log('Server running on port 3000');
});
```
#### 5. **DELETE**
- Removes a resource from the server.
- Idempotent: multiple identical requests have the same effect as a single request.
- Used for: deleting user accounts, removing items from a shopping cart.

```javascript
const http = require('http');

http.createServer((req, res) => {
  if (req.method === 'DELETE') {
    res.writeHead(200, { 'Content-Type': 'application/json' });
    res.end(JSON.stringify({ message: 'Resource deleted' }));
  }
}).listen(3000, () => {
  console.log('Server running on port 3000');
});
```
#### 6. **HEAD**
- Similar to `GET`, but retrieves only the headers, not the body.
- Used for checking resource metadata without downloading the content.
```javascript
const http = require('http');

http.createServer((req, res) => {
  if (req.method === 'HEAD') {
    res.writeHead(200, { 'Content-Type': 'application/json' });
    res.end(JSON.stringify({ message: 'HEAD request received' }));
  }
}).listen(3000, () => {
  console.log('Server running on port 3000');
});
```
#### 7. **OPTIONS**
- Returns the HTTP methods that the server supports for a specific resource.
- Used for CORS preflight requests and discovering server capabilities.
```javascript
const http = require('http');

http.createServer((req, res) => {
  if (req.method === 'OPTIONS') {
    res.writeHead(200, { 'Content-Type': 'application/json' });
    res.end(JSON.stringify({ message: 'OPTIONS request received' }));
  }
}).listen(3000, () => {
  console.log('Server running on port 3000');
});
```
---
---
---

## 🔹What is a buffer in NodeJS?
A buffer is a temporary storage area in memory used to hold data while it is being transferred between two locations. In Node.js, buffers are used to handle binary data streams, such as file I/O or network communication. Buffers allow you to work with raw binary data directly, without having to convert it to a string or other data type.

#### 🧱 Key Features of Buffers
- **Fixed Size** : Buffers have a fixed size, which is defined when they are created.
- **Binary Data** : Buffers can hold raw binary data, making them suitable for handling files, images, and network protocols.
- **Efficient** : Buffers are designed for high performance and low memory overhead.

#### ✅ Use Cases :
- Reading and writing files
- Handling network protocols (TCP, UDP)
- Processing binary data (images, audio, video)
- Converting between different encodings (`utf8`, `base64`, `hex`, etc.).

#### 📦 Creating Buffers
```javascript
const buffer1 = Buffer.alloc(10); // Creates a buffer of size 10 bytes, filled with zeros
const buffer2 = Buffer.from('Hello, World!'); // Creates a buffer from a string
const buffer3 = Buffer.from([1, 2, 3, 4, 5]); // Creates a buffer from an array of bytes
```

#### Working with Buffers:
```javascript
const buf = Buffer.from('Node.js');

// Access bytes
console.log(buf[0]); // 78 (ASCII for 'N')

// Modify buffer
buf[0] = 110; // changes 'N' to 'n'

// Convert back to string
console.log(buf.toString()); // 'node.js'
``` 

#### Buffer Methods
| Method                | Description |
|-----------------------|-------------|
| `Buffer.alloc(size)`  | Creates a buffer of the specified size, filled with zeros. |
| `Buffer.from(string)` | Creates a buffer from a string. |
| `Buffer.from(array)`  | Creates a buffer from an array of bytes. |
| `buf.toString()`      | Converts the buffer to a string. |
| `buf.length`          | Gets the length of the buffer. |
| `buf[index]`         | Accesses a specific byte in the buffer. |

#### Example Use Case :

```javascript
const fs = require('fs');
const buffer = Buffer.alloc(1024); // Create a buffer of 1KB
fs.readFile('example.txt', (err, data) => {
  if (err) throw err;
  data.copy(buffer); // Copy file data into the buffer
  console.log('Buffer content:', buffer.toString('utf8', 0, data.length));
});
```
> N:B: Here, `data` is a `Buffer` containing the file's binary content.

---
---
---


## 🔹What are streams in NodeJS?

Streams are a powerful feature in Node.js that allow you to read and write data in a continuous flow, rather than loading the entire data into memory at once. This is particularly useful for handling large files or data sources, as it reduces memory usage and improves performance.

#### 🔄 Four Types of Streams

| Type       | Description                                  | Example Usage                     |
|------------|----------------------------------------------|-----------------------------------|
| `Readable` | Stream from which data can be read           | Reading files, HTTP requests      |
| `Writable` | Stream to which data can be written          | Writing to files, HTTP responses  |
| `Duplex`   | Stream that is both readable and writable    | TCP sockets                       |
| `Transform`| Duplex stream that modifies the data         | Compression, encryption, etc.     |

#### 📦 Readable Streams
Readable streams allow you to read data from a source, such as a file or network socket, in chunks. You can listen for the `data` event to process each chunk of data as it arrives.

```javascript
const fs = require('fs');
const readableStream = fs.createReadStream('example.txt', { encoding: 'utf8' });
readableStream.on('data', (chunk) => {
  console.log('Received chunk:', chunk);
});
readableStream.on('end', () => {
  console.log('No more data to read.');
});
```

#### 📦 Writable Streams
Writable streams allow you to write data to a destination, such as a file or network socket. You can use the `write()` method to send data to the stream.

```javascript
const fs = require('fs');
const writableStream = fs.createWriteStream('output.txt', { encoding: 'utf8' });
writableStream.write('Hello, World!\n');
writableStream.write('This is a writable stream example.\n');
writableStream.end(() => {
  console.log('Data has been written to output.txt');
});
```
#### 📦 Duplex Streams
Duplex streams are both readable and writable. They allow you to read data from a source and write data to a destination simultaneously.

```javascript
const { Duplex } = require('stream');
const duplexStream = new Duplex({
  read(size) {
    this.push('Hello from readable side!\n');
    this.push(null); // No more data to read
  },
  write(chunk, encoding, callback) {
    console.log('Received from writable side:', chunk.toString());
    callback();
  }
});
duplexStream.on('data', (chunk) => {
  console.log('Data from duplex stream:', chunk.toString());
});
duplexStream.write('Hello from writable side!\n');
duplexStream.end();
```
#### 📦 Transform Streams
Transform streams are a type of duplex stream that can modify the data as it is being read or written. They are useful for tasks like compression, encryption, or data transformation.

```javascript
const { Transform } = require('stream');
const transformStream = new Transform({
  transform(chunk, encoding, callback) {
    const upperCaseChunk = chunk.toString().toUpperCase();
    this.push(upperCaseChunk);
    callback();
  }
});
const readableStream = fs.createReadStream('example.txt', { encoding: 'utf8' });
readableStream.pipe(transformStream).pipe(process.stdout);
```

#### 🎯 Benefits of Streams :
- Efficient for large or continuous data

- Reduces memory usage

- Enables real-time data processing

- Ideal for I/O-bound applications

---
---
---

## 🔹What is the passport module in NodeJS?

Passport is a popular authentication middleware for Node.js that simplifies the process of implementing various authentication strategies in your application. It provides a consistent API for handling user authentication, making it easier to integrate with different authentication providers (like Google, Facebook, Twitter, etc.) or use local authentication (username/password).

It provides a simple and modular approach to handling different types of authentication strategies such as :

- Username/password (local)

- OAuth (Google, Facebook, GitHub, etc.)

- JWT (JSON Web Tokens)

- SAML, LDAP, OpenID Connect, and many others

#### 📦 Installing Passport

```bash
npm install passport
```
To use the local strategy (username/password), also install :

```bash
npm install passport-local
```

#### ✅ Example : Local Authentication with Passport

1. Setup Passport

```javascript
const passport = require('passport');
const LocalStrategy = require('passport-local').Strategy;

// Dummy user for example
const user = { id: 1, username: 'admin', password: 'secret' };

// Configure local strategy
passport.use(new LocalStrategy((username, password, done) => {
  if (username === user.username && password === user.password) {
    return done(null, user);
  } else {
    return done(null, false, { message: 'Incorrect credentials.' });
  }
}));

// Serialize user to session
passport.serializeUser((user, done) => {
  done(null, user.id);
});

// Deserialize user from session
passport.deserializeUser((id, done) => {
  if (id === user.id) {
    done(null, user);
  } else {
    done('User not found');
  }
});
```
2. Integrate with Express

```javascript
const express = require('express');
const session = require('express-session');
const app = express();

app.use(session({
  secret: 'your_secret_key',
  resave: false,
  saveUninitialized: false
}));
app.use(passport.initialize());
app.use(passport.session());
app.use(express.urlencoded({ extended: true })); // For parsing form data
app.post('/login', passport.authenticate('local', {
  successRedirect: '/success',
  failureRedirect: '/login'
}));
app.get('/success', (req, res) => {
  res.send(`Welcome ${req.user.username}!`);
});
app.get('/login', (req, res) => {
  res.send('<form method="post"><input name="username"><input name="password" type="password"><button type="submit">Login</button></form>');
});
app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```

#### 🔐 Protecting Routes
```javascript
function ensureAuthenticated(req, res, next) {
  if (req.isAuthenticated()) {
    return next();
  }
  res.redirect('/login');
}

app.get('/protected', ensureAuthenticated, (req, res) => {
  res.send(`This is a protected route. Welcome ${req.user.username}!`);
});
```

#### 🌐 Other Strategies
You can easily add other strategies :

- Google OAuth : `passport-google-oauth20`

- JWT : `passport-jwt`

- Facebook : `passport-facebook`

Each strategy follows the same pattern : `passport.use(new Strategy(...))`.

---
---
---

## 🔹What is callback hell?

Callback hell, also known as "Pyramid of Doom," refers to a situation in JavaScript where multiple nested callbacks make the code difficult to read and maintain. This often occurs when dealing with asynchronous operations, leading to deeply nested structures that resemble a pyramid.

#### ❌ Example of Callback Hell

```javascript
doSomething(function (err, result1) {
  if (err) throw err;

  doSomethingElse(result1, function (err, result2) {
    if (err) throw err;

    doAnotherThing(result2, function (err, result3) {
      if (err) throw err;

      finish(result3, function (err, finalResult) {
        if (err) throw err;

        console.log('Done:', finalResult);
      });
    });
  });
});
```

This nesting keeps growing with each async operation, making the code:

- Hard to follow

- Difficult to debug

- Error-prone

- Unscalable


#### ✅ How to Fix Callback Hell :

1. **Use Promises** : Promises allow you to chain asynchronous operations, flattening the structure.

```javascript
doSomething()
  .then(result1 => doSomethingElse(result1))
  .then(result2 => doAnotherThing(result2))
  .then(result3 => finish(result3))
  .then(finalResult => console.log('Done:', finalResult))
  .catch(err => console.error('Error:', err));
```
2. **Use Async/Await** : This syntax makes asynchronous code look synchronous, improving readability.

```javascript
async function run() {
  try {
    const result1 = await doSomething();
    const result2 = await doSomethingElse(result1);
    const result3 = await doAnotherThing(result2);
    const finalResult = await finish(result3);
    console.log('Done:', finalResult);
  } catch (err) {
    console.error('Error:', err);
  }
}
run();
```
3. **Modularize Code** : Break down complex functions into smaller, reusable functions to reduce nesting.

```javascript
function step1(data, cb) { /* ... */ }
function step2(data, cb) { /* ... */ }
function step3(data, cb) { /* ... */ }

// Then call them in sequence
step1(input, function (err, result1) {
  if (err) return handleError(err);
  step2(result1, function (err, result2) {
    if (err) return handleError(err);
    step3(result2, function (err, result3) {
      if (err) return handleError(err);
      console.log('Done:', result3);
    });
  });
});
```

---
---
---

## 🔹What are timers module in NodeJS?

The timers module in Node.js provides a way to execute code after a specified delay or at regular intervals. It is built into Node.js and is part of the global scope, so you don't need to require it explicitly.

#### 🕒 Key Functions

1. **setTimeout()**: Executes a function after a specified delay (in milliseconds).

```javascript
setTimeout(() => {
  console.log('Executed after 2 seconds');
}, 2000);
```

2. **setInterval()**: Repeatedly executes a function at specified intervals (in milliseconds).

```javascript
setInterval(() => {
  console.log('Executed every 1 second');
}, 1000);
```

3. **clearTimeout()**: Cancels a timeout that was previously established by `setTimeout()`.

```javascript
const timeoutId = setTimeout(() => {
  console.log('This will not be executed');
}, 2000);
clearTimeout(timeoutId);
```

4. **clearInterval()**: Cancels an interval that was previously established by `setInterval()`.

```javascript
const intervalId = setInterval(() => {
  console.log('This will not be executed');
}, 1000);
clearInterval(intervalId);
```

### ⏳ Use Cases

- Delaying the execution of a function
- Repeatedly executing a function at fixed intervals
- Implementing timeouts for asynchronous operations

### ⚠️ Important Notes

- Timers are not guaranteed to execute exactly after the specified delay. They are subject to the event loop and other factors that may affect timing.
- Using timers can lead to callback hell if not managed properly, so consider using Promises or async/await for better readability.
### 🧰 Example: Using Timers in Node.js

```javascript
console.log('Start');

setTimeout(() => {
  console.log('Executed after 2 seconds');
}, 2000);

setInterval(() => {
  console.log('Executed every 1 second');
}, 1000);

console.log('End');
```
### Output
```
Start
End
Executed after 2 seconds
Executed every 1 second
Executed every 1 second
Executed every 1 second
...
```
#### 📦 Common Timer Functions

| Function              | Description                                                       |
|-----------------------|-------------------------------------------------------------------|
| `setTimeout(fn, ms)`  | Executes a function once after a delay                            |
| `setInterval(fn, ms)` | Repeatedly executes a function at every interval                  |
| `setImmediate(fn)`    | Executes a function immediately after I/O events                  |
| `process.nextTick(fn)`| Executes a function before the next event loop iteration begins   |

---
---
---


## 🔹What is the difference between `fs.readFile` and `fs.readFileSync` in NodeJS?

`fs.readFile` and `fs.readFileSync` are both methods in the Node.js `fs` (file system) module used to read files, but they differ in how they handle asynchronous operations.
| Feature                | `fs.readFile`                          | `fs.readFileSync`                     |
|-----------------------|---------------------------------------|---------------------------------------|
| Asynchronous           | Yes                                   | No                                    |
| Blocking               | No                                    | Yes                                   |
| Callback               | Requires a callback                   | Returns the content directly          |
| Use Case               | Non-blocking I/O operations           | Simple scripts or startup tasks      |
| Error Handling         | Uses a callback for error handling    | Throws an error if file not found     |
| Performance            | Better for I/O-bound tasks            | Slower for large files due to blocking|
| Example Usage         | `fs.readFile('file.txt', callback)`  | `const data = fs.readFileSync('file.txt')` |
#### 📦 Example of `fs.readFile`

```javascript
const fs = require('fs');
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error('Error reading file:', err);
    return;
  }
  console.log('File content:', data);
});
```
#### 📦 Example of `fs.readFileSync`

```javascript
const fs = require('fs');
const data = fs.readFileSync('example.txt', 'utf8');
console.log('File content:', data);
```
#### 📌 When to Use Each
- **Use `fs.readFile`** when you want to perform non-blocking I/O operations, especially in a server environment where you want to handle multiple requests concurrently without blocking the event loop.
- **Use `fs.readFileSync`** when you need to read a file synchronously, such as during the startup of a script or when you are sure that the file is small and won't block the event loop for too long.

---
---
---

## 🔹What is a `.body-parser` in NodeJS?

`body-parser` is a middleware in Node.js that is used to parse incoming request bodies in a middleware before your handlers, available under the `req.body` property. It is particularly useful for handling data sent in HTTP requests, such as form submissions or JSON payloads.

#### 📦 Installing body-parser
```bash
npm install body-parser
```
#### ✅ Basic Usage
```javascript
const express = require('express');
const bodyParser = require('body-parser');
const app = express();
// Parse application/json
app.use(bodyParser.json());
// Parse application/x-www-form-urlencoded
app.use(bodyParser.urlencoded({ extended: true }));
// Example route
app.post('/submit', (req, res) => {
  console.log(req.body); // Access parsed data
  res.send('Data received');
});
app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```
#### 📌 Middleware Options
- `bodyParser.json()` : Parses incoming requests with JSON payloads.
- `bodyParser.urlencoded({ extended: true })` : Parses incoming requests with URL-encoded payloads (like form submissions).
- `bodyParser.text()` : Parses incoming requests with plain text payloads.
- `bodyParser.raw()` : Parses incoming requests with binary data.
#### 📌 Example of Parsing JSON Data
```javascript
app.post('/json', (req, res) => {
  console.log(req.body); // Access parsed JSON data
  res.json({ message: 'JSON data received', data: req.body });
});
```
#### 📌 Example of Parsing URL-Encoded Data
```javascript
app.post('/form', (req, res) => {
  console.log(req.body); // Access parsed form data
  res.json({ message: 'Form data received', data: req.body });
});
```
#### 📌 Important Notes
- `body-parser` is now built into Express as of version 4.16.0, so you can use `express.json()` and `express.urlencoded()` instead of requiring `body-parser` separately.
- Always use `body-parser` before your route handlers to ensure that the request body is parsed before you access it.
### 📦 Example with Express Built-in Middleware
```javascript
const express = require('express');
const app = express();
// Parse application/json
app.use(express.json());
// Parse application/x-www-form-urlencoded
app.use(express.urlencoded({ extended: true }));
// Example route
app.post('/submit', (req, res) => {
  console.log(req.body); // Access parsed data
  res.send('Data received');
});
app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```
---
---
---

## 🔹What is `CORS` in NodeJS?

CORS stands for Cross-Origin Resource Sharing. It is a security feature implemented by browsers to control how web pages can request resources from a different domain (origin) than the one that served the web page.

> In Node.js (especially with Express.js), CORS is something you configure on your server to allow or block requests from other origins.
#### 📦 Why CORS is Important
Normally, browsers block cross-origin HTTP requests (for security reasons). So if your frontend (e.g., `http://localhost:3000`) tries to call an API on `http://localhost:5000`, the browser will block it unless the server explicitly allows it.
#### 📦 How CORS Works
When a web application makes a cross-origin request, the browser sends an HTTP request with an `Origin` header indicating the origin of the request. The server can respond with specific CORS headers to indicate whether the request is allowed or denied.


#### 🔐 CORS in Action
Without CORS:
```http
Origin: http://localhost:3000
GET http://localhost:5000/api/users → ❌ Blocked by browser
```
```javascript
fetch('http://localhost:5000/api/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```
With CORS enabled:
```http
Origin: http://localhost:3000
GET http://localhost:5000/api/users → ✅ Allowed by server
```
```javascript
fetch('http://localhost:5000/api/data', {
  method: 'GET',
  headers: {
    'Origin': 'http://localhost:3000'
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

#### ✅ Enabling CORS in Node.js (Express)
#### 📦 Step 1: Install cors middleware
```bash
npm install cors
```
#### 🛠 Step 2: Use it in your Express app
```javascript
const express = require('express');
const cors = require('cors');

const app = express();

// Allow all origins (open CORS policy)
app.use(cors());

app.get('/api/data', (req, res) => {
  res.json({ message: 'CORS enabled!' });
});
```

#### 🔧 Restrict to Specific Origin
```javascript
app.use(cors({
  origin: 'http://localhost:3000' // Allow only this origin
}));
```

#### ⚙️ CORS Options

```javascript
app.use(cors({
  origin: 'http://example.com', // Allow only this origin
  methods: 'GET,POST', // Allowed HTTP methods
  allowedHeaders: 'Content-Type,Authorization', // Allowed headers
  credentials: true // Allow cookies to be sent
}));
```

#### 📦 Common CORS Headers
| Header                  | Description                                                  |
|-------------------------|--------------------------------------------------------------|
| `Access-Control-Allow-Origin` | Specifies which origins are allowed to access the resource. Use `*` to allow all origins. |
| `Access-Control-Allow-Methods` | Specifies which HTTP methods are allowed (e.g., GET, POST, PUT, DELETE). |
| `Access-Control-Allow-Headers` | Specifies which headers can be included in the request. |
| `Access-Control-Allow-Credentials` | Indicates whether the browser should include credentials (cookies, HTTP authentication) in the request. |
| `Access-Control-Expose-Headers` | Specifies which headers can be exposed to the browser. |
| `Access-Control-Max-Age` | Specifies how long the results of a preflight request can be cached. |

---
---
---

## 🔹What is the purpose of NODE_ENV?

**`NODE_ENV`** is an environment variable in Node.js used to define the environment in which a Node.js application is running — such as:

- `development`

- `production`

- `test`

#### 🔧 Common Environment Values

| Value         | Purpose                                                   |
|---------------|------------------------------------------------------------|
| `development` | Default for development — detailed logs, no caching       |
| `production`  | For deployed apps — optimized, minified, minimal logging  |
| `test`        | Used when running automated tests                         |

#### ✅ Example Usage in Code
```javascript
if (process.env.NODE_ENV === 'production') {
  console.log('Running in production mode');
} else if (process.env.NODE_ENV === 'development') {
  console.log('Running in development mode');
} else {
  console.log('Running in an unknown environment');
}
```

#### ⚙️ How to Set NODE_ENV
- **Linux/Mac**: Set it in the terminal before running your app.
```bash
export NODE_ENV=production
node app.js
```
```bash
set NODE_ENV=production
node app.js
```
- **Windows**: Use `set` command in the Command Prompt.
```bash
set NODE_ENV=production
node app.js
```
- **Using npm scripts**: You can set `NODE_ENV` in your `package.json` scripts.
```json
{
  "scripts": {
    "start": "NODE_ENV=production node app.js",
    "dev": "NODE_ENV=development nodemon app.js"
  }
}
```
- install `cross-env` for cross-platform compatibility:
```bash
npm install cross-env
```
- **Using dotenv**: You can also use a `.env` file with the `dotenv` package to manage environment variables.
```bash
NODE_ENV=production
```
```javascript
require('dotenv').config();
console.log(process.env.NODE_ENV); // 'production'
```

---
---
---

