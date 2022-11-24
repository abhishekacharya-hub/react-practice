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

__what is virtual dom__

in React, for every DOM object, there is a corresponding "virtual DOM object". A virtual DOM object is a representation of a DOM object, like a lightweight copy. A virtual DOM object has the same properties as a real DOM object, but it lacks the real thing's power to directly change what's on the screen.

Manipulating DOM is slow, but manipulating Virtual DOM is fast as nothing gets drawn on the screen. So each time there is a change in the state of our application, virtual DOM gets updated first instead of the real DOM.


__what is react component__

Components are the building blocks of any React app and a typical React app will have many of these. Simply put, a component is a JavaScript class or function that optionally accepts inputs i.e. properties(props) and returns a React element that describes how a section of the UI (User Interface) should appear.

In React, a Stateful Component is a component that holds some state. A Stateless component, by contrast, has no state. Note that both types of components can use props.


__stateless component__

```javascript
import React from "react";

const ExampleComponent = (props) => {
  return <h1>stateless component - {props.message}</h1>;
};

const App = () => {
  const message = "react interview question";
  return (
    <>
      <ExampleComponent message={message} />
    </>
  );
};
export default App;
```

The above example shows a stateless component named ExampleComponent which is inserted in the <App/> component. The ExampleComponent just comprises of a <h1> element. Although the Stateless component has no state, it still receives data via props from a parent component.


__statefull component__

```javascript
import React, { useState } from "react";

const ExampleComponent = (props) => {
  const [email, setEmail] = useState(props.defaultEmail);

  const changeEmailHandler = (e) => {
    setEmail(e.target.value);
  };

  return <input type="text" value={email} onChange={changeEmailHandler} />;
};

const App = () => {
  const defaultEmail = "suniti.mukhopadhyay@gmail.com";
  return (
    <div>
      <ExampleComponent defaultEmail={defaultEmail} />
    </div>
  );
};

export default App;

```

The above example shows a stateful component named ExampleComponent which is inserted in the <App/> component. The ExampleComponent contains a <input>. First of all, in the ExampleComponent, we need to assign defaultEmail by props to a local state by a useState() hook in ExampleComponent.

Next, we have to pass email to value property of a input tag and pass a function changeEmailHandler to an onChange() event for a purpose keeping track of the current value of the input.

