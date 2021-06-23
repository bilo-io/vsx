<img
style="height: 256px"
height="256"
src="https://cdn.iconscout.com/icon/free/png-256/css3-8-1175200.png"
/>

# 5. Styling

> A guide to frontend development with Visual Studio Code.
>
> - Back to the [README](../../README.md)
> - Check out the [Guides](./guides/CryptoCharts.md)
> - Also check out [Appendices](./appendix/CodingStandards.md)

- [1. Environment](./1-Environment.md)
- [2. ES6, Typescript & NodeJS](./2-Javascript.md)
- [3. React](./3-React.md)
- [4. Redux](./4-Redux.md)
- `5. Styling`
- [6. Storybook](./6-Storybook.md)
- [7. Testing](./7-Testing.md)
- [8. Git](./8-Git.md)
- [9. Webpack](./9-Webpack.md)
- [10. Development](./10-Development.md)

## 1. Sass

<img
style="height: 10rem; width: auto"
src="https://cdn.iconscout.com/icon/free/png-256/sass-2752078-2284895.png"
/>

[Sass](https://sass-lang.com/) (Syntactically Awesome Style Sheets) boasts more features and abilities than any other CSS extension language out there. It has been maintained by the Core team for over 14 years (as of 2021).

> NOTES:
>
> - sass files usually have the `.scss` extension
> - sass looks almost like regular css, but with additional (optional) syntax
> - another common alternative is `LESS`

## 2. Tailwind

<img
style="height: 10rem; width: auto"
src="https://seeklogo.com/images/T/tailwind-css-logo-5AD4175897-seeklogo.com.png"
/>


[TailwindCSS](https://tailwindcss.com/) is a utility-first CSS framework packed with classes like `flex`, `pt-4`, `text-center` and `rotate-90` that can be composed to build any design, directly in your markup.
For the vast majority of styling we use TailwindCSS, and prefer that over inline or custom styles. There is also a `tailwind.config.js` with custom overrides.

> NOTE: Only in _very_ few occasions do we allow custom styles/classes.

## 3. Mobile First

Always write your styles with mobile-first in mind.

> e.g. Here the item is `hidden` on mobile, and has `display: block` from screen size `md` upwards.
> This uses `Tailwind` described below.

```jsx
const Item = ({ children }) => (
    <div className="hidden md:block">
        // ...
    </div>
)
```

Another example where you set the div on different resolutions (e.g. mobile is full width, medium screens are half width, and on large+ screens the width is 1/3 of the max width).

```jsx
const AnotherItem = ({ children }) => (
    <div className="w-full sm:w-1/2 lg:w-1/3">
        // ...
    </div>
)
```

## References

- [Tailwind CSS](https://tailwindcss.com/)

<br />
<br />
<hr />
<br />
<br />

[Next Part: 6. Storybook](./6-Storybook.md)

<br />
<br />