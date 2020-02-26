

# About

An easy to use react split panel component with flexible constrains. 

[examples](https://bnbarak.github.io/split-panel-react)

# Installation

`npm i split-panel-react`

# Usage

```javascript
import SplitPanel from 'split-panel-react';
```

```javascript
<SplitPanel>
  <div>Left side</div>
  <div>Right side</div>
</SplitPanel>
```

# Advanced Usage

```javascript
const containerStyle = {
  height: "200px",
  border: "1px solid #e0e0e0",
  boxShadow: "0px 0px 6px -3px #8483DB"
};

const dividerStyle = {
  background: "#ff90f9",
  width: "2px"
};

<SplitPanel
  containerStyle={containerStyle}
  dividerStyle={dividerStyle}
  leftMaxWidth={700}
  leftMinWidth={100}
  rightMaxWidth={700}
  rightMinWidth={50}
  defaultLeftWidth={600}
>
  <div>Left side</div>
  <div>Right side</div>
</SplitPanel>
```

## Props

##### leftMaxWidth ([number] default: `null`)

Left panel maximum width in pixels

##### leftMinWidth ([number], default: `null`)

Left panel minimum width in pixels

##### rightMaxWidth ([number] default: `null`)

Right panel maximum width in pixels

##### rightMinWidth ([number] default: `null`)

Right panel minimum width in pixels

##### defaultLeftWidth ([number] default: `null`)

Left panel default width in pixels

##### defaultRightWidth ([number] default: `null`)

Right panel default width in pixels

##### defaultRatio ([number] default: `50`)

Default ration between the two side, scale: 1-100.
Example: `40` will set the width of the left panel to 40% of the container

##### maxRatio ([number] default: null`)

The maximum ratio between the left and the right panels, scale: 1-100 [example](https://bnbarak.github.io/split-panel/?path=/story/constrains--min-ratio)

##### minRatio ([number] default: `50`)

The minimum ratio between the left and the right panels, scale: 1-100 [example](https://bnbarak.github.io/split-panel/?path=/story/constrains--max-ratio)

##### height ([number] default: `null`)

Container's height in pixels

##### containerStyle ([object] default: `{}`)

An object to style the container, [example](https://bnbarak.github.io/split-panel/?path=/story/style--container)

##### dividerStyle ([object] default: `{}`)

An object to style the divider, [example](https://bnbarak.github.io/split-panel/?path=/story/style--divider)

##### onStart ([function] default: `() => {}`)

A callback being fire when the divider starts moving

##### onFinish ([function] default: `() => {}`)

A callback being fire when on mouse up event from the divider

##### onChange: ([function] default: `({ratio, containerWidth, leftWidth, rightWisth) => {}`)

A callback being fire when the divider moves.

##### dividerWidth ([number] default: `2`)

Divider width in pixels. For accuracy, indicate the divider width if changed in `dividerStyle`


## Q&A

- **What happen if I have conflicted constrains?**
  `split-panel` respects all constrains equally. The user need to make sure that the constrains does not conflict. For example:
  Here the `leftMinWidth` is bigger than the `leftMaxWidth`

```javascript
<SplitPanel leftMaxWidth={200} leftMinWidth={300}>
  <div>a</div>
  <div>b</div>
</SplitPanel>
```
