# v-pure-tooltip
> A pure CSS tooltip directive for Vue.js 2.x (based on [Balloon.css](https://github.com/kazzkiq/balloon.css))


# Installation
<pre>npm install v-pure-tooltip</pre>

# Usage
## Load the directive
```js
import Vue from 'vue';
import VPureTooltip from 'v-pure-tooltip';

Vue.use(VPureTooltip);
```

## Configuration: via modifiers
```html
<div v-pure-tooltip.POSITION.LENGTH.VISIBLE="VALUE"></div>
```
... where:
- **POSITION**: `up`, `down`, `left`, `right`, `up-left`, `up-right`, `down-left`, `down-right`
- **LENGTH**: `small`, `medium`, `large`, `xlarge`, `fit`
- **VISIBLE**: `visible`
- **VALUE**: `someVariable`, `'string with HTML special chars, emoji, font icons'`

>*NOTE: the order of modifiers doesn't matter.*


*E.g. #1: Tooltip positioned to left, medium size and visible all the time* 
```html
<div v-pure-tooltip.left.medium.visible="'My Awesome Tooltip Text'">I'm always visible</div>
```

*E.g. #2: Tooltip positioned down-left, small size and visible only on hover*
```html
<div v-pure-tooltip.down-left.small="tooltipMessage">Hover me!</div>
```
```js
export default {
  data: () => ({
    tooltipMessage: 'Tooltip message with emojis: 😀 😬 😁 😂 😃 😆',
  }),
};
```

## Configuration: via object literals
```html
<div v-pure-tooltip="{
  position: POSITION,
  length: LENGTH,
  visible: VISIBLE,
  value: VALUE }"
></div>
```

| KEY-VALUE | TYPE   | ACCEPTED VALUES |
| -------- | ------- | --------------- |
| POSITION | String  |`up`, `down`, `left`, `right`, `up-left`, `up-right`, `down-left`, `down-right` |
| LENGTH   | String  | `small`, `medium`, `large`, `xlarge`, `fit` |
| VISIBLE  | Boolean | `true`, `false`
| VALUE    | String  |`'string with HTML special chars, emoji, font icons'`

*E.g.: Tooltip positioned down, fit size and visible only on hover*
```html
<div v-pure-tooltip="tooltipConfig">Hover me!</div>
```
```js
export default {
  data: () => ({
    tooltipConfig: {
      position: 'down',
      length: 'fit',
      visible: false,
      value: 'HTML special characters: &#9787; &#9986; &#9820;',
    },
  }),
};
```

## Configuration notes
- Use only one configuration method: modifiers or object literals. There's no support for a combination of these two.
- When using object literals or modifiers with Vue data variable, any update on these will trigger an update within the directive.
- VPureTooltip can handle any Balloon.css features.  
- For more visual effects please visit the awesome [Balloon.css](https://github.com/kazzkiq/balloon.css) library and its demo page.


## License
The code is available under the [MIT license](https://github.com/tbutcaru/v-pure-tooltip/blob/master/README.md).
