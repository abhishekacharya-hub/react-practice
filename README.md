# react-practice

__how react works ?__

React is a JavaScript library created for building fast and interactive user interfaces for web and mobile applications. It is an open-source, component-based, front-end library responsible only for the application view layer.

The main objective of ReactJS is to develop User Interfaces (UI) that improves the speed of the apps. It uses virtual DOM (JavaScript object), which improves the performance of the app. The JavaScript virtual DOM is faster than the regular DOM. We can use ReactJS on the client and server-side as well as with other frameworks. It uses component and data patterns that improve readability and helps to maintain larger apps.


__what is Destructuring in react ?__

Destructuring is a convenient way of accessing multiple properties stored in objects and arrays. It was introduced to JavaScript by ES6 and has provided developers with an increased amount of utility when accessing data properties in Objects or Arrays.

When used, destructuring does not modify an object or array but rather copies the desired items from those data structures into variables. These new variables can be accessed later on in a React component.

```javascript
import React from "react";

export default function App() {
  // Destructuring
  const [counter, setcounter] = React.useState(0);
  return (
    <>
      <button onClick={() => setcounter(counter + 1)}>Increment</button>
      <button onClick={() => setcounter(counter > 0 ? counter - 1 : 0)}>
        decrement
      </button>
      <h2>resul : {counter}</h2>
    </>
  );
}

```