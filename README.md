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
