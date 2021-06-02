# Coding Standards

Writing clean, maintainable and re-usable code is very important for large (and even small) software projects.
This section combines various sources to highlight important aspects we'd like to adhere to when writing code.

## React

### Best Practices

There are several core sections you should have covered in the [official React documentation](https://reactjs.org/docs/getting-started.html):
- [Thinking in React](https://reactjs.org/docs/thinking-in-react.html)
- [Composition vs Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html)
- [Lifting State Up](https://reactjs.org/docs/lifting-state-up.html)

### 1. Keep components small and function-specific

React makes it possible to have huge components that execute a number of tasks. But a better way to design components is to keep them small, so that one component corresponds to one function. 

Ideally, a single component should render a specific bit of your page or modify a particular behavior. There are many advantages to this:

- Function-specific components can be standalone, which makes testing and maintenance easier.
- Each small component can be reused across multiple projects.
- Components executing general functions can be made available to the community.
- With smaller components, it’s easier to implement performance optimizations.
- It’s easier to update smaller components.
- Bigger components have to perform harder and may be difficult to maintain.

### 2. Reusability is important, so keep creation of new components to the minimum required

By sticking to the rule of `one function = one component`, you can improve the reusability of components. What this means is that you should **skip** trying to build a new component for a function _if there already exists_ a component for that function.

- By reusing components across your project or across any number of projects, not only will you achieve consistency, you’ll also be contributing to the community.

- On the other hand, if any component becomes huge, unwieldy and difficult to maintain, it’s better to break it up into as many smaller components as required.

### 3. Consolidate duplicate code – DRY your code
A common rule for all code is to `keep it as brief and concise as possible.`

It’s no different here too, since React best practices also instruct you to keep code brief and precise. One way to do this is to avoid duplication – Don’t Repeat Yourself (DRY).

- You can achieve this by scrutinizing the code for patterns and similarities.
- If you find any, it’s possible you’re repeating code and there’s scope to eliminate duplication.
- Most likely, a bit of rewriting can make it more concise.

### 4. Use Function Declaration In Dull Areas

For people unfamiliar with your code, or React, name functions in dull areas. E.g. the `useEffect` hook when the component unmounts.

```diff
- DON'T
```
```jsx
React.useEffect(() => {
  setMounted(true)

  return () => {
    setMounted(false)
  }
}, [])
```

```diff
+ DO
```
```jsx
React.useEffect(() => {
  setMounted(true)

  return function unMount() {
    setMounted(false)
  }
}, [])
```

### 5. Use \</> over \<Fragment />
> It just reduces the code debt.

```diff
- DON'T
```
```jsx
const App = () => (
    <React.Fragment>
        <Navbar />
        <AppContent />
    </React.Fragment>
)
```

```diff
+ DO
```
```jsx
const App = () => (
    <>
        <Navbar />
        <AppContent />
    </>
)
```

### 6. Avoid the boolean Trap

When it comes to the primitive booleans to determine output value of something you have to be careful. Consider the `<Typraphy />` component takes these as text options: `'h1', 'h2', 'h3', 'h4', 'h5', 'h6', 'title', 'subheading'`. 

Knowing in which priority these would be applied by using booleans would not be certain, unless you look at the source code of the Typography component.


```diff
- DON'T
```
```jsx
<Typography color="primary" align="center" subheading title>
    Welcome to my bio
</Typography>
```

Rather specify one explicitly
```diff
+ DO
```
```jsx
<Typography color="primary" align="center" variant="title">
    Welcome to my bio
</Typography>
```

### 7. Componentize Duplicate Elements

This just means _"converting duplicate elements to their own reusable component"._ If you don't do this you're putting a burden on your teammates in the future, because they might be confused having to edit them, potentially causing frustration of having to update duplicate elements to accomplish a single change.

> E.g. imagine the scenario of a back button that is responsive showing the `'Back'` and a left arrow on desktop, vs only an arrow on mobile. If this button exists in more than one page it would be redundant to rewrite it for each use case. Even in the case that it might behave slightly differently in each use case, then you could just pass that behaviour down as a prop from the parent component.

e.g. 
```diff
- DON'T => reimplement existing code unnecessarily
```
```jsx
const onClick = // ... custom back button behaviour

const backButton = <button
    type="button"
    className="absolute lg:fixed mt-2 ml-6 text-2xl lg:mt-2 lg:-ml-4 lg:text-base left-0 top-0 lg:top-auto lg:left-auto z-40 text-header-text focus:outline-none font-bold"
    onClick={() => (onClick ? onClick() : history.goBack())}
>
    <span className="block lg:hidden">{backMessages.backButtonTextMobile}</span>
    <span className="hidden lg:block py-4">{backMessages.backButtonText}</span>
</button>
```
Aim to write less code. Imagine having an implementation like this for each instance of the back button ... and then the design changes... And you'd have to update each and every single implementation of this component. 

This is cleaner, and much more maintainable:

```diff
+ DO
```
```jsx
// default behaviour is () => history.goBack()
<BackButton />

// custom behavkour as 'onClick' prop
<BackButton onClick={() => window.location.reload() }/>
```
## Javascript / TypeScript

This section provides examples of recommended, clean code.

### 1. Evaluation conditions

Aim to write less code.

```diff
- DON'T
```
```jsx
const isValid = 
    variable !== a && 
    variable !== b && 
    variable !== c &&
    variable !== d;
```

This is cleaner:
```diff
+ DO
```
```jsx
const isValid = ![a,b,c,d].includes(variable)
```

### 2. Destructuring
Aim to write less code.

```diff
- DON'T
```
```jsx
const logUser = (user) => {
    sendMail('Hello', user.firstName, user.email);

    console.log(`
        FirstName: ${user.firstName}
        LastName: ${user.lastName}
        email: ${user.email}
    `)
}
```
This is cleaner:

```diff
+ DO
```
```jsx
const logUser = (user) => {
    const { firstName, lastName, email } = user;

    sendMail('Hello', firstName, email);

    console.log(`
        FirstName: ${firstName}
        LastName: ${lastName}
        email: ${email}
    `)
}
```

### 3. Callbacks
```diff
- DON'T: write out the callback and invocation if args are the same
```
```jsx
const Button = (
    <button onClick={() => customFuction()} />
)
```

```diff
+ DO: shorten the redudnant callback
```
```jsx
const Button = (
    <button onClick={customFuction} />
)
```

### Import order

Consider using a strucutred import order, such as:
```
React import
Library imports (Alphabetical order)
Absolute imports from project (Alphabetical order)
Relative imports (Alphabetical order)
import * as
import './<some file>.<some ext>'
```

For example:

```jsx
import React from 'react'
import { useSelector } from 'react-redux'
import styled from 'styled-components'
import FrogsGallery from './FrogsGallery'
import FrogsTable from './FrogsTable'
import Stations from './Stations'
import * as errorHelpers from '../utils/errorHelpers'
import * as utils from '../utils/'
```

## Redux

Ideally for Redux, each resource should have its own loading and error states, rather than having a shared one for the reducer.

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

## Styles

### 1. Mobile First

Always write your styles with Mobile first in mind.

> e.g. Here the item is `hidden` on mobile, and has `display: block` from screen size `md` updwards.
> This uses `Tailwind` described below.

```jsx
const Item = ({ children }) => (
    <div className="hidden md:block">
        // ...
    </div>
)
```

### 2. Tailwind

For the vast majority of styling we use [TailwindCSS](https://tailwindcss.com/), and prefer that over inline or custom styles. There is also a `tailwind.config.js` with custom overrides.

> NOTE: Only in _very_ few occassions do we allow custom styles/classes.

## References
- [Clean Code Javascript](https://github.com/ryanmcdermott/clean-code-javascript)
- [TailwindCSS](https://tailwindcss.com/)
- [Medium: "Thinking in React" - A paradox statement](https://medium.com/@nimelrian/thinking-in-react-a-paradox-statement-33c19e2eb9e2)
- [React Docs: Thinking in React](https://reactjs.org/docs/thinking-in-react.html)
- [React Docs: Composition vs Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html)
- [React Docs: Lifting State up](https://reactjs.org/docs/lifting-state-up.html)
- [15 React Best Practices you need to follow in 2021](https://www.codeinwp.com/blog/react-best-practices/)