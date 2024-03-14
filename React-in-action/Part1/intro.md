\***\*\*\*\*\***\*\*\*\***\*\*\*\*\*** REACT INTRO **\*\*\*\***\*\*\*\***\*\*\*\***

RESOURCE: React in Action // Book

// SUMMARY PREVIEW

> . A library for creating UIs initially built and open-sourced by facebook//meta.

> . Key goals: provide simplicity, better performance and utilizes components to attain this.

> . Components are the fundamental unit of React. Additionally React implements a virtual DOM that sits between your program and the browserDOM - this virtual DOM allows for efficient updates to the DOM using a fast diffing algorithm.

> > React has an expressive mental model, drawing from core cs software engineering techniques. This model draws broadly from both functional and object-oriented programming concepts.

> > React allows you to create user interfaces from components.Components maintain their own state, are written in and work with “vanilla” JavaScript, and inherit a number of helpful APIs from React. Most React apps are written for browser-based environments, but can also be used in native
> > environments like iOS and Android.

// Major features within the react ecosystem include //

A]] Components - Encapsulated units of functionality which serve as react primary building units. These utilize data (properties and state) to render your UI as output.

B]] React Libraries - React uses a set of core libraries - the core React library works with the react-dom and react-native libraries and is focused on component specification and definition.
Furthermore it lets you build a tree of components that a renderer for the browser or another platform can use.

    >> case example is react-dom which is aimed at browser env and server-side rendering.
    >> React native libraries focus on native platforms and lets you create React applications for iOs, Android and other platforms.

## The Virtual DOM

> > A major theme in React is a drive to simplify complex tasks and abstract unnecessary complexity from the developer.

> > One of the ways it does this is by encouraging a declarative approach rather than an imperative approach. -

> . Hence you get to declare how your components should look and behave under different states and React's internal machinery handles the complexity of managing updates, updating the UI to reflect the changes and so on

> One of the major driving technology is the virtual DOM - A virtual DOM is a data structure or a collection of data structures that mimics or mirrors the DOM that exists in the browsers.

> . This DOM will serve as an intermediate layer between the application code and the browserDOM.

> . The virtual DOM allows the complexity of change detection and management to be hidden from the developer and moved to a specialized layer of abstraction.

> . By using react's virtual DOM we are able to handle painpoints such as change detection in updating a UI in an a optimal way.

> . Another key consideration is performance - React's design and implementation of a virtual DOM helps address this though its should be noted that it's designed to be fast enough.

> . A robust API, simple mental model and l=things like cross-browser compatibility end up being important outcomes of React's virtual DOM than an extreme focus on performance.

// Virtual DOM --- Need for speed?

> .React is performant by design - performance is a key feature but its secondary to simplicity.

> . The virtual DOM is part of what enables you to defer thinking about complicated state logic and focus on other, more important parts of your application.

> . The conclusion is that your focus shouldn't be in thinking extensively of how the virtual DOM accomplishes your data updates and changes but rather focusing on your project. - that's the simplicity part of REACT: you’re freed up to focus on the parts of your application that need the most focus.

## The DOM

> > . Document Object Model is a programming interface that allows Javascript programs to interact with different types of documents (HTML, XML, SVG).

> .The DOM provides a structured way of accessing, storing and manipulating different parts of a document.

> . At a high-level, the DOM is a tree structure that reflects the hierarchy of an XML document.

> . By using REact we don't have to directly interact with the DOM.

## Updates and Diffing

> > . DOM mutation done poorly can be expensive, so React tries to be efficient in its updates to your UI and employs methods similar to 3D games.

> . React’s diffing and update procedure. When a change happens, React determines differences between the actual and in-memory DOMs. Then it performs an efficient update to the browser’s DOM. This process is often referred to as a diff (“what changed?”) and patch (“update only what changed”) process.

// Diffing short for Differences Algorithm is used to differentiate the DOM Tree for efficient updates. React utilize diffing algorithm to identify the changes in the newly created virtual dom and previous version of dom after any changes are made.

// Assumption for Diffing Algorithm

React uses a heuristic algorithm called the Diffing algorithm for reconciliation based on these assumptions:

    Elements of different types will produce different trees
    We can set which elements are static and do not need to be checked.

## Components

> .Components are the most fundamental unit of React.

// components in general;

> . Using components as mental and visual tools when designing and building user inter-faces can lead to better, more intuitive application design and use.

> > Example: An example of an interface broken into components. Each distinct section can be thought of as a component. Items that repeat in a uniform nature can be thought of as one component that gets reused over different data

> . User interfaces often contain elements that are reused or repurposed in other parts of the interface. And even if they’re not reused, they’re at least distinct. These different elements, the distinct elements of an inter- face, can be thought of as components.

// components in React: Encapsulated and reusable

> . React components are encapsulated, reusable and composable - this characteristic helps enable a much simpler and elegant way of thinking about and building user interfaces.

> . Hence rather than have a bunch of unstructured code your application can be comprised of clear, concise groups of code.

> . When working with React components its important to ensure that organization and consistency as part of your component design.
> . These design components can either be self-contained and focus on a particular concern or a handful of related concerns.

> . This paves way for components that are portable, logically grouped and easy to move around and reuse throughout your application.

// Note: Even if it takes advantage of other libraries, a well-designed React component should be fairly self-contained.

> .By breaking your UI into components, you're able to work more easily on different part of the application.
> . Boundaries between components mean that functionality and organization can be well-defined, whereas self-contained components mean they can be reused and moved around more easily.

> .React components can additionally work together to form composite components - component composition is a powerful aspect of react which allows you to create a component once and make it available to the rest of your application for reuse. (a plus in large applications).

> .A final aspect of React components is lifecycle methods. These are predictable, well-defined methods you can use as your component moves through different parts of its lifecycle (mounting, updating, unmounting, and so on).

**\*\*\*\***\*\***\*\*\*\*** What does React not do? \***\*\*\*\*\***\*\*\***\*\*\*\*\***

> > By understanding what something can and can't do helps in determining tradeoffs, rather than basing those engineering decisions on opinions or absolutes.

// Worthwhile benefits

A]] Flexibility - Frameworks offer more opinion and standardization. React’s approach allows you to select only the tools that you need and to pick the best tools for your use-case.

B]] Testability - many of React's components are pure functions, hence automated testing doesn't require mocking or subbing - UI tests typically require a browser but REact allows the ability to run unit tests and memory via NOde. A single React components tested in isolation are reliable and deterministic because they are pure functions

C]] Performance - Though it's not the fastest its use of a virtual DOM helps it benchmark well - its able to save battery and CPU, and simplifies the programming model by rendering the screen when necessary. Great option for teams looking to minimize page load times and data use.

D]] Community Support - React has a large community backing with majority of developers using React backing the quality of their experience with the framework.

E]] Developer Experience - Because the React API isn’t very large, many developers don’t find it necessary to constantly reference documentation. React offers the option of declaring classes or functions for components, which in turn allows HTML to be housed within JavaScript.

> > This design is opposite to competitors like Angular or Ember, which require developers to learn a special syntax

F]] Corporate Investment - React is supported by a full-time staff of committed developers who blog regularly about the development process. They also offer codemods to simplify the process of keeping code up to date. When a new version is released, these codemods give developers the ability to run a command line that automatically updates their code base.

## Tradeoffs of React

// Downsides

A]] React trades being concise for being explicit. For example, two-way binding isn’t very common, so a change handler is required to keep things in sync. This results in more control, but also requires more code.

B]] React is JavaScript-centric, frameworks like Angular, View and Ember are more template-centric, which can be beneficial for teams who are new to JavaScript. React, on the other hand, requires a thorough knowledge of modern JavaScript.

C]] Because it's a library rather than a full framework, React requires more setup which can result in decision fatigue.

D]] React popularized the idea of a single component containing JavaScript and markup. This approach contrasts with the model view controller norm. While there are definite benefits to React’s approach, some may prefer separation.

> > Frameworks normally uses a separate template file. React encapsulates logic and markup into autonomous component depending on their functionality.

E]] React is corporate-backed hence Facebook's corporate backing can be a positive or negative depending on one's perspective - benefits include dedicated funding but the final decisions is still taken by facebook.

## React for teams

A]] React is a great tool for larger teams and larger applications due to the simplicity of using it.

B]] React provides powerful abstractions which helps focusing on essential tasks.

C]] React is a lightweight library in terms of both responsibility and functionality - meaning you're no required to focus on buy-ins to things like a more comprehensive API and can focus primarily on your application.

> > Unlike some Opinionated frameworks and libraries which take an all-or nothing adoption stance, React offers a "just the view" scope and general interoperability with Javascript - hence a declarative way of programming rather than imperative since its a declarative component-based library.

}} Sum of it all is React's simplicity, un-opinionated nature and performance make it it a great fit for small and large projects alike.
