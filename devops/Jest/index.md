# Jest

## Introduction
Jest is a delightful JavaScript testing framework with a focus on simplicity. It works with projects using Babel, TypeScript, Node.js, React, Angular, and Vue.js.

## Basic Syntax
```javascript
// Example of a basic Jest test
test('adds 1 + 2 to equal 3', () => {
    expect(1 + 2).toBe(3);
});
```

## Common Use Cases
- Unit testing
- Integration testing
- Snapshot testing
- Mocking and spying

## Advanced Features
- **Mock Functions**: Create mock functions to test code in isolation.
- **Snapshot Testing**: Capture and compare snapshots of your components.
- **Code Coverage**: Measure the code coverage of your tests.
- **Watch Mode**: Automatically run tests related to changed files.

## Code Snippets
### Mock Functions
```javascript
const myMock = jest.fn();
myMock.mockReturnValueOnce(10).mockReturnValueOnce('x').mockReturnValue(true);

console.log(myMock(), myMock(), myMock(), myMock()); // 10, 'x', true, true
```

### Snapshot Testing
```javascript
import React from 'react';
import renderer from 'react-test-renderer';
import MyComponent from './MyComponent';

test('renders correctly', () => {
    const tree = renderer.create(<MyComponent />).toJSON();
    expect(tree).toMatchSnapshot();
});
```

### Code Coverage
```bash
# Run tests with coverage
jest --coverage
```

### Watch Mode
```bash
# Run Jest in watch mode
jest --watch
```

## Tips & Best Practices
- **Isolate Tests**: Write tests that are independent and can run in isolation.
- **Use Descriptive Names**: Use descriptive names for your test cases to make them easy to understand.
- **Mock External Dependencies**: Mock external dependencies to avoid flaky tests.
- **Run Tests Frequently**: Run tests frequently to catch issues early.
- **Measure Coverage**: Use code coverage tools to ensure your tests cover all critical paths.

## External Resources
- [Jest Official Documentation](https://jestjs.io/docs/en/getting-started)
- [Jest GitHub Repository](https://github.com/facebook/jest)
- [Testing Library](https://testing-library.com/docs/react-testing-library/intro/)
- [Awesome Jest](https://github.com/jest-community/awesome-jest)