# Soft CSS
Soft CSS is a good blank for any project. It will reset browser styles and add a grid.

## Getting started

### Install

```bash
npm i soft-css
```

### Use
Clone this repository for your project. Import sass file like this:
```sass
@import soft-css;
```
Or connect soft.css in any way.

### Refresh
Resets the default browser styles. Key changes:
- `box-sizing: border-box` for everything
- `body {margin: 0}`
- Bold headings
- Working with `picture`
- Neat inputs on IOS
- No minimum input width, and fixed textarea width
- Font sizes in inputs and buttons have been fixed

### Grid
Soft CSS has a default grid, but it can be customized. To do this, add the variable `$ breakpoints-list` above the file import. `$ breakpoints-list` is an array contains objects containing: prefix, width and padding. Note that there is two padding around the edges of the screen. An example of a standard `$ breakpoints-list` _(similar to BS, but with different paddings)_:
```sass
// (Prefix, minimum screen width, padding)
$breakpoints-list: (null, null, 16px), (sm, 540px, 20px), (md, 768px, 30px), (lg, 992px, 30px), (xl, 1200px, 40px)
```
Please note that the first breakpoint must not have a prefix and no minimum width.

There are two types of grids in Soft CSS: on grids and on flexes. The grid on the grid is needed to create a block with cards (suppose a list of posts or products in a store), it is very convenient because you do not need to think about horizontal paddings, and besides, it does not have a layer in the form of `.row`; the flex mesh is similar to bootstrap and is used in all other cases.

The entire mesh is wrapped in a `container` or` container-fluid` class. The width of the container is limited by paddings, so you can use a padding background right on the container. You can also use the `class =" container grid "` construct to generate a box grid.

Sample code for grid:
```html
<div class="container grid">
    <div class="col-6"></div>
    <div class="col-6"></div>
</div>
```

Example code for flex:
```html
<div class="container">
    <div class="row">
        <div class="col-6"></div>
        <div class="col-6"></div>
    </div>
</div>
```

Warning: the container can only be assigned top and bottom paddings, and only as `padding-top` and` padding-bottom`. If you add `padding: 30px 0` everything will break

### Typography
Font sizes are set to rem. The sizes of the headers are placed in a variable, it can be changed by analogy with $breakpoints-list:
```sass
// (HTML tag, size in rem)
$titleSizes: (h1, 4.5), (h2, 3), (h3, 2.25), (h4, 1.5), (h5, 1), (h6, 1)
```

## Classes

```sass
// Классы сетки
.container, .container-fluid // For content wrapping
.row // Used inside a container, creates a flex wrapper
.grid // Creates a grid wrapper
.grid-gap // Adds gap padding to your grid block
.col-1 — .col-12,
.col-prefix-1 — .col-prefix-12 // To add width to blocks, the prefix is ​​taken from $ breakpoints-list
.col-auto // Auto width, only works with flex
.col-fill // Fills all remaining space, only works with flex
.offset-1 — .offset-prefix-11 // Shifts col to the right, only works with flex

// Typography classes
.button
.text-align-left, .text-align-center, .text-align-right

// Helper classes
.align-items-start, .align-items-center, .align-items-end, .align-items-unset
.justify-content-start, .justify-content-center, .justify-content-end, .justify-content-unset,
.justify-content-around, .justify-content-between, .justify-content-evenly
.justify-items-start, .justify-items-center, .justify-items-end, .justify-items-unset
.align-self-start, .align-self-center, .align-self-end, .align-self-unset // Content position

.d-none, .d-block, .d-flex, .d-grid, .d-inline-block, .d-inline-flex // Display mode

.h-10, .h-25, .h-50, .h-75, .h-100 // Height in percent
.w-10, .w-25, .w-50, .w-75, .w-100 // Width in percent
```

