**JSX (JavaScript XML)** is a syntax extension for JavaScript used in React, allowing developers to write HTML-like code within JavaScript. It provides a more readable way to define UI components and their structure by combining HTML elements and JavaScript logic in a single file.

For example, instead of using `React.createElement` calls to create UI components, you can use JSX to define them more intuitively:

```jsx
const element = <h1>Hello, world!</h1>;
```

Under the hood, JSX is transformed into JavaScript functions (`React.createElement`) during compilation, making it both declarative and functional.


1. **Rules**
	1. JSX must return a **single parent element**
	2. JSX must be  **properly closed**
	3. Attributes are written using the **camelCase**(eg: helloWorld)
	4. 