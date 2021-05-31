1. Difference from real DOM vs Virtual DOM
  - Real DOM 
    - updates slow
    - directly updates HTML
    - creates new DOM if element updates
    - DOM manipulation is very expensive
    - too much memory waste
  - virtual DOM
    - updates faster
    - doesn't directly update HTML
    - updates the jsx if element updates
    - DOM manipulation is very easy

2. what is react 
  - front-end JAvaScript library library developed by Facebook in 2011
  - follows the component based approach which helps building UI components
  - used for developing complex and interactive web and mobile UI
  - open sourced only in 2015

3. Major features of React
  - uses virtual DOM
  - server-side rendering
  - follows uni-directional data flow or data binding
    - pass state down to components
  
4. Major advantages of react
  - increase application performance
  - can be used on client and server side
  - JSX code increases readability
  - easy to integrate with other frameworks

5. React Limitations
  - React is just a library, not a full blown framework
  - very large library, take a while to understand
  - difficult for novice programmer to understand
  - coding gets complex when it uses inline templating and JSX

6. What is JSX? 
  - shorthand for JavaScript XML
  - use JS along with HTML
  - ``` 
    render(){
      return(
        <div>
          <h1>
            Hello, Wold!
          </h1>
        </div>
      )
    }
    ```

7. What do you understand about Virtual DOM?
  - virtual DOM is a lightwieght JavaScript object which is originally just the copy of the real DOM. It is a node tree that lists the elements, their attributes and content as Objects and their proporties. React's render function creates a node tree out of the React Components. It hten updates this tree in response to the mutatinos in the data model which is caused by various actions done by the user or by the system.
    - Whenever an underlying data changes the entire UI is re-rendering in Virtual DOM representation.
    - Then the difference between the previous DOM representation and the new one is calculated.
    - Once the calculations are done, the real DOM will be updated with only the things that have actually changed. 

8. Why can't browsers read JSX>
  - Browsers can only read JavaScript objects but JSX is not a regular JavaScript object. Thus to enable a browser to read JSX, first, we need to transform JSX file into a JavaScript object using JSX transformers like Babel and the pass it to the browser.

9. How different is React's ES6 syntax when compared to ES5?
  - require v import
    - ```
      // ES5
      var React = require('react')

      // ES6
      import React from 'react'
    ```
  - export v exports
    - ```
      // ES5 
      module.exports = Component

      // ES6
      export default Component
    ```
  - component and function
    - ```
    // ES5
    var MyComponent = React.createClass({
      render: function() {
        return({
          <h3>Hello, World</h3>
        })
      }
    })

    // ES6
    class MyComponent extends React.Component {
      render() {
        return(
          <h3>Hello, World</h3>
        )
      }
    }
    ```
  - props
    - ```
    // ES5
    var App = React.createClass({
      propTypes: { name: React.PropTypes.string }
      render: function() {
        return(
          <h3>Hello, World</h3>
        )
      }
    })

    // ES6
    class App extends React.Component {
      render(){
        return(
          <h3>Hello, World</h3>
        )
      }
    }
    ```
  - state
    - ```
      // ES5
      var App = React.createClass({
        getInitialState: function() {
          return { name: 'world' };
        },
        render: function() {
          return (
            <h3>Hello, {this.state.name}!</h3>
          )
        }
      });

      // ES6
      class App extends React.Component {
        constructor() {
          super();
          this.state = { name: 'world' };
        }
        render() {
          return (
            <h3>Hello, {this.state.name}!</h3>
          )
        }
      }
      ```
- 10. Difference between React and Angular
  - React
    - Architecture: Only the View of MVC
    - Rendering: Server-side
    - DOM: Uses virtual DOM
    - Data Biding: One-way data biding
    - Debugging: Compile time debugging
    - Author: Facebook
  - Angular
    - Architecture: Complete MVC
    - Rendering: Client-side
    - DOM: Uses real DOM
    - Data Binding: Two-way data binding
    - Debugging: Runtime debugging
    - Author: Google
- 11. Everthing is a component?
  - Componets are the building blocks of a React application's UI. These componets split up the entire UI into small indepenedent and reusable pieces. Then it renders each of these components independent of each other without affecting the rest of the UI
- 12. What is the purpose of render() in React
  - Each React component must have a render() mamdatorily. It returns a single React element which is the representation of the native DOM component. If more than one HTML element needs to be rendered, then they must be grouped together insed one enclosing tag such as <form>, <group>, <div> etc. This functionmust be kept pure i.e., it must return the same result each time it is invoked.
- 13. How can you embed two or more components into one?
  - ```
  class MyComponent extends React.Component{
    render(){
      return(          
        <div>
          <h1>Hello</h1>
          <Header/>
        </div>
      );
    }
  }
  class Header extends React.Component{
    render(){
        return (
        <h1>Header Component</h1
        )
    };
  }

  ReactDOM.render(
    <MyComponent/>, document.getElementById('content')
  );
  ```
- 14. What is Props? 
  - Props is the shorthand for Properties in React. They are read-only components which must be kept pure i.e. immutable. They are always passed down from the parent to the child componets through the appliaciton. A child component can never send a prop back to the parent component. This help in maintaining the unidirectional data flow and are generally used to render the dynamically generated data.
- 15. What is a state in React and how it is used
  - States are the source of data and must be kept as simple as possible. Basically, states are the objects which determine components rendering and behavior. They are mutable unlike the props and create dynamic and interactive components. They are accessed by this.state()
- 16. Difference between state and props
  - state
    - received initial value from parent component
    - set default values inside component
    - changes inside component
    - set initial value for child components
  - props
    - received initial value from parent component
    - parent component can change value
    - set default values inside component
    - set initial value for child components
    - changes inside chld component
- 17. How can you update state of a component
  - ```
    class MyComponent extends React.Component {
      constructor() {
        super();
        this.state = {
          name: 'Maxx',
          id: '101'
        }
      }
      render()
        {
          setTimeout(()=>{this.setState({name:'Jaeha', id:'222'})},2000)
          return (
            <div>
              <h1>Hello {this.state.name}</h1>
              <h2>Your Id is {this.state.id}</h2>
            </div>
          );
        }
    }

  ReactDOM.render(
    <MyComponent/>, document.getElementById('content')
  );
  ```
- 18. What is arrow funciton in React? How is it used?
  - Arrow functions are more of breif syntax for wrting the function expression. They are also called 'fat-arrow' (=>) the function. These functions allow to bind the context of components properly since in ES6 auto binding is not available by default. Arrow function are mostly useful while working with the higher order functions.
  - ```
  // General way
  render() {
    return(
      <MyInput onChange={this.handleChange.bind(this) }>
    )
  }
  // With Arrow Function
  render() {
    return(
      <MyInput onChange={ (e) => this.handleOnChange(e) }>
    )
  }
  ```
- 19. Differentiate between stateful and stateless components
  - stateful
    - Stores info about component's state change in memory
    - Have authority to change state
    - Containes teh knowledge of past, current, and possible futher changes in state
    - Stateless components notify them about the requirement of the state change, then they send down the props to them
  - Stateless
    - Calculates the internal state of the components
    - Do not have the authority to change state
    - Contains no knowledge of past current and possible state changes
    - They recieve the props from the Statefule components and treat them as callback functions
- 20. What are the different phases of React component's lifecycle?
  - There are three different phases of React component's lifecycle
    - i. Initial Rendering Phases: This is the phase when the component is about to start its life journey and make its way to the DOM
    - ii. Updating Phase: Once the component gets added to the DOM, it can potentially update and re-render only when a prop or state change occurs. That happens only in this phase
    - iii. Unmounting Phase: This is the final phase of a component's life cycle in which the component is destryoyed and removed from the DOM.

React Interview Questions

- 21. explian the lifecycle methods of React components in detail
  - componentWillMount(): Executed just before rending takes place both on client and server side
  - componentDidMount(): Executed on client side only after the first render
  - componentWillReceiveProps() - Invoked as soon as the props are received from the parent class and before another render is called
  - shouldComponentUpdate(): Returns true or false value based on certain conditions. If you watn your component to update, return true else return false. By default it returns false
  - componentWillUpdate(): Called just before rendering takes place in the Dom
  - componentDidUpdate(): Called immediately after renderin takes place
  - componentWillUnmount(): Called after the component is unmounted from the DOM. It s used to clear up the memory spaces.
- 22. What is an event in React? 
  - In React, events are the triggered reactions to specific actions like mouse hover, mouse click, key press, etc. Handling these events are similar to handling events in DOM element. But there are some synthatical differences like:
    - Events are named using camel case instead of just using the lowercase
    - Events are passed as functions instead of strings
  - The event arguments contain a set of properties which are specific to an event. Each event type contains its own properties and behavior which can be accessed via its event handler only.
- 23. How do you create an event in React
  - ```
    class Display extends React.Component({
      show(evt) {
        // code
      },
      render(){
        return(
          <div onClick={this.show}>Click Me!</div>
        )
      }
    })
    ```
- 24. What are sythetic events in React
  - Sythetic events are the objects
