\***\*\*\*\*\*\*\*** Data and data flow in React \***\*\*\*\*\***\*\*\*\*\***\*\*\*\*\***

> . Modern web applications are typically built as data-first applications - through this data a variety of ways to interact with other people over the web is created - and this done by mostly modifying and receiving data.

## What is state??

// This includes all the information a program has access to at a given instant in time. - in other words a snapshot of what you know about a program at an instant.

## Mutable and Immutable state

// In React you can represent data as either- state - that is data that can within a component and props(hence we can overwrite or update the data) - that is data a component receives that shouldn't change by the component.

A]] Immutable - An immutable, persistent data structure supports multiple versions over time but can’t be directly overwritten; immutable data structures are generally persistent

// Immutable or persistent data structures usually record a history and don’t change but rather make versions of what changed over time.

// Persistent data structures can keep track of changes over time. This is where the immutability of immutable data structures becomes clearer: only copies of state are made—they’re not replaced. - The old state is replaced by the new one, but the data isn’t replaced

B]] Mutable - A mutable, ephemeral data structure supports only a single version over time; mutable data structures are overwritten when they change and don’t support additional versions.

// Ephemeral data structures, on the other hand, usually don’t record history and get wiped out with each update.

// Ephemeral data structures only have the capacity to store a moment’s worth of data.

// There two main ways React components deal with data and communicate with each other;

A]] Component State
B]] Props

## State in React - Mutable state in React: Component State

What is React State???

> . React components can manage their own data using React's built-in state API.
> . This differs from the general concept of state in programming.
> . Only components inheriting from the React.Component class have access to this state API.

Accessing State???

> . State is accessed using this.state within a component
> . this refers to the current component instance
> . State is a special property managed by React to store data

Updating State

> . Unlike regular properties, directly assigning a new value to this.state won't update the UI.
> . React requires a specific way to update state to trigger a re-render of the component with the new data

Using state sparingly

> . Consider using stateless functional components or state management patterns (Redux, MobX) to minimize complexity and improve performance.

Updating state

> . Never directly modify this.state.
> . use the setState method to update state and trigger a re-render.
> . setState takes up an updater function - The updater function receives the current state and props as arguments.
> . Return a new state object from the updater function.
> . setState performs a shallow merge of the returned object with the current state.

setState vs Direct Modification

> . Avoid directly modifying this.state as it can lead to unexpected behavior and debugging issues.

> . setState ensures a predictable and controlled way to update state.

Benefits of using setState

A]] Simplifies component structure and logic
B]] Reduces boilerplate code for managing different states
C]] Promotes a declarative approach to UI development

## State in React - Immutable state in React: Props

// Props for Immutable Data: Props are the primary way to pass data between React components, promoting immutability.

// Prop Usage: Props can be accessed in constructors, render methods, and lifecycle methods of any component.

// Semi-Immutable Props: React's prop API is semi-immutable. It uses Object.freeze to prevent modifications, but technically props aren't truly immutable.

// Object.freeze - static method freezes an object. Freezing an object prevents extensions and makes existing properties non-writable and non-configurable. Freezing an object is the highest integrity level that JavaScript provides.

// Props as Data Source: Props can be passed from a parent component, set using a component's defaultProps, or even contain other React components.

// Unidirectional Data Flow: Props are meant to be consumed by components, not modified. You should treat them as read-only to avoid unexpected behavior.

/// State and Props Relationship: A component's state can be used as props for its children, enabling data flow from parent to child.

// One-way data-flow: Changes flow down the component hierarchy, not the other way around. A parent's state change can trigger prop updates for its children.

## Working with Props: PropTypes and default props

... PropTypes - prop-type packages
// Provides type checking for props during development.

// Specifies expected data types and structures for props.

// Not part of core React anymore, needs separate installation.

// Can be used for type checking in other libraries besides React.

... Setting PropTypes

// Defined as a static property propTypes on the component class.

// Uses functions and properties from the PropTypes object.

// Allows specifying prop types, shapes, and requirements (optional/mandatory).

.... Default Props

// Defined as a static property defaultProps on the component class.

// Provides default values for props in case they are not passed during usage.

// Ensures components have necessary data to function even if props are missing.

## Stateless functional components

> .Suitable for Prop-Driven Components: Ideal for components that rely solely on props and don't require state management.

> . Reduced Resource Usage: No backing instance needed by React, leading to potentially lower memory usage.

> . No State or Lifecycle Methods: Doesn't have access to React's state API or lifecycle methods.

> . Pure Functions: Can be written as named functions or anonymous expressions and are considered pure due to consistent output for given inputs.

> . Performance Benefits: React can potentially optimize by avoiding unnecessary checks and allocations due to their purity.

> . Powerful in Combination: Work well with parent components that manage state, promoting separation of concerns and potentially reducing state complexity.

> . Redux Example: Often used with Redux for centralized state management, leading to fewer stateful components overall.

## Component Communication

// Building with Subcomponents: React encourages building components from smaller, reusable subcomponents, promoting modularity and organization.

// Component Relationships: Components can represent "is-a" and "has-a" relationships, allowing you to think of them as parts of a whole or entities with internal components.

// Communication via Props: Unlike some frameworks, React uses props for component communication. Passing props involves:

    A]] Accessing data in the parent component (state or props)
    B]] Passing that data down to child components

// No Centralized Services: React avoids the use of framework-specific services for communication. Props provide a clear and direct way for components to share data.

## One-way data-flow

// Data binding is the process that establishes a connection between the application UI and the other data.

or

// Data binding usually refers to the process of setting up
a connection between data in your app and the view (the display of
that data).

// In practice, this is often manifested as something like a library or framework connecting app data like models (a user) to the user interface and keeps them in sync.

// Another way to think of React is as a projection - the UI is the data projected into a view and when the data changes so does the view change too.

// To be a proficient developer you need to understand how data flows and how different frameworks and libraries take different approaches to data flow.

// In react data flows in one direction - You can pass data through components but can’t reach out and modify the state or props of other components without passing props. You also can’t modify the data in a parent.

// But you can pass the data back up the hierarchy via callbacks - when a parent receives a callback from a child component - it can change its data and send the changed data back down to the child components.

// Even in this scenario with callbacks, data still
flows downwards in aggregate and remains determined by the parent passing that data down. That’s why we say that in React data flows unidirectionally.

// Data flows one way in React. Props are passed from parent to child (from owner to ownee), and children can’t edit the state or props of a parent component. Each component that has a backing instance can modify its own state but can’t modify anything outside itself apart from setting the props of one of its children.

// This unidirectional flow is helpful in building UIs as they make thinking of data flow become easier through an application.

**\*\***\***\*\*** Summary \***\*\*\*\*\***\*\*\***\*\*\*\*\***

A]] State is info available to a program at a given moment in time.
B]] Immutable state does't change but mutable state does
C]] Persistent/immutable data structures don't change but record their changes and make copies of themselves
D]] Ephemeral, mutable data structures are wiped out when they’re updated.
E]] React uses both mutable (local component state) and pseudo-immutable data (props).
F]] Props are pseudo-immutable and should not be modified once set.
G]] Component state is tracked by a backing instance and can be modified with setState.
H]] setState performs a shallow merge of data and updates your component’s state, preserving any top-level properties that aren’t overwritten
G]] Data flows one way in React, from parents to children. Children can yield back data to a parent via a callback, but they can’t directly modify the parent’s state, and a parent can’t directly modify a child’s state.

// Component interaction is done via props instead

## Why directly modifying state in React components is a bad practice

1]] React doesn't detect changes - When you directly modify this.state, React isn't notified of the change. It relies on the setState method to track state updates and trigger a re-render of the component with the new data. So, any changes you make directly won't be reflected in the UI.

2]] Inconsistent Behavior - Since React isn't aware of the direct modification, it might not update the state immediately. You might see the old state value for some time, leading to unexpected behavior and making debugging difficult.

3]] Lost Updates - If you perform multiple direct modifications in quick succession, React might only recognize the final state, effectively overwriting any intermediate changes you made. This can lead to data loss and incorrect rendering.

4]] Shallow Merge with setState -Even if you use setState after a direct modification, it might not work as intended. setState performs a shallow merge by default, meaning only the top-level properties of the state object are updated. If you have nested data within your state, directly modifying it won't be reflected through setState

# Recapp: It's essential to use the setState method to ensure controlled and predictable state updates that trigger re-renders and maintain data integrity.
