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

The above example shows a stateless component named ExampleComponent which is inserted in the App/ component. The ExampleComponent just comprises of a h1 element. Although the Stateless component has no state, it still receives data via props from a parent component.


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

The above example shows a stateful component named ExampleComponent which is inserted in the App/ component. The ExampleComponent contains a input. First of all, in the ExampleComponent, we need to assign defaultEmail by props to a local state by a useState() hook in ExampleComponent.

Next, we have to pass email to value property of a input tag and pass a function changeEmailHandler to an onChange() event for a purpose keeping track of the current value of the input.



__What is the difference between Component and Container in React?__

The presentational components are concerned with the look, container components are concerned with making things work.

For example, this is a presentational component. It gets data from its props, and just focuses on showing an element

```javascript
/**
 * Presentational Component
 * 
 **/
const Users = props => (
  <ul>
    {props.users.map(user => (
      <li>{user}</li>
    ))}
  </ul>
)
```

On the other hand this is a container component. It manages and stores its own data, and uses the presentational component to display it.

```javascript
/**
 * Container Component
 * 
 **/
class UsersContainer extends React.Component {
  constructor() {
    this.state = {
      users: []
    }
  }

  componentDidMount() {
    axios.get('/users').then(users =>
      this.setState({ users: users }))
    )
  }

  render() {
    return <Users users={this.state.users} />
  }
}
```

__how to import and export in react?__

```javascript
//importing combination
import React, {component} from 'react';
import ReactDOM from 'react-dom';

//wrapping component with braces if no dafault exports 
import {Button} from './Button';

//default export (recommended)
import Button from './Button';


class DangerButton extends Component {
  render() 
  {
    return <Button color = "red"/>
  }
}
export default DangerButton;
//or export DangerButtion
```

__diffrence between component and element__

1. __react Element__

it is a simple object that describes a DOM node and its attributes or properties. It is an immutable description object and you can not apply any methods on it.

```javascript
const element = <h1>React Element Example!</h1>;
ReactDOM.render(element, document.getElementById('app'));
```

2. __react Component__

It is a function or class that accepts an input and returns a React element. It has to keep references to its DOM nodes and to the instances of the child components.

```javascript
function Message() {
  return <h1>React Component Example</h1>
}
ReactDOM.render(</Message>, document.getElementById("app")
```

__What are functional components in react?__

A React functional component is a simple JavaScript function that accepts props and returns a React element. It also referred as stateless components as it simply accept data and display them in some form.

After the introduction of React Hooks, writing functional components has become the ​standard way of writing React components in modern applications.