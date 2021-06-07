# 2. ES6, TypeScript & Node

A guide to frontend development with Visual Studio Code.

- [1. Setup Environment](./1-SetupEnvironment.md)
- ES6, Typescript & NodeJS
- [3. React](./3-React.md)
- [4. Redux](./4-Redux.md)
- [5. Styling](./5-Styling.md)
- [6. Storybook](./6-Storybook.md)

## ES6 (Javascript)

Javascirpt is an implementation of ECMA script, which received many new updates since ES6.

Reference: [full list of ES6 language updates](https://github.com/lukehoban/es6features)

### Fundamentals

- `window`, `navigator`
- `var`, `const`, `let`
- `classes` and Arrow functions (e.g `() => {}`)
- Double `==` vs Triple `===`
- Spread operator `...`

- Destructuring

```diff
- const email = user.email
- const name = user.name

+ const { email, name } = user;
```

- Array functions:
  - `forEach`
  - `map`,
  - `reduce`, `filter`, `find`,`some`,`every`
  - `findIndex`
  - `10_000` notation for numbers
  - `promises` and `async` / `await`

## Typescript

Microsoft created a superset of Javascript, which adds static type checking to the language, making it more predictable and thus safer to code.

> A similar alternative is [FlowType]()

- [Typescript Language Guide](https://www.typescriptlang.org/)
- [Typescript React Cheat Sheet](https://github.com/typescript-cheatsheets/react)

And some online Code Sandboxes for Typescript and React:

- [Typescript Lang.org](https://www.typescriptlang.org/play?#code/JYWwDg9gTgLgBAKjgQwM5wEoFNkGN4BmUEIcA5FDvmQNwCwAUKJLHAN5wCuqWAyjMhhYANFx4BRAgSz44AXzhES5Snhi1GjLAA8W8XBAB2qeAGEInQ0KjjtycABsscALxwAFAEpXAPnaM4OANjeABtA0sYUR4Yc0iAXVcxPgEhdwAGT3oGAOTJaXx3L19-BkDAgBMIXE4QLCsAOhhgGCckgAMATQsgh2BcAGssCrgAEjYIqwVmutR27MC5LM0yuEoYTihDD1zAgB4K4AA3H13yvbAfbs5e-qGRiYspuBmsVD2Aekuz-YAjThgMCMcCMpj6gxcbGKLj8MTiVnck3gAGo4ABGTxyU6rcrlMF3OB1H5wT7-QFGbG4z6HE65ZYMOSMIA)
- [CodeSandbox](https://codesandbox.io/s/react-ts?utm_source=dotnew)
- [Stackblitz](https://stackblitz.com/edit/react-typescript-base)

## NodeJS

NodeJS is a Javascript runtime that runs without the browser. As such, you won't have access to browser specfiic things like `window`.

- npm / yarn
- node scripts
  - custom node script e.g to generate a `version.json` file
- package.json
  - `engines`
  - `resolutions`
  - `scripts`
  - `dependencies`
  - `devDependencies`
- lock files
  - resolving conflicts (just run `yarn`)

## Further Reading

- [Appendix: Coding Standards](./appendix/CodingStandards.md)