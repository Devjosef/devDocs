# React

## Introduction
React is a JavaScript library for building user interfaces, maintained by Facebook and a community of individual developers and companies. It allows developers to create large web applications that can update and render efficiently in response to data changes.

## Basic Syntax
```javascript
import React from 'react';
import ReactDOM from 'react-dom';

function App() {
    return (
        <div>
            <h1>Hello, World!</h1>
        </div>
    );
}

ReactDOM.render(<App />, document.getElementById('root'));
````


## Common Use Cases
- Building single-page applications (SPAs)
- Creating reusable UI components
- Managing application state
- Handling user input and events

## Advanced Features
- **Hooks**: Functions like `useState` and `useEffect` that let you use state and other React features without writing a class.
- **Context API**: A way to pass data through the component tree without having to pass props down manually at every level.
- **React Router**: A library for routing in React applications.
- **Redux**: A state management library often used with React.

## Code Snippets
### Functional Component with State
````javascript
import React, { useState } from 'react';

function Counter() {
    const [count, setCount] = useState(0);

    return (
        <div>
            <p>You clicked {count} times</p>
            <button onClick={() => setCount(count + 1)}>
                Click me
            </button>
        </div>
    );
}

export default Counter;
````


### Using useEffect Hook
````javascript
import React, { useState, useEffect } from 'react';

function DataFetcher() {
    const [data, setData] = useState(null);

    useEffect(() => {
        fetch('https://api.example.com/data')
            .then(response => response.json())
            .then(data => setData(data));
    }, []);

    return (
        <div>
            {data ? <pre>{JSON.stringify(data, null, 2)}</pre> : 'Loading...'}
        </div>
    );
}

export default DataFetcher;
````


### Context API
````javascript
import React, { createContext, useContext, useState } from 'react';

const MyContext = createContext();

function MyProvider({ children }) {
    const [value, setValue] = useState('Hello from context!');

    return (
        <MyContext.Provider value={value}>
            {children}
        </MyContext.Provider>
    );
}

function MyComponent() {
    const value = useContext(MyContext);
    return <div>{value}</div>;
}

function App() {
    return (
        <MyProvider>
            <MyComponent />
        </MyProvider>
    );
}

export default App;
````


## Tips & Best Practices
- **Component Reusability**: Create reusable components to avoid code duplication.
- **State Management**: Use hooks like `useState` and `useReducer` for managing state in functional components.
- **Performance Optimization**: Use `React.memo` and `useCallback` to optimize performance by preventing unnecessary re-renders.
- **Prop Types**: Use PropTypes or TypeScript to type-check your components' props.
- **Testing**: Write tests for your components using libraries like Jest and React Testing Library.

## External Resources
- [React Official Documentation](https://reactjs.org/docs/getting-started.html)
- [React Router Documentation](https://reactrouter.com/web/guides/quick-start)
- [Redux Documentation](https://redux.js.org/introduction/getting-started)
- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/)