# Styler

## Simplicity is the key

The simplest way writing css-in-js in any framework: react/vue/angular. It is native css-in-js library with just barbone to help you get started on any project with css-in-js.

## Features

- Framework agnostic
- Server side rendering
- emotion.js syntax for easy onboarding.
- styled-component for react lovers use [@vtechguys/styler-styled](https://www.npmjs.com/package/@vtechguys/styler-styled)
- Size: 1.6KB and Gzipped: 889 Bytes

## Use

```js
import { css } from "@vtechguys/styler";

const boxStyles = {
  width: "50px",
  height: "50px",
  border: "1px solid black",
  display: "flex",
  flexDirection: "row",
  justifyContent: "center",
  alignItems: "center",
};

const className = css(boxStyles);

console.log("generated class: ", className); // generated class: css-1234
```

The above shows how native it can be used and thus framework agnostic. Following is using it with react.

```jsx
import { css } from "@vtechguys/styler";

const styles = {
  boxStyles: css({
    width: "50px",
    height: "50px",
    border: "1px solid black",
    display: "flex",
    flexDirection: "row",
    justifyContent: "center",
    alignItems: "center",
  }),
};

function Box() {
  return <div className={styles.boxStyles}>Box</div>;
}
```

The keyframes and styled used like:

```jsx
const growAnimationName = keyframes({
  from: { transform: "scale(1)" },
  to: { transform: "scale(2) " },
});

const Link = styled("a")({
  backgroundColor: "orange",
  color: "white",
  fontWeight: 600,
  fontSize: 16,
  padding: "8px 16px",
  margin: "20px",
  "&:hover": {
    animation: `${growAnimationName} 500ms ease-in-out`,
  },
});
```

For server side rendering:

```js
import { getStyleSSR, STYLE_TAG_ID } from "@vtechguys/styler";
// once rendering is complete put this in <head>
// the id here is important for the styler lib so don't change it
const styleTag = `<style id="${STYLE_TAG_ID}">${getStyleSSR()}</style>`;
```
