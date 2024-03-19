**\*\***\*\*\***\*\*** Chapter 2\***\*\*\*\*\***\*\***\*\*\*\*\***

// Overview on React

A]] Components - these are encapsulated units of functionality, that serve as core fundamental units of react. They're javascript function or classes that receive properties as inputs and maintain their own internal state.

B]] React libraries - React applications run using React libraries. The React library(react) is supported by the react-dom and react-native libraries.

C]] Third-party libraries - React doesn’t enforce opinions on you with regard to data modeling, HTTP calls, specific areas of styling such as look and feel, or other aspects of your application

## React components

> . Components are the fundamental unit of a client-side application written in React.

> . When building an application first and foremost understand the application data

Composition and parent-child relationships

> . React components are organized like tree structures (as DOM elements) and can be nested, and contain other components.

> . Components can be used in flexible ways, because they are self-contained, they tend to be composable.

> . Composable components are often easily moved around and can be reused to create other components. Portability is often a feature of well-designed React components.

> . Due to this composability, components can be used in many places throughout the application - hence forming a parent-child relationship.

> . If a component contains another component, it’s said to be the parent. A component within another component is said to be a child. While components existing within the same level don't share any sort of direct relationship.

Establishing Component Relationship

// Guidelines for breaking UI into components

A]] Ensure that components are grouped together in a way that makes sense; components should be organized around related functionality. Watch out to ensure you're not creating a rigid hierarchy if your components are untenable to move around

B]] If an interface element is being repeated multiple times, then that's a good candidate for becoming a component.

C]] You dont have to get everything right the first time - hence iteration is part of the process. Initial planning provides a direction strategy.

## Creating React Elements

// A react Element is a light, stateless, immutable primitive in React. There are two types, that is; ReactComponentElement and ReactDOMElement. ReactDOMElements are virtual representation of DOM elements. ReactComponentElement reference either a function or class corresponding to a React application.

> . Elements are the descriptors e use to tell React what we want to see on the screen and are a central concept in React

> . What does it mean that React element to be a virtual rep of a DOM element - This means that React elements are to React what DOM elements are to the DOM—the basic primitives that compose a UI.

> . React element utilize a familiar mental model structure to work with - that is the DOM tree structure of elements, which helps visualize some similarities between React element and DOM elements.

> . Another way is that React elements is a set of basic instructions for React to use, like a blueprint for the DOM element. React elements are what React DOM will utilize to update the DOM.

// React elements are what React uses to create a virtual DOM that React DOM will manage and use to reconcile and update the actual DOM. They are simple blueprints for React to use in creating and managing elements.

// Syntaxes

## Signature of ReactDOM.render

ReactDOM.render (
ReactElement element,
DOMElement container,
[function callback]
) -> ReactComponent

## Signature of .createElement

React.createElement(
String/ReactClass type,
[object props],
[children...]
) -> React element

//React.createElement takes a string or component (either a class extending React.Component or a function), a props object, and children and returns a React element.

// React.createElement asks;
1] what am I creating?
2] How should I configure it?
3] What does it contain?

## Breakdown

A]] type - You can pass in either a string that is the tag name of the HTML element to be created ("div", "span", "a", and so on) or a React class,

B]] p - properties. The props object provides a way of specifying which attributes will be defined on the HTML element (if in the context of a React- DOMElement) or will be available to a component class instance.

C]] children- this is where composability comes in play - Using children..., the arguments passed after type and props let you nest, order, and even further nest other React elements.

// How React turns your many React .createElements into what you see on the screen.

> . React used ReactElements you provide to create a virtual DOM that React DOM can use as it manages the browserDOM.

// React will recursively evaluate a series of React elements to determine how it should form a virtual DOM tree structure for your components.

// It will also check for more React elements in children... to evaluate. React will go through every possible path, like a child asking, “What is X?” until they know everything.

## Summary REACT Elements

// Characteristics of React Elements

a]] React elements take a string to create a type of DOM element(div, a, p, etc.)

b]] You provide configuration the REACT element via a props object; these are analogous to attributes DOM elements can have; example// (<img src="aURL" />)

c]] React elements are nestable and you can provide other React elements as the children of an element

d]/ React Elements are what components are made from in React

e]] React uses React Elements to create a virtual DOM that React DOM can use as it updates the browserDOM

**\*\***\*\***\*\*** Grouping React Elements

> . To group React elements you can use components as they serve as bundles and can be group based of functionality, markup, styles and related bits on your application's UI.

> . They also act as a boundary containing other components - hence components can be independent, reusable pieces which allows you to work on each in isolation.

> . You are able to create two primary types of components using functions and JS classes;

    A]] stateless functional components
    B]] stateful React components - created from js classes

// Creating React classes

> . React components are like React elements but with more features.

> . Components in React are classes that help group together REact elements and functionality.

> . These components can be created as classes that extend the React.component base class or function

## Example

create MyReactClassComponent extends Component {
render() {}
}

> . Rather than invoke a specific method from the React library- React.createElement,; creating a components from React.Component involves declaring a Javascript class that inherits fromm the React.component abstract base class.

## Ways of Creating components as React classes

]] The render method

> . The render method needs to return exactly one React element. In this way, the render method is similar to how React elements are created—they can be nested but at the topmost level there’s a single node.

> . However unlike ReactElements, the render methods of React classes have access to embedded data and component methods and additional methods inherited from React.component abstract base class.

> . This means that React will create and keep track of special data object for an instance of a React class that stays around over time and can be updated through special React functions.

// Note: React will create a backing instance in memory for components created as React component classes.

// React elements are mirrors of the DOM and components are ways to group them together.

// The backing instance is a way of providing data storage and access for a specific component. The data stored in the instance will be made available to the component’s render method through specific API methods.

// This means that you get access to data
that you can change and that will persist over time

> . When using a React class to create a component, you also have access to props—data that you can pass to your component and that it can in turn pass to child components.

}} Property Validation via PropTypes

> .React class components are free to use custom properties.

> . But with this feature- you need to provide some sort of way to validate which properties you'll be using so as to prevent bugs and plan the data your components will use.

> . One way of getting by this is using validators available from a namespace within React: PropTypes

// The prop-types library provides a set of validators that lets you specify what your components needs or expects; Analogy: think of PropTypes as a sort of contract that can be fulfilled or broken by other developers or your future self.

## Benefit of PropTypes

A]] Benefit Using PropTypes is not a strict protocol but rather helps in bug prevention and ease of debugging.

B]] Allows you to when you specify what props you expect first, to get a chance to think through which of your components will need to work.

> . When using PropTypes you have to add the propTypes property to the React.component class via a static class property or simple property assignment after the class definition

## The life and times of a Component

> . Components made from React classes have backing instances that let you store data and need to have render methods that returns exactly one React Element.

// Hence, React will take React elements and create an in-memory virtual DOM from them, and it will handle managing and updating the DOM.

> . React classes can have some special methods that will be called in a certain order as

> . React manages the virtual DOM. render, which you’ve used to return React elements, is just one of those methods.

> . Additionally apart from reserved lifecycle methods, React gives you the freedom and functionality to add desired functionality.

// React classes and React elements are used by React to create
an in-memory virtual DOM that manages the real DOM. It also creates a “synthetic” event system so that you can still react to events from the browser (such as clicks, scrolls, and other user-caused events).

## React state of mind

> . Along with custom methods and lifecycle methods, React classes also gives you state (data) that can persist with the component(backing instance).

So what is state in light terms???

State is information about something at a given time.

// In React state exists either as mutable or immutable.

// Note: Components created as JS classes that extend React.Component may have both mutable and immutable state, whereas components created from functions(stateless functional components) only have access to immutable state(props).

// You can't directly mutate "this.props" as it stems from immutable state. - Props are intended to be immutable, meaning they are passed down from parent to child components and should not be directly modified within the child component. This promotes predictable behavior and prevents unintended side effects.

// In React components, this.state holds the component's internal state that can be updated to trigger re-renders.

// State and props are vehicles for the data that make up your app and make it useful.

// In React props and state are the primary ways that you can utilize dynamic or static data in your UI (showing user information, passing data to event handlers, and so forth).

// Example:
A]] If you’re creating a social network application (and you will in future chapters), you’ll often use a combination of props and state to build components that display and update user information, updates, and more.

B]] If you’re using React for data visualization, you might use props and state as inputs for visualization libraries like D3.js.

## Summary Data types in React

A]] Mutable

B]] Immutable

// setting initial state

When to use state??? - when you want to make changes to data stored within a component

// Note: In React, data that tends to need to be mutable often comes from or is the result of user input (often text, files, toggled options, and so on), but could be many other
things.

> > To keep track of user interactions with form elements, you need to provide an initial state and then change that state over time.

// To update state within a React class component, you’ll use this.setState; look at the basic usage. It takes an updater
function to use for updating state and doesn’t return anything:

// One key difference between updating or reassigning a value in JavaScript and using setState is that React can choose to batch updates based on state changes to maximize efficiency. This means that when you call setState to perform a state update, it won’t necessarily happen right away. This is React's way of being efficient.

How do events work in React??

> . Javascript is event-driven;

// React implements a synthetic event system as a part of the virtual DOM that will translate events in the browser into events for your React application.

// One difference is that React event handlers are set up on React elements or components themselves (as opposed to using addEventListener). You can update the state of your component using the data from these events (text from an input, a radio button value, or even the target of the event).

############################ Part B ######################

## JSX

// Benefits of JSX and differences from HTML

A]] Similarity to HTML and simpler syntax—If writing React.createElement repeatedly felt tedious or if you found the nesting hard to follow, you’re not alone.

> . JSX’s similarity to HTML makes declaring your component’s structure in a familiar way much easier and dramatically improves readability.

B]] Declarative and encapsulated - By including the code that will make up your view alongside any related methods, you create a group of functionality. Essentially everything you need to know about the component is in one place. Nothing is unnecessarily hidden from you, which means you can reason about your components more easily and be more fully aware of how it works as a system.

// JSX differences from HTML or XML

A]] HTML tags versus React components—Custom React components you created using React.createClass are by convention capitalized so you can determine the difference between custom and native HTML components.

B]] Attribute expressions—When you want to use a JavaScript expression as an attribute value, wrap the expression in a pair of curly braces (<Comment a={this.props.b}/>) instead of quotes (<User a=”this.props.b”/>)

C]] Boolean attributes - omitting the value of an attribute (<Plan active />, <Input checked />)causes JSX to treat it as true. To pass a false value, you have to use an attribute expression (attribute={false})

D]] Nested Expressions - to insert the value of an expression inside an element, you also use a pair of curly braces (<p>{this.props.content}</p>)

## Summary

A]] There two main types of elements that we work with to create components in React. These are REACT ELEMENTS and REACT CLASSES.

== REACT ELEMENTS - these are "what you want to see on the screen" and are comparable to DOM elements

== REACT CLASSES - These are Javascript classes that inherit from the React.component class - these are typically the components. They are created from classes - extending React.component or functions - stateless functional components.

B]] React classes get access to state that can change over time - mutable state - but all react elements get access to props that should be modified (immutable state).

C]] React classes have special methods called lifecycle methods that will be called by REACT in a particular order during the rendering and update process - This makes your components more predictable to work with and allows you to easily hook into the component update process.

D]] React classes can have custom methods defined on them to perform tasks such as mutating state.

E]] React components communicate via props and have child-parent relationships. Parent components can pass data to children, but children can't modify parents. They can pass data back to parents via callbacks - but don't have direct access to parents.

F]] JSX is an XML-like extension of Javascript that lets you write components in a easier and familiar way.

## Project Link

Project; Letters Social component
Links:
https://codesandbox.io/p/devbox/rnwvwt?file=%2Fsrc%2Findex.js%3A47%2C12

https://codesandbox.io/p/devbox/rnwvwt?file=%2Findex.html%3A2%2C59
