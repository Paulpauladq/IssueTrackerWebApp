# ZiqiTang-Book

##Chapter 5
  

##Chapter 4
   In this chapter, what we want to do is to add components which can respond to the users' input and events.
  In React, we could implement that using state.
### Inital State
* The state of a component is captured in this.state variable using the form of key-value pair in the component’s class.
* In the first step, we just create the inital state variable and store it in this.state variable in the constructor of IssueTable class.
![chapter4_react_state](./images/chapter4_initial_state.png)

### Async State Initialization
* Normally, the initialization state will require to be fetched via API call instead of static setup in the constructor.
* In this step, we use asynchronized call in the componentDidMount() method to set up the state after the DOM is represented.
* We use the setState() callback function inside the asynchronized call to set the initial state. 
* Setting the state outside the constructor is to make sure that the state will be set after all the components are ready to be rendered(DOM is ready).
![chapter4_react_state](./images/chapter4_async_state_init.png)

###Updating State
* In this step, we need to append the content of the components
* To do this, we need make a copy of this.state first and use setState() to set up the appended array.

###Lifting State Up
* In this step, we need to refactor the code to separate the whole processes into their own components.
* We'll create the IssueList class and make it as the father component and make the IssueAdd and IssueTable as its children component.
* We put load data and add row method into the IssueList class.
* We pass the this.state and this.createIssue method down to the children class as props and the children class will render using these props.
* We need to bind the createIssue method to IssueList component since we need to call the function with this refering to IssueList class.
* The results remain the same.

###Event Handling
* We will and a form on the bottom of the table and set the onSubmit event handler for the button to add the content we input into the IssueTable.
* We will render using the document form and pass the text we input as props of the handling method.
* Inside the handleSubmit method, we need to handle the event and use createIssue method to add rows to the table.
* The bind for handleSubmit method is needed since the original object is the window.
![chapter4_react_state](./images/chapter4_event_handler.png)

## Chapter 3
### Issue Tracker
* add classes representing components of issue trackers

### React Classes
* the objective is to convert the single-line JSX into a simple React component instantiated
  from a React class, so that we can later use the full power of the first class React components.

![chapter3_helloworldReact](./images/chapter3_helloworldReact.png)

### Composing Components
* the UI can be split into smaller independent pieces so that each piece can be coded and reasoned in isolation, making it easier to build and understand a complex UI.
* A component takes inputs (called properties) and its output is the rendered UI of the component.

![chapter3_issuetracker_React](./images/chapter3_issuetracker_React.png)

### Passing Data

* Using properties: It should be possible to pass different input data from a parent component to a child component and make it render differently on different instances.

![chapter3_passing_using_children](./images/chapter3_passing_using_children.png)

* Using children: There is another way to pass data to other components, using the contents of the HTML-like node of the component. In the child component, this can be accessed using a special field of this.props called this. props.children.
              
              ![chapter3_passing_using_children](./images/chapter3_passing_using_children.png)
              
              ​    
### Dynamic Composition
* I replace our hard-coded set of IssueRow components with a programmatically generated set of components from an 
array of issues.


![chapter3_dynamic_components](./images/chapter3_dynamic_components.png)

### Summary 
  It was fun to write Web app using React. The component-based framework is
  very easy to use and we are able to manage the web UI gracefully using component classes. 

## Chapter 2
### Server-less Hello World
* simple piece of code in a single HTML file that uses React to
  display a simple page on the browser
* use React to create element and render
* can see the Hello World page through the broswer

![chapter2_helloworld](./images/chapter2_helloworld.png)

### JSX
* JSX stands for JavaScript XML
* Since browsers’ JavaScript engines don’t understand JSX，we have to transform JSX into regular JavaScript
based React.createElement() calls using Babel.

### Project setup
* nvm: Node Version Manager, that tool makes installation and switching
        between multiple versions of Node.js easy.
* Node.js: Node.js is JavaScript outside of a browser. The creators of Node.js just took Chrome’s V8
           JavaScript engine and made it run independently as a JavaScript runtime.
* Express: Express is a framework that simplifies the task of writing the server code.
           The Express framework lets you define routes, specifications of what to do when an HTTP request matching a 
           certain pattern arrives.        


### Separate Script File
* in order to make the code efficient.
* We move the transformation to the build stage in our development, so that
  we can deploy a ready-to-use distribution of the application.
  
### JSX Transform
* We create a new directory to keep all the JSX files, which will be transformed into plain JavaScript and
  into the public folder.
  
### Older Broswer Support
* use Babel to transform newer version of JavaScript to the older version.
* add an array for different continents.
* The screenshots after running are as below (for Chrome and Safari).

![Chapter2_chrome](./images/Chapter2_chrome.png)

![Chapter2_safari](./images/Chapter2_safari.png)

### Automated
* add customized commands in package.json to allow customized commands to be run

### Summary
  It was fun to get familiar with the tools like Express and Node.JS. The MERN stack is very
  convenient to use and easy to understand.