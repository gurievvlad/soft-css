# Soft CSS
Soft CSS is a good blank for any project. It will reset browser styles and add a grid.

## Getting started

### Use
Clone this repository for your project. Import sass file like this:
```
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
Soft CSS has a default grid, but it can be customized. To do this, add the variable `$ breakpoints-list` above the file import. `$ breakpoints-list` is an array contains objects containing: prefix, width and padding. Note that there is two padding around the edges of the screen. An example of a standard `$ breakpoints-list` __(similar to BS, but with different paddings)__:
```
// (Prefix, minimum screen width, padding)
$breakpoints-list: (null, null, 16px), (sm, 540px, 20px), (md, 768px, 30px), (lg, 992px, 30px), (xl, 1200px, 40px)
```
Please note that the first breakpoint must not have a prefix and no minimum width.

There are two types of grids in Soft CSS: on grids and on flexes. The grid on the grid is needed to create a block with cards (suppose a list of posts or products in a store), it is very convenient because you do not need to think about horizontal paddings, and besides, it does not have a layer in the form of `.row`; the flex mesh is similar to bootstrap and is used in all other cases.

The entire mesh is wrapped in a `container` or` container-fluid` class. The width of the container is limited by paddings, so you can use a padding background right on the container. You can also use the `class =" container grid "` construct to generate a box grid.

Sample code for grid:
```
<div class="container grid">
    <div class="col-6"></div>
    <div class="col-6"></div>
</div>
```

Example code for flex:
```
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
```
// (HTML tag, size in rem)
$titleSizes: (h1, 4.5), (h2, 3), (h3, 2.25), (h4, 1.5), (h5, 1), (h6, 1)
```


