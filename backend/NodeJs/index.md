# Node.js

## Introduction
Node.js is an open-source, cross-platform, JavaScript runtime environment that executes JavaScript code outside of a web browser. It is designed to build scalable network applications.

## Basic Syntax
```javascript
// Example of a basic Node.js server
const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello, World!\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

## Common Use Cases
- Building RESTful APIs
- Real-time applications
- Microservices
- Command-line tools

## Advanced Features
- **Asynchronous Programming**: Use callbacks, promises, and async/await for non-blocking code.
- **Streams**: Handle streaming data efficiently.
- **Cluster Module**: Utilize multi-core systems for better performance.
- **Modules**: Organize code into reusable modules.

## Code Snippets
### Asynchronous Programming
```javascript
// Using Promises
const fs = require('fs').promises;

fs.readFile('example.txt', 'utf8')
  .then(data => {
    console.log(data);
  })
  .catch(err => {
    console.error(err);
  });
```

### Streams
```javascript
// Reading a file using streams
const fs = require('fs');
const readStream = fs.createReadStream('example.txt', 'utf8');

readStream.on('data', chunk => {
  console.log(chunk);
});
```

### Cluster Module
```javascript
const cluster = require('cluster');
const http = require('http');
const numCPUs = require('os').cpus().length;

if (cluster.isMaster) {
  console.log(`Master ${process.pid} is running`);

  // Fork workers
  for (let i = 0; i < numCPUs; i++) {
    cluster.fork();
  }

  cluster.on('exit', (worker, code, signal) => {
    console.log(`Worker ${worker.process.pid} died`);
  });
} else {
  // Workers can share any TCP connection
  http.createServer((req, res) => {
    res.writeHead(200);
    res.end('Hello, World!\n');
  }).listen(8000);

  console.log(`Worker ${process.pid} started`);
}
```

### Modules
```javascript
// math.js
function add(a, b) {
  return a + b;
}

module.exports = { add };

// app.js
const math = require('./math');
console.log(math.add(2, 3));
```

## Tips & Best Practices
- **Use Asynchronous Methods**: Prefer asynchronous methods to avoid blocking the event loop.
- **Error Handling**: Implement proper error handling to make your application robust.
- **Modular Code**: Organize your code into modules for better maintainability.
- **Security**: Follow security best practices to protect your application.
- **Testing**: Write tests to ensure your code works as expected.

## External Resources
- [Node.js Official Documentation](https://nodejs.org/en/docs/)
- [Node.js Best Practices](https://github.com/goldbergyoni/nodebestpractices)
- [Awesome Node.js](https://github.com/sindresorhus/awesome-nodejs)
- [Node.js Design Patterns](https://www.nodejsdesignpatterns.com/)