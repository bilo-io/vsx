# 5. Styling

> A guide to frontend development with Visual Studio Code.
>
> - Back to the [README](../../README.md)
> - Try out the [Assessment](./guides/CryptoCharts.md)
> - Also check out [Appendices](./appendix/CodingStandards.md)

- [1. Setup Environment](./1-SetupEnvironment.md)
- [2. ES6, Typescript & NodeJS](./2-Javascript.md)
- [3. React](./3-React.md)
- [4. Redux](./4-Redux.md)
- Styling
- [6. Storybook](./6-Storybook.md)

## 1. Tailwind

For the vast majority of styling we use [TailwindCSS](https://tailwindcss.com/), and prefer that over inline or custom styles. There is also a `tailwind.config.js` with custom overrides.

> NOTE: Only in _very_ few occasions do we allow custom styles/classes.

## 2. Mobile First

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

## References

- [Tailwind CSS](https://tailwindcss.com/)
