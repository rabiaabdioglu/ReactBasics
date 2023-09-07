- [React Basics](#react-basics)
  - [React Fundamentals](#react-fundamentals)
    - [Creating Your First Component](#creating-your-first-component)
    - [JSX and Basic Component Structure](#jsx-and-basic-component-structure)
    - [Using Components Inside Components](#using-components-inside-components)
  - [Props and State Usage](#props-and-state-usage)
    - [Communicating Data with Props](#communicating-data-with-props)
    - [Managing and Updating State](#managing-and-updating-state)
    - [Event Handling and State Management](#event-handling-and-state-management)
  - [Event Handling and Dynamic Content](#event-handling-and-dynamic-content)
  - [Lifecycle and useEffect Hook](#lifecycle-and-useeffect-hook)

## React Basics

#### React Fundamentals
###### Creating Your First Component
###### In React, a component is the building block of a user interface.
###### It's a reusable piece of UI that can be composed together to create complex applications. Let's start by creating a simple component:

```javascript
// App.js
import React from 'react';

function App() {
  return (
    <div>
      <h1>Hello, World!</h1>
    </div>
  );
}

export default App;

```




###### JSX and basic component structure


```javascript

// Using expressions within JSX
import React from 'react';

function Greeting() {
  const name = 'John';
  return <h2>Hello, {name}!</h2>;
}

export default Greeting;

```

###### Using Components Inside Components
###### One of the key advantages of React is its component composition.
###### You can create small, reusable components and use them within other components. This enhances code organization and reusability

```javascript
// Using components inside components
import React from 'react';

function UserInfo() {
  return (
    <div>
      <Greeting />
      <p>This component uses another component inside it.</p>
    </div>
  );
}

function Greeting() {
  const name = 'Alice';
  return <h2>Hello, {name}!</h2>;
}

export default UserInfo;

```


#### Props and State Usage
###### "In React, props and state are essential concepts for building dynamic and interactive user interfaces. Props are used to pass data from a parent component to its child component, while state is used to manage data that can change over time within a component."

###### Communicating data with Props

###### Props (short for properties) allow you to pass data from a parent component to its child components. 
###### This enables components to communicate and share information

```javascript

import React from 'react';

function Greeting(props) {
  return <h2>Hello, {props.name}!</h2>;
}

function App() {
  return (
    <div>
      <Greeting name="Alice" />
      <Greeting name="Bob" />
    </div>
  );
}

export default App;

```

###### Managing and Updating State
###### State is a way to manage data that can change within a component. 
###### To use state, we need to convert a functional component into a class component or use React's useState hook. 
```javascript
import React, { Component } from 'react';

class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0,
    };
  }

  incrementCount = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.incrementCount}>Increment</button>
      </div>
    );
  }
}

export default Counter;

```
###### Event Handling and State Management
###### React components can respond to user interactions through event handling. Event handlers are functions that are triggered when specific events occur, such as clicking a button
```javascript
import React, { Component } from 'react';

class ToggleButton extends Component {
  constructor(props) {
    super(props);
    this.state = {
      isToggled: false,
    };
  }

  toggleState = () => {
    this.setState({ isToggled: !this.state.isToggled });
  };

  render() {
    return (
      <div>
        <button onClick={this.toggleState}>
          {this.state.isToggled ? 'ON' : 'OFF'}
        </button>
      </div>
    );
  }
}

export default ToggleButton;

```


#### Event Handling and Dynamic Content
###### Handling button clicks and events
###### In React, handling user interactions and events is crucial for building interactive UIs. Event handling in React is similar to handling events in HTML, but with a more declarative approach.
```javascript
import React, { Component } from 'react';

class ClickCounter extends Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0,
    };
  }

  handleButtonClick = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <p>Click count: {this.state.count}</p>
        <button onClick={this.handleButtonClick}>Click me</button>
      </div>
    );
  }
}

export default ClickCounter;

```


###### Dynamic content updates with State
###### State enables us to create dynamic and responsive UIs. By updating state, we trigger re-renders that reflect changes in the UI. 
```javascript
import React, { Component } from 'react';

class DynamicContent extends Component {
  constructor(props) {
    super(props);
    this.state = {
      message: 'Initial message',
    };
  }

  changeMessage = () => {
    this.setState({ message: 'Updated message' });
  };

  render() {
    return (
      <div>
        <p>{this.state.message}</p>
        <button onClick={this.changeMessage}>Change Message</button>
      </div>
    );
  }
}

export default DynamicContent;

```

#### Lifecycle and useEffect Hook
###### In class components, React provides a set of lifecycle methods that allow you to hook into different stages of a component's existence. With functional components, you can achieve similar functionality using the useEffect hook

```javascript
import React, { Component } from 'react';

class LifecycleExample extends Component {
  componentDidMount() {
    console.log('Component did mount');
  }

  componentDidUpdate() {
    console.log('Component did update');
  }

  componentWillUnmount() {
    console.log('Component will unmount');
  }

  render() {
    return <p>Component Lifecycle Example</p>;
  }
}

export default LifecycleExample;

```



