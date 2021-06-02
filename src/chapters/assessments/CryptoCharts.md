# Assessment

## Crypto Charts

The purpose of this assessment exercise is to get a basic understanding of how our technologies work and fit together.

At the end of this exercise you will have covered:

- React
- React Router
- Redux
- Tailwind CSS
- API communication with `axios`

## Task Description

Create a React application using [Create React App (CRA)](https://reactjs.org/docs/create-a-new-react-app.html#create-react-app). The app should:

- fetch crypto currency data from the CoinGecko API.
- show a list / grid view of the list of currencies
- allow toggling between list and grid view
- clicking on a crypto currency in your UI should navigate to a new, "detail" page (e.g. `/explore/:cryptoCurrency`), on which you should
  - show more data about the selected crypto currency
  - be able to see a chart of the crypto currency's performance using the React wrapper of [Highcharts](https://www.highcharts.com/demo), namely [highcharts-react-official](https://www.npmjs.com/package/highcharts-react-official).
- Implement `TailwindCSS` for styling and `FontAwesome` for icons

Create a Navbar which:

- has the items:
  - `/` for home
  - `/explore` for the page to explore crypto currencies
  - `/favorites` to see which crypto currencies you saved to your localStorage
- is a sidebar (for desktop and tablet screen sizes)
- is a bottom tab bar (for mobile screen sizes)

## Resources

- [Create React App](https://reactjs.org/docs/create-a-new-react-app.html#create-react-app)
- [Tailwind CSS]()
- [CoinGecko API]()
- [Highcharts React](https://www.npmjs.com/package/highcharts-react-official)