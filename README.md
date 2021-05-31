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
10. Difference between React and Angular
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
11. Everthing is a component?
  - Componets are the building blocks of a React application's UI. These componets split up the entire UI into small indepenedent and reusable pieces. Then it renders each of these components independent of each other without affecting the rest of the UI
12. What is the purpose of render() in React
  - Each React component must have a render() mamdatorily. It returns a single React element which is the representation of the native DOM component. If more than one HTML element needs to be rendered, then they must be grouped together insed one enclosing tag such as <form>, <group>, <div> etc. This functionmust be kept pure i.e., it must return the same result each time it is invoked.
13. How can you embed two or more components into one?
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
14. What is Props? 
  - Props is the shorthand for Properties in React. They are read-only components which must be kept pure i.e. immutable. They are always passed down from the parent to the child componets through the appliaciton. A child component can never send a prop back to the parent component. This help in maintaining the unidirectional data flow and are generally used to render the dynamically generated data.
15. What is a state in React and how it is used
  - States are the source of data and must be kept as simple as possible. Basically, states are the objects which determine components rendering and behavior. They are mutable unlike the props and create dynamic and interactive components. They are accessed by this.state()
16. Difference between state and props
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
17. How can you update state of a component
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
18. What is arrow funciton in React? How is it used?
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
19. Differentiate between stateful and stateless components
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
20. What are the different phases of React component's lifecycle?
  - There are three different phases of React component's lifecycle
    - i. Initial Rendering Phases: This is the phase when the component is about to start its life journey and make its way to the DOM
    - ii. Updating Phase: Once the component gets added to the DOM, it can potentially update and re-render only when a prop or state change occurs. That happens only in this phase
    - iii. Unmounting Phase: This is the final phase of a component's life cycle in which the component is destryoyed and removed from the DOM.

React Interview Questions

21. explian the lifecycle methods of React components in detail
  - componentWillMount(): Executed just before rending takes place both on client and server side
  - componentDidMount(): Executed on client side only after the first render
  - componentWillReceiveProps() - Invoked as soon as the props are received from the parent class and before another render is called
  - shouldComponentUpdate(): Returns true or false value based on certain conditions. If you watn your component to update, return true else return false. By default it returns false
  - componentWillUpdate(): Called just before rendering takes place in the Dom
  - componentDidUpdate(): Called immediately after renderin takes place
  - componentWillUnmount(): Called after the component is unmounted from the DOM. It s used to clear up the memory spaces.
22. What is an event in React? 
  - In React, events are the triggered reactions to specific actions like mouse hover, mouse click, key press, etc. Handling these events are similar to handling events in DOM element. But there are some synthatical differences like:
    - Events are named using camel case instead of just using the lowercase
    - Events are passed as functions instead of strings
  - The event arguments contain a set of properties which are specific to an event. Each event type contains its own properties and behavior which can be accessed via its event handler only.
23. How do you create an event in React
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
24. What are sythetic events in React
  - Sythetic events are the objects which act as a cross-browser wraper around the browser's native event. They combine the behavior of different browsers into one API. This is done to make sure the events show consistent properties across different browsers.
25. What do you understand by refs in React?
  - Refs is shorthand for References in React. It is an attribute which helps to store a reference to a particular React element or component, which will be returned by the components render configuartion function. It is used to return references to a particular element or component returned by render(). They come in handy when we need DOM measurements or to add methods to the components.
  - ```
    class ReferenceDemo extends React.Component{
      display() {
        cost name = this.inputDemo.value;
        document.getElementBId('disp').innerHTLM = name
      }
      render() {
        return(
          <div>
            Name: <input type='text' ref={input => this.inputDemo = input} />
            <button name='Click' onClick={this.display}>Click</button>
            <h2>Hello <span id='disp'></span> !!!</h2>
          </div>
        )
      }
    }
    ```
26. List some of the cases when you should use Refs
  - Follwing are the cases when refs should be used
    - When you need to manage focus, select text or media playback
    - To trigger imperative animations
    - Integrate which third-party DOM libraries
27. How do you modularize code React?
  - We can modularize code by using the export and import properties. They help in writing the componets separately in different files.
  - ```
    // ChildComponent.jsx
    export default class ChildComponent extends React.Component {
      render () {
        return( 
          <div>
            <h1>This is a child component</h1>
          </div>
        )
      }
    }

    // ParentComponent.jsx
    import ChildComponent from './childcomponent.js'
    class ParentComponent extends React.Component {
      render() {
        return(
          <div>
            <App />
          </div>
        )
      }
    }
    ```
28. How are forms created in React
  - Ract forms are similar to HTML forms. But in React, the state is contained in the state property of the component and is only updated via setState(). Thus the elements can't directly update their state and their submission is handled by a JavaScript function. This functin has full access to the data that is entered by the user into the form.
  - ```
    handleSubmit(event) {
      alert('A name was submitted: ' + this.state.value);
      event.preventDefault();
    }

    render() {
      return(
        <form onSubmit={this.handleSubmit}>
          <label>
            Name:
            <input type='text' value={this.state.value} onChange={this.handleSubmit} /> 
          </label>
          <input type="submit" value="Submit" />
        </form>
      )
    }
29. Difference between Controlled and Uncontrolled components
  - Controlled
    - They do not maintain their own state
    - Data is controlled by the parent component
    - They take in the current values through props and then notify the changes via callbacks
  - Uncontrolled
    - They maintain their own state
    - Data is controlled by the DOM
    - Refs are used to get their current values
30. What are Higher Order Components (HOC)?
  - Higher Order Componet is an advanced way of reusing the component logic. Basically, it's a pattern that is derived from React's compositional nature. HOC are custom components which wrap another component within it. They can accept any dynamically provided child component but they won't modify or copy any behavior from their input components. You can say that HOC are 'pure' componnents.
31. What can you do with HOC?
  - HOC can be used for many tasks like
    - Code reuse, logic and bootstrap abstraction
    - Render High jacking
    - State abstraction and manipulation
    - Props manipulation
32. What are Pure Components
  - Pure components are the simplest and fastest components which can be written. They can replace any component which only has a render(). These components enhance the simplicity of the code and performance of the application.
33. What is the significance of keys in React?
  - Keys are used for identifying unique Virtual DOM Elements with their corresponding data driving the UI. They help React to optimize the rendering by recycling all the existing elements in the DOM. These keys must be a unique number or string, using which React just reorders the elements instead of re-rendering them. This leads to increase in application's performance.

  React-Redux questions

34. What were the major problems with MVC framework
  - DOM manipulation was very expensive
  - Applications were slow and inefficient
  - There was huge memory wastage
  - Because of circular dependencies, a complicated model was created around models and views
35. Explain Flux
  - Flux is an architectural pattern which enforces the uni-directional data flow. It controls derived data and enables communication between mutiple components using a central Store which has authority for all data. Any update in data throughout the application must occur here only. Flux provides stability to the application and reduces run time errors
36. What is Redux?
  - Redux is one of the most trending libraries for front-end development in today's marketplace. It is a predictable state container for JavaScript applications and is used for the entire application's state management. Applications developed with Redux are easy to test and can run in different enviornments showing consistent behavior.
37. What are the three principles that Redux follows?
  - Single source of truth: The state of the entire application is stored in an object/state tree within a single store. The signle state tree makes it easier to keep track of changes over time and debug or inspect the application.
  - State is read-only: The only way to change the state is to trigger an action. An action is a plain JS object describing the change. Just like state is the minimal representation of data, the action is the minimal representation of the change to that data.
  - Changes are made with pure functions: In order to specify how to the state tree is transformed by actions, you need pure funcitons. Pure functions are those whose return value returns solely on the values fo their arguments.
38. What do you understand by "Single source of truth"?
  - Redux uses 'Store' for storing the application's entire state at one place. So all the component's state are stored in the store and they receive updates from the store itself. The single state tree makes it easier to keep track of changes over time and debug or inspect application.
39. List down the componets of Redux
  - Action: its an object that describes what happened
  - Reducer: It is a place to determine how the state will change
  - Store: state/object tree of the entire application is saved in the store
  - View: simplay displays the data provided by the store
40. Show how the data flows through redux
  - container -> actions -> reducers -> store -> provider component -> container
41. How are Actions defined in redux
  - Actions in React must have a type property that indicates the type of actions being performed. They must be defined as a string constant and you can add more properties to it as well. In Redux, actions are created using the functions called Action Creators. Below is an example of Action and Action creator:
  - ```
    function addTodo(text) {
      return {
        type: ADD_TODO.
        text
      }
    }
    ```
42. Explain the role of Reducer
  - Reducers are pure functions which specify how the application's state changes in response to an ACTION. Reducers work by taking in the previous state and action, and then it returns a new state. It determines what sort of update needs to be done based on the type of the action, and then returns new values. It returns teh previous state as it is, if no work needs to be done.
43. What is the significance of Store in Redux
  - A store is a JavaScript object which can hold the application's state and provide a few helper methods to access the state, dispatch actions and register listeners. The entire state/object tree of an applications is saved in a single store. As a result of this, Redux is very simple and predictable. We can pass middleware to the store to handle the proccessing of data as well as to keep a log of various actions that change the state of stores. All the actions return a new state via reducers.
44. How is redux different from Flux?
  - Flux
    - The store contains state and change logic
    - There are multiple stores
    - All the stores are disconnected and flat
    - Has singleton dispatcher
    - React components subscribe to the store
    - State is mutable
  - Redux
    - Store and change logic is separate
    - ther is only one store
    - single store with hierarchical reducers
    - no concept of dispatcher
    - container components utilize connect
    - state is immutable
45. What are the advantages of Redux
  - Predicatbility of outcome: Since there is always one source of truth, i.e. the store, there is no confusion about how to sync the current state with actions and otehr parts of the application
  - Maintainability: The code becomes easier to maintainwith a predictable outcome and strict structure
  - Server-side rendering: you just need to pass the store created on the server, to the client side. This is very helpful for initial render and provides a better user experience as it optimizes the application performance
  - Developer tools: From actions to state changes, developers can track everything going on in the application in real time
  - Community and ecosystem: Redux has a huge community behind is which makes it even more captivating to use. A large community of talented individuals contribute to the betterment of the library and develop various applications with in.
  - Ease of testing: Redux;s code is mostly functions which are small, pure and isolated. This makes the code testable and independent
  - Organization: Redux is precise about how code should be organized, this makes the code more consistent and easier when a team works with it.

React Router Questions
46. What is React Router
  - React Router is a powerfule routing library built on top of React, which helps in adding new screens and flows to the application. This keeps the URL in sync with data that's being displayed on the web page. It maintains a statdardized structure and behavior and is useed for developing single page web appliactions. React Router has a simple API
47. Why is switch keyword used in React Router v4?
  - Although a <div> is used to encapsulate multiple routes insed the Router. The 'switch' keyword is used when you want to display only a single route to be rendered amongst the several defined routes. The <switch> tag when in use matches the typed URL with the defined routes in sequential order. When the first match is found, it renders the specific route. Thereby bypassing the remaining routes.
48. Why do we need a router in react?
  - A Router is used to define multiple routes and when a user types a specific URL, if this URL matches the path of any 'route' defined inside the router, then the user is redirected to that particular route. So basically, we need to add a Router library to our app that allows creating multiple routes with each leading to us a unique view.
  - ```
    <switch>
      <route exact, path='/' component={Home}/>
      <route path='/posts/:id' component={Newpost}/>
      <route path='/posts' component={Post}/>
    </switch>
    ```
49. List advantages of React Router
  - i. Just like how React is based on components, in React Router v4, the API is 'All About Components'. A Router can be visualized as a single root component (<BroserRouter>) in which we enclose the specific child routers (<route>). 
  - ii. No need to manually set History value: In React Router v4, all we need to do is wrap our routes within the <BrowserRouter> component.
  - iii. The packages are split: There packages one each for Web, Native and Core. This supports the compact size of our application. It is easy to switch over based on a similar coding style.
50. How is React Router different from conventional routing?
  - Conventional Routing
    - Pages Involved: Each view corresponds to a new file
    - URL changes: A HTTP request is sent to a server and corresponding HTML page is recevied
    - FEEL: User actually navigates across different pages for each view
  - React Routing
    - Pages Involved: Only single HTML page is involved
    - URL changes: Only the history attribute is changed
    - Feel: User is duped thinking he is navigating across different pages


