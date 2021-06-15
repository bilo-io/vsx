# 2. ES6, TypeScript & Node

> A guide to frontend development with Visual Studio Code.
>
> - Back to the [README](../../README.md)
> - Try out the [Assessment](./guides/CryptoCharts.md)
> - Also check out [Appendices](./appendix/CodingStandards.md)

- [1. Setup Environment](./1-SetupEnvironment.md)
- `2. ES6, Typescript & NodeJS`
- [3. React](./3-React.md)
- [4. Redux](./4-Redux.md)
- [5. Styling](./5-Styling.md)
- [6. Storybook](./6-Storybook.md)
- [7. Testing](./7-Testing.md)

<img
style="width: 256px"
width="256"
src="https://s3.amazonaws.com/clarityfm-production/attachments/6604/default/es6.png?1442839695"
/>

## ES6 (Javascript)

Javascript is an implementation of ECMA script, which received many new updates since ES6.

Reference: [full list of ES6 language updates](https://github.com/lukehoban/es6features)

### Fundamentals

You should know the following fundamentals to be an effective JS developer.

- `window`, `navigator`
- `var`, `const`, `let`
- `classes` and Arrow functions (e.g `() => {}`)
- Double `==` vs Triple `===`
- Spread operator `...`
- Destructuring
- Array functions:
  - `forEach`
  - `map`,
  - `reduce`, `filter`, `find`,`some`,`every`
  - `findIndex`
  - `10_000` notation for numbers
  - `promises` and `async` / `await`

- `async` & `await`
- `Promises`

## Typescript

Microsoft created a superset of Javascript, which adds static type checking to the language, making it more predictable and thus safer to code.

> A similar alternative is [FlowType](https://flow.org/)

- [Typescript Language Guide](https://www.typescriptlang.org/)
- [Typescript React Cheat Sheet](https://github.com/typescript-cheatsheets/react)

And some online Code Sandboxes for Typescript and React:

- [Typescript Lang.org](https://www.typescriptlang.org/play?#code/JYWwDg9gTgLgBAKjgQwM5wEoFNkGN4BmUEIcA5FDvmQNwCwAUKJLHAN5wCuqWAyjMhhYANFx4BRAgSz44AXzhES5Snhi1GjLAA8W8XBAB2qeAGEInQ0KjjtycABsscALxwAFAEpXAPnaM4OANjeABtA0sYUR4Yc0iAXVcxPgEhdwAGT3oGAOTJaXx3L19-BkDAgBMIXE4QLCsAOhhgGCckgAMATQsgh2BcAGssCrgAEjYIqwVmutR27MC5LM0yuEoYTihDD1zAgB4K4AA3H13yvbAfbs5e-qGRiYspuBmsVD2Aekuz-YAjThgMCMcCMpj6gxcbGKLj8MTiVnck3gAGo4ABGTxyU6rcrlMF3OB1H5wT7-QFGbG4z6HE65ZYMOSMIA)
- [CodeSandbox](https://codesandbox.io/s/react-ts?utm_source=dotnew)
- [Stackblitz](https://stackblitz.com/edit/react-typescript-base)

## NodeJS

[NodeJS](https://nodejs.org/en/) is a Javascript runtime that runs without the browser.
As such, you won't have access to browser specific things like `window`, etc.

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
