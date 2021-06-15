# 4. Redux

> A guide to frontend development with Visual Studio Code.
>
> - Back to the [README](../../README.md)
> - Check out the [Guides](./guides/CryptoCharts.md)
> - Also check out [Appendices](./appendix/CodingStandards.md)

- [1. Environment](./1-Environment.md)
- [2. ES6, Typescript & NodeJS](./2-Javascript.md)
- [3. React](./3-React.md)
- `4. Redux`
- [5. Styling](./5-Styling.md)
- [6. Storybook](./6-Storybook.md)
- [7. Testing](./7-Testing.md)
- [8. Git](./8-Git.md)
- [9. Webpack](./9-Webpack.md)
- [10. Development](./10-Development.md)

<img
style="height: 10rem; width: auto"
src="https://cdn.iconscout.com/icon/free/png-256/redux-283024.png"
/>

## Overview

[Redux]() is a predictable state container for JavaScript apps.

It helps you write applications that behave consistently, run in different environments (client, server, and native), and are easy to test. On top of that, it provides a great developer experience, such as live code editing combined with a time traveling debugger.

You can use Redux together with React, or with any other view library. It is tiny (2kB, including dependencies), but has a large ecosystem of addons available.

![redux-architecture](./../assets/img/redux-architecture.svg)

## Integration With React

- [Provider](https://react-redux.js.org/api/provider)

> The `<Provider>` component makes the Redux store available to any nested components that need to access the Redux store.
>
> Since any React component in a React Redux app can be connected to the store, most applications will render a `<Provider>` at the top level, with the entire app’s component tree inside of it.
>
> The Hooks and connect APIs can then access the provided store instance via React's Context mechanism.
>
> - Reducers
> - Actions

### Redux files

Ideally for Redux, each resource should have its own loading and error states, rather than having a shared one for the reducer.

To make the store avaiable to the entire application, wrap it at the top level similar to:

```jsx
const store = createStore(rootReducer)

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
)
```

> And an example of the `slice` with Redux Toolkit would be something like:

```js
const initialState = {
    [groupName]: {
        // ...
        [resourceA]: {
            loading: true,  // for loading indicator
            error: null,    // stores error message, status, stack, etc.
            data: []        // successful data retrieval
        },
        // ...
        [resourceX]: {
            loading: true,
            error: null,
            data: []
        },
        // ...
    }
}
```

## Redux DevTools

[Download Redux DevTools Extension](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd?hl=en) for your browser to make debugging easier.

![redux-devtools](https://adamfolwarczny.com/img/github/redux-devtools-app-demo.png)

## Redux Toolkit

### Motivation

The Redux Toolkit package is intended to be the standard way to write Redux logic. It was originally created to help address three common concerns about Redux:

- "Configuring a Redux store is too complicated"
- "I have to add a lot of packages to get Redux to do anything useful"
- "Redux requires too much boilerplate code"

### Installation

```sh
yarn add redux react-redux @reduxjs/toolkit
```

### What's in the box

Redux Toolkit includes these APIs:

|Function|Info|
|:-|:-|
|`configureStore`:| wraps createStore to provide simplified configuration options and good defaults. It can automatically combine your slice reducers, adds whatever Redux middleware you supply, includes redux-thunk by default, and enables use of the Redux DevTools Extension.|
|`createReducer`:| that lets you supply a lookup table of action types to case reducer functions, rather than writing switch statements. In addition, it automatically uses the immer library to let you write simpler immutable updates with normal mutative code, like state.todos[3].completed = true.|
|`createAction`:| generates an action creator function for the given action type string. The function itself has toString() defined, so that it can be used in place of the type constant.|
|`createSlice`:| accepts an object of reducer functions, a slice name, and an initial state value, and automatically generates a slice reducer with corresponding action creators and action types.|
|`createAsyncThunk`:| accepts an action type string and a function that returns a promise, and generates a thunk that dispatches pending/fulfilled/rejected action types based on that promise.|
|`createEntityAdapter`:| generates a set of reusable reducers and selectors to manage normalized data in the store|
|`createSelector`| utility from the Reselect library, re-exported for ease of use.|

### Getting Started

> If you want a more comprehensive guide to understand redux toolkit, see here

- [Redux Toolkit Quick Start](https://redux-toolkit.js.org/tutorials/quick-start)
- [Redux Toolkit with Typescript](https://redux-toolkit.js.org/usage/usage-with-typescript)

> NOTE: Redux Toolkit is already written in TypeScript, so its TS type definitions are built in... so you won't have to `yarn add @types/@redux/toolkit` or anything like that

```jsx
import { createSlice } from '@reduxjs/toolkit';

export const slice = createSlice({
  name: 'counter',
  initialState: {
    value: 0,
  },
  reducers: {
    increment: state => {
      // Redux Toolkit allows us to write "mutating" logic in reducers. It
      // doesn't actually mutate the state because it uses the immer library,
      // which detects changes to a "draft state" and produces a brand new
      // immutable state based off those changes
      state.value += 1;
    },
    decrement: state => {
      state.value -= 1;
    },
    incrementByAmount: (state, action) => {
      state.value += action.payload;
    },
  },
});

export const { increment, decrement, incrementByAmount } = slice.actions;
```

### References

- [Redux Toolkit](https://redux-toolkit.js.org/)

<br />
<br />
<hr />
<br />
<br />

[Next Part: 5. Styling](./5-Styling.md)

<br />
<br />