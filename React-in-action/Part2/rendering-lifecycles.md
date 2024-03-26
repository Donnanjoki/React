###### CHAPTER 4 - RENDERING AND LIFECYCLE METHODS IN REACT #######

   # Source: React-In-Action


Letters Social Repo

// Features;
     1] Creating posts that have text
     2] Adding locations to posts with Mapbox
     3] Liking and commenting on posts
     4] Providing OAuth authentication via GitHub and Firebase
     5] Displaying posts in a newsfeed
     6] Using basic pagination


## Render Process and Lifecycle Methods

Lifecycle Methods - these are special methods that are attached to class-based React components that will be executed at specific points in a component's lifecycle.

>. Lifecycle methods aren't unique to REact only and are present in many UI technologies.
>. The main parts of a React's component's life are mounting, updating and unmounting.

// Types of Lifecycle Methods


>. Lifecycle methods can be broken into two main groups; That is
    A] Will methods - called right before something happens
    B] Did methods - called right after something happens

>.Components have four main parts of their lifecycle methods;
    A] Initialization - when a component class is being instantiated
    B] Mounting - A component is being inserted into the DOM
    C] Updating - A component is being updated with new data via state or props
    D] Unmounting - A component is being removed from the DOM

    // The three main parts of a component’s life are when it’s mounting, mounted, and unmounting. A component is mounting when it’s being inserted into the DOM, mounted once it is, and unmounting when it’s being removed.


## Initial and will methods

// defaultProps - A static property that provides the default props for a component. Sets on " this.props " if that prop is not set by the parent component, it is accessed before any components are mounted and can't rely on "this.props" or "this.state".

// state(initial) - The value of this property in the constructor will be the initial value set for the state of your component. That's  especially helpful when you need to provide placeholder content, or set default values. It is similar to default props with the exception that the data is expected to be mutated and only available on components that inherit from React.Component.



## Mounting Components

>. This is the process of React inserting a component into the DOM. (Recap::: components only exist in the virtual DOM until React creates them in the real DOM)

>. Mounting methods will let you "hook" into the beginning and the end of a component's life and are only fired once because, by definition, there can only be one beginning and end to a component.


// Mounting is the process of React inserting your components into the REal DOM. Once done your component is "ready", and then its a good time to perform tasks like HTTP calls or read cookies; additionally you will be able to access the DOM elements via ref

>. Before a component is mounted, you only have one opportunity to change state - you can use "component WillMount", which will provide the opportunity to set state or perform other actions before a component mounts.

>. t’s important to know which methods trigger a rerender and which don’t so
you can understand how your app will behave as well as debug it if something goes
wrong.

>. Mounting : Mounting and unmounting are controlled externally by ReactDOM (a component can’t unmount itself without the help of ReactDOM), but it can control
whether or not an update to the component should occur via shouldComponentUpdate.

// ComponentDidMount method -   In this method, you have access to component state and props as well as the knowledge that your component is ready for updates. That means it’s a good place to do things like update your component state with data coming back from a network request. 
>. It’s also a great place to work with third-party libraries that depend on the DOM, like jQuery and others

## Updating Methods

>. React provides several methods to hook into the update process: "shouldComponentUpdate", "componentWillUpdate" and "componentDidUpdate"

>. A difference between "update methods and mounting methods is that they provide arguments for props and state. You are able to utilize these to determine whether an update should occur or to react to changes.

>. Unless specified otherwise, shouldComponentUpdate will always return "true", but
if you’re careful to always treat state as immutable and to read only from props and
state in render(), then you can override shouldComponentUpdate with an implementation that compares the old props and state to their replacements. 

>. That can be useful for performance tuning but should be treated as an escape hatch. React already employs sophisticated and advanced methods to determine what should be updated and when. If you do end up using shouldComponentUpdate, it should be in a case where those methods aren’t sufficient for some reason.

// Recap: Updating lifecycle methods. When a component is being updated, several hooks fire that let you determine whether the component should be updated at all, how to update, and when the update is done.

// Recall: React is recursive in how it forms a tree and renders things as it will exhaustively examine every part of your components by asking about each component and all its children. 

>. Note when an update occurs, child components receive props because the prop of that child has been changed by the parent via "this.setState()" - then on updating methods run in order; shouldComponentUpdate, componentsWillUpdate, componentDidUpdate - if for some reason the component is told not to update by returning false from shouldComponentUpdate, those steps would be skipped. 

## Unmounting Methods

>. React DOM is responsible for mounting and unmounting components. Mounting is the process of inserting your components into the DOM and unmounting is the opposite: the process of removing your components from the DOM. Once components are unmounted, they no longer exist in the DOM.

>. Unmounting is the process of removing a component from the DOM. If your application is written all with React, a router will remove components as you move between different pages. 

>. Additionally, you can take advantage of "componentWillUnmount" to do any cleanup you need to when a component is being removed. 

// Recall: Mounting and unmounting are controlled externally by ReactDOM (a component can’t unmount itself without the help of ReactDOM), but it can control
whether or not an update to the component should occur via shouldComponentUpdate.

// While a component is mounted, it “lives” in the actual DOM and
can be updated by React to keep it in sync with your data. 

// Unmounted, component only exists in virtual DOM.

// 

## Catching Errors

>. React's " error boundaries" - if an uncaught exception is thrown within a component's constructor render or lifecycle methods, React will unmount the component and its children from the DOM, this enables the errors to be isolated in components to avoid breaking the rest of the app.

>. You can also handle these errors by using another method that your components inherit from "React.Component: componentDidCatch , the semantics of this is similar' to Javascript's try...catch

>. ComponentDidCatch gives you access to the error being thrown and an error message. 














































## SUMMARY 

