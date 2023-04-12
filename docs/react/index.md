---
layout: home
title: React
has_children: true
---

# React

<https://github.com/sudheerj/reactjs-interview-questions>

## Key concepts

- **Components**: React is a component-based library, which means that applications are made up of reusable, self-contained components. Components can be composed together to create more complex UIs.
- **Virtual DOM**: React uses a virtual DOM, which is an in-memory representation of the actual DOM. This allows React to update the UI efficiently by minimizing the number of DOM manipulations.
- **JSX**: React uses JSX, which is a syntax extension that allows developers to write HTML-like code in JavaScript. This makes it easy to create and compose components.
- **Props**: Components can accept inputs called props, which are passed down from parent components. Props are read-only and cannot be modified by the component that receives them.
- **State**: Components can have internal state, which allows them to keep track of data that changes over time. State is mutable and can be modified by the component that owns it.
- **Lifecycle Methods**: Components have lifecycle methods that are called at specific points during the component's lifespan. This allows developers to run code when a component is mounted, updated, or unmounted.
- **Hooks**: Hooks are a feature introduced in React 16.8 that allow developers to use state and other React features without writing class components. Hooks can be used to manage state, run effects, and create custom hooks.
- **Context**: Context is a feature that allows data to be passed down through a component tree without having to pass props down manually at every level. This can be useful for sharing data that is used by many components.
- **Redux**: Redux is a popular state management library that can be used with React. It provides a centralized store that holds the state of an application and allows components to subscribe to changes.
- **Server-side Rendering**: React can be used for server-side rendering, which means that the initial HTML is generated on the server and sent to the client. This can improve the performance and SEO of a web application.

## Angular vs React

| |**Angular**|**React**|
|:----|:----|:----|
|Author|Google|Facebook|
|Architecture|Complete MVC|View layer of MVC|
|DOM|Real DOM|Virtual DOM|
|Data-Binding|Bi-directional|Uni-directional|
|Rendering|Client-Side|Server-Side|
|Performance|Comparatively slow|Faster due to Virtual DOM|


## useState

The useState() is a built-in React Hook that allows you for having state variables in functional components. It should be used when the DOM has something that is dynamically manipulating/controlling.

```typescript
...
const [count, setCounter] = useState(0);
const [otherStuffs, setOtherStuffs] = useState(...);
...
const setCount = () => {
   setCounter(count + 1);
   setOtherStuffs(...);
   ...
};
```

## Functional vs Class components

Before the introduction of Hooks in React, functional components were called stateless components and were behind class components on a feature basis. After the introduction of Hooks, functional components are equivalent to class components.

Although functional components are the new trend, the react team insists on keeping class components in React. Therefore, it is important to know how these components differ.


## Redux

Redux is an open-source, JavaScript library used to manage the application state. React uses Redux to build the user interface. It is a predictable state container for JavaScript applications and is used for the entire application’s state management.

- *Store*: Holds the state of the application.
- *Action*: The source information for the store.
- *Reducer*: Specifies how the application's state changes in response to actions sent to the store.

## Flux

Flux is the application architecture that Facebook uses for building web applications.

It is a method of handling complex data inside a client-side application and manages how data flows in a React application.

- There is a single source of data (the store) and triggering certain actions is the only way way to update them.The actions call the dispatcher, and then the store is triggered and updated with their own data accordingly.
- When a dispatch has been triggered, and the store updates, it will emit a change event that the views can rerender accordingly.

## Redux vs Flux

|**SN**|**Redux**|**Flux**|
|:----|:----|:----|
|1.|Redux is an open-source JavaScript library used to manage application State|Flux is an architecture and not a framework or library|
|2.|Store’s state is immutable|Store’s state is mutable|
|3.|Can only have a single-store|Can have multiple stores|
|4.|Uses the concept of reducer|Uses the concept of the dispatcher|

## Webpack

Webpack is a popular open-source JavaScript module bundler.
