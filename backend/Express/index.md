# Express

## Introduction
Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.

## Basic Syntax
```javascript
// Example of a basic Express server
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
    res.send('Hello, World!');
});

app.listen(port, () => {
    console.log(`Server is running on http://localhost:${port}`);
});
```

## Common Use Cases
- Building RESTful APIs
- Serving static files
- Middleware integration
- Real-time applications

## Advanced Features
- **Middleware**: Use middleware functions to handle requests.
- **Routing**: Define routes to handle different HTTP methods and paths.
- **Error Handling**: Implement error handling middleware.
- **Templating**: Use templating engines like Pug or EJS to render dynamic content.

## Code Snippets
### Using Middleware
```javascript
// Example of using middleware in Express
const express = require('express');
const app = express();
const port = 3000;

const myMiddleware = (req, res, next) => {
    console.log('Middleware executed');
    next();
};

app.use(myMiddleware);

app.get('/', (req, res) => {
    res.send('Hello, World!');
});

app.listen(port, () => {
    console.log(`Server is running on http://localhost:${port}`);
});
```

### Routing
```javascript
// Example of defining routes in Express
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
    res.send('Hello, World!');
});

app.post('/submit', (req, res) => {
    res.send('Form submitted');
});

app.listen(port, () => {
    console.log(`Server is running on http://localhost:${port}`);
});
```

### Error Handling
```javascript
// Example of error handling middleware in Express
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
    throw new Error('Something went wrong!');
});

// Error handling middleware
app.use((err, req, res, next) => {
    console.error(err.stack);
    res.status(500).send('Something broke!');
});

app.listen(port, () => {
    console.log(`Server is running on http://localhost:${port}`);
});
```

### Templating
```javascript
// Example of using a templating engine in Express
const express = require('express');
const app = express();
const port = 3000;

app.set('view engine', 'pug');

app.get('/', (req, res) => {
    res.render('index', { title: 'Hey', message: 'Hello there!' });
});

app.listen(port, () => {
    console.log(`Server is running on http://localhost:${port}`);
});
```

## Tips & Best Practices
- **Use Middleware**: Leverage middleware for logging, authentication, and error handling.
- **Modular Routes**: Organize routes into separate modules for better maintainability.
- **Security**: Use security best practices like helmet and rate limiting.
- **Error Handling**: Implement comprehensive error handling to manage different types of errors.
- **Testing**: Write tests for your routes and middleware to ensure reliability.

## External Resources
- [Express Official Documentation](https://expressjs.com/)
- [Express GitHub Repository](https://github.com/expressjs/express)
- [Awesome Express](https://github.com/expressjs/awesome-express)