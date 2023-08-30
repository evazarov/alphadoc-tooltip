## Table of Contents
- [Installation](#installation)
- [Setup](#setup)
- [Usage](#usage)
- [Customization](#customization)
- [Related](#related)

## Installation

**via npm**
```shell
npm install evazarov/alphadoc-tooltip
```

**via yarn**
```shell
yarn add evazarov/alphadoc-tooltip
```

## Setup

**in Webpack**
```javascript
import tooltip from 'alphadoc-tooltip/tooltip.css'
```

Make sure, `node_modules` is included in the `includePaths` setting. You can then directly import the library into your file.

## Usage

Using the tooltip is incredibly simple. Simply add a `aria-label` and `role="tooltip"` attribute to the element on which you want the tooltip to appear. The tooltip message is the attribute value `aria-label="your message"`. This along with a position modifier is all you need to get going. Example:-
```html
<button aria-label="Hey tooltip!" data-tooltip-position="top" role="tooltip">
```

### Position Modifiers

You can change the direction of the tooltip by adding a `data-tooltip-position` attribute. The accepted values of this attribute are:- `top`, `top-left`, `top-right`, `bottom`, `bottom-left`, `bottom-right`, `left` and `right`. Example:-
```html
<button aria-label="Hey tooltip!" data-tooltip-position="top-left" role="tooltip">
```

### Size Modifiers

By default, the tooltip will takeup only the size it requires to show the text. You can specify sizes by adding a `data-tooltip-size` attribute. The accepted values include `small`, `medium`, `large` and `fit`. Example:-
```html
<button aria-label="This is a decently long text!" data-tooltip-position="top-left" data-tooltip-size="medium" role="tooltip">
```

**Note** - `fit` sets the width of the tooltip to be the same as the width on the element. It only works along with the `top` and `bottom` position modifiers.

## Customization

Tooltip uses **css variables**, which allows you to customize the behavior of the tooltip as per your needs.


| Variable                        | Description                                        | Default Value |
|---------------------------------|----------------------------------------------------|---------------|
| `--tooltip-transition-duration` | Specifies the duration of the tootltip transition  | `.18s`        |
| `--tooltip-transition-delay`    | The delay on hover before showing the tooltip      | `0s`          |
| `--tooltip-transition-easing`   | The easing applied while transitioning the tooltip | `ease-in-out` |
| `--tooltip-font-size`           | Sets the font size of the text in tooltip          | `13px`        |
| `--tooltip-font-weight`         | The font weight of the text in tooltip             | `normal`      |
| `--tooltip-text-transform`      | Controls the casing of the text                    | `none`        |
| `--tooltip-text-align`          | Sets the alignment of the text in the tooltip      | `center`      |

&nbsp;

Example:-
```css
:root {
 --tooltip-transition-duration: 0.5s;
 --tooltip-transition-delay: 1s;
 --tooltip-transition-easing: ease-out;
 --tooltip-font-size: 13px;
 --tooltip-font-weight: bold;
 --tooltip-text-transform: uppercase;
 --tooltip-text-align: left;
}
```

The above code will cause all the tooltips to transition over `0.5s` while applying an easing of type `ease-out` after a delay of `1s`. The text will be `bold` and `uppercase` and have a font size of `13px`.

You could also customize the tooltip for individual instances by using a selector more specific than `:root`. Example:-

```css
.tooltip {
 --tooltip-transition-duration: 0.2s;
 --tooltip-transition-delay: 0s;
 --tooltip-transition-easing: ease-in-out;
}
```

The above code would only affect the tooltips shown on any element with the `tooltip` class.

For more on css variables see [here](https://css-tricks.com/now-css-custom-properties-thing-value-parts-can-changed-individually/)
