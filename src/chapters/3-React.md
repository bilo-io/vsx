# 3. React

> A guide to frontend development with Visual Studio Code.
>
> - Back to the [README](../../README.md)
> - Check out the [Guides](./guides/CryptoCharts.md)
> - Also check out [Appendices](./appendix/CodingStandards.md)

- [1. Environment](./1-Environment.md)
- [2. ES6, Typescript & NodeJS](./2-Javascript.md)
- `3. React`
- [4. Redux](./4-Redux.md)
- [5. Styling](./5-Styling.md)
- [6. Storybook](./6-Storybook.md)
- [7. Testing](./7-Testing.md)
- [8. Git](./8-Git.md)
- [9. Webpack](./9-Webpack.md)

<img
style="height: 10rem; width: auto"
src="https://cdn.iconscout.com/icon/free/png-256/react-226053.png"
/>

## Overview

React is a library responsible for the view layer of a web application. It can be combined with various other libraries to create a fully-fledged web application.
> NOTE:
>
> - [Why use React?](https://www.peerbits.com/blog/reasons-to-choose-reactjs-for-your-web-development-project.html)
> - In contrast to a library, a framework such as [Angular](https://angular.io/) is self-contained and opinionated. This means there is less thinking required on how to accomplish certain things in favour of ways which are predefined by the framework.

A basic React component for a navigation bar could look like this, using `JSX` syntax:

```jsx
import React from 'react'

const NavBar = (props) => {
    const navItems = [
        {
            name: 'Home',
            path: '/'
        },
        {
            name: 'About',
            path: '/about'
        }
    ]

    return (
        <div>
        {
            navItems.map((item) => (
                <div onClick={props.goTo(item.path)}>
                  {item.name}
                </div>
            ))
        }
        </div>
    )
}
```

And this would be the usage of a component, where you pass in a custom prop, a function to navigate around the app using browser `history`:

```jsx
const App = () => {
    return (
        <div className="app-container">
          <Navbar goTo={(path) => history.push(path)}>
          {/*... the rest of the App */}
        </div>
    )
}
```

## Get Started

- [Create React App](https://create-react-app.dev/docs/getting-started/)
- [Code Sandbox](https://codesandbox.io/s/react-ts?utm_source=dotnew)
- [Custom webpack config](https://www.freecodecamp.org/news/learn-webpack-for-react-a36d4cac5060/)

## Core Principles

While you should have covered the [Main Concepts](https://reactjs.org/docs/hello-world.html) section of the official React docs, you should definitely make sure to understand and embrace the following sub sections:

- [Components and Props](https://reactjs.org/docs/components-and-props.html)
- [State and Lifecycle](https://reactjs.org/docs/state-and-lifecycle.html)
- [Handling Events](https://reactjs.org/docs/handling-events.html)
- [Lifting State Up](https://reactjs.org/docs/lifting-state-up.html)
- [Composition vs Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html)
- [Thinking in React](https://reactjs.org/docs/thinking-in-react.html)

> The `Advanced Guides` are also important to be aware of, should you encounter a problem covered therein.

## Lifecycle Hooks

Go over the [React Hooks API Reference](https://reactjs.org/docs/hooks-reference.html) to understand how to manage state and lifecycle in function components.

Also make understand how these hooks work:

- must know: `useState`, `useEffect`, `useContext`, `useRef`
- secondary: `useLayoutEffect`, `useReducer`, `useMemo`, `useCallback`
