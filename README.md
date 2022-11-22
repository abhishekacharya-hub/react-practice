# react-practice


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