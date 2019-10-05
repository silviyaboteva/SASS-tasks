# js-3tyqrr

[Edit on StackBlitz ⚡️](https://stackblitz.com/edit/js-3tyqrr)

# This project is built using SASS preprocessor and flexbox

## Sass techniques

- Install [node-sass](https://www.npmjs.com/package/node-sass) NPM package to compile the SCSS files to CSS. To install node-sass run the following command in your terminal: `npm install node-sass`.
- Open the package.json file in a code editor. Add scripts section (if not available) add the dollowing command:
```
"scripts": {
  ...
  "scss": "node-sass --watch scss -o css"
}
```
- Run the following command in the terminal: `npm run scss`.

## Flexbox techniques

### Parent Element (Container)
The flex container properties are:

#### display: flex;

#### flex-direction: row | row-reverse | column | column-reverse; 
- row (default): left to right in ltr; right to left in rtl
- row-reverse: right to left in ltr; left to right in rtl
- column: same as row but top to bottom
- column-reverse: same as row-reverse but bottom to top

#### flex-wrap: nowrap | wrap | wrap-reverse;
- nowrap (default): all flex items will be on one line
- wrap: flex items will wrap onto multiple lines, from top to bottom.
- wrap-reverse: flex items will wrap onto multiple lines from bottom to top.

#### flex-flow: <‘flex-direction’> || <‘flex-wrap’>
- The default value is row nowrap.

#### justify-content(horizontally): flex-start | flex-end | center | space-between | space-around | space-evenly | start | end | left | right ... + safe | unsafe;
Save to use:
- flex-start (default): items are packed toward the start of the flex-direction.
- flex-end: items are packed toward the end of the flex-direction.
start: items are packed toward the start of the writing-mode direction.
- center: items are centered along the line.

Chrome not supported:
- end: items are packed toward the end of the writing-mode direction.
- left: items are packed toward left edge of the container, unless that doesn't make sense with the flex-direction, then it behaves like start.
- right: items are packed toward right edge of the container, unless that doesn't make sense with the flex-direction, then it behaves like start.
- start

Edge not supported:
- space-between: items are evenly distributed in the line; first item is on the start line, last item on the end line.

- space-around: items are evenly distributed in the line with equal space around them. Note that visually the spaces aren't equal, since all the items have equal space on both sides. The first item will have one unit of space against the container edge, but two units of space between the next item because that next item has its own spacing that applies.
- space-evenly: items are distributed so that the spacing between any two items (and the space to the edges) is equal.


#### align-items(vertically): stretch | flex-start | flex-end | center | baseline | first baseline | last baseline | start | end | self-start | self-end + ... safe | unsafe;
- stretch (default): stretch to fill the container (still respect min-width/max-width)
- flex-start / start / self-start: items are placed at the start of the cross axis. The difference between these is subtle, and is about respecting the flex-direction rules or the writing-mode rules.
- flex-end / end / self-end: items are placed at the end of the cross axis. The difference again is subtle and is about respecting flex-direction rules vs. writing-mode rules.
- center: items are centered in the cross-axis
- baseline: items are aligned such as their baselines align

#### align-content: flex-start | flex-end | center | space-between | space-around | space-evenly | stretch | start | end | baseline | first baseline | last baseline + ... safe | unsafe;
- flex-start / start: items packed to the start of the container. The (more supported) flex-start honors the flex-direction while start honors the writing-mode direction.
- flex-end / end: items packed to the end of the container. The (more support) flex-end honors the flex-direction while end honors the writing-mode direction.
- center: items centered in the container
- space-between: items evenly distributed; the first line is at the start of the container while the last one is at the end
- space-around: items evenly distributed with equal space around each line
- space-evenly: items are evenly distributed with equal space around them
stretch (default): lines stretch to take up the remaining space

### Child Element (Items)

#### flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
It is recommended that you use this shorthand property rather than set the individual properties. The shorthand sets the other values intelligently.

The second and third parameters (flex-shrink and flex-basis) are optional. Default is 0 1 auto.

#### order: <integer>; /* default is 0 */

#### flex-grow: <number>; /* default 0 */
This defines the ability for a flex item to grow if necessary. If all items have flex-grow set to 1, the remaining space in the container will be distributed equally to all children. If one of the children has a value of 2, the remaining space would take up twice as much space as the others (or it will try to, at least).

#### flex-shrink: <number>; /* default 1 */
This defines the ability for a flex item to shrink if necessary.

#### flex-basis: <length> | auto; /* default auto */
This defines the default size of an element before the remaining space is distributed. If set to 0, the extra space around content isn't factored in. If set to auto, the extra space is distributed based on its flex-grow value. https://www.w3.org/TR/css-flexbox-1/images/rel-vs-abs-flex.svg

#### align-self: auto | flex-start | flex-end | center | baseline | stretch;
This allows the default alignment (or the one specified by align-items) to be overridden for individual flex items.

