# g.css

v1.0

g.css is a simple, lightweight and fully customizable - responsive css grid system. 

It's supported in Chrome, Firefox, Opera, Safari, IE9+ and all mobile browsers.

[Demo](http://edsloan.github.io/g.css)

## Installation

-   Clone `git clone https://github.com/edsloan/g.css.git`
-   [Archived download](https://github.com/edsloan/g.css/archive/master.zip)

## Getting Started

#### Link to g.css
```html
<head>
	<link rel="stylesheet" href="css/g.css">
</head>
```
Or if you want to use the minified file, point the `href` above to `href="css/g.min.css"`.

#### HTML structure
```html
<div class="g">
	<div class="r">
		<div class="x12">
			<!--Content-->
		</div>
	</div>
	<div class="r">
		<div class="x4">
			<!--Content-->
		</div>
		<div class="x4">
			<!--Content-->
		</div>
		<div class="x4">
			<!--Content-->
		</div>
	</div>
	<!-- ...and so on... -->
</div>
```
This example will give a 1 column grid on the first row and a 3 column grid on the second, ideal for a main banner and then sub-content below.

- - -
It's worth noting that the column class uses the CSS [attribute selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors) - `[class^='x']` for reference, so it's **imperative** that you place it at the start of the class attribute definition.
```html
<div class="x8 a-class another-class">
	<!--content-->
</div>
```

#### Full width background
Simply switch around the `g` and `r` classes in your markup and apply the background to the element holding the `r` class. Background images work great also, you can throw in the optional extras of `background-size: cover` to make sure the image will always fill the full width and `background-position: 50% 50%` to vertically and horizontally center it.
```html
<div class="r bg">
	<div class="g">
		<div class="x12">
			<!--Content-->
		</div>
	</div>
</div>
```
```css
/*color*/
.bg {
	background: grey
}
/*images*/
.bg {
	background-image: url('img/src');
	background-size: cover;  /* don't forget vendor prefixes for older browser versions*/
	background-position: 50% 50%
}
```

#### Sass
- Go to where g.css sits within your project:

    `cd .. your/g.css/directory`

- Run the command to start watching your changes:

    `sass --watch sass/g.scss:g.css --style expanded`

- Finally, open the _options.scss partial and follow the instructions if you wish to configure your set-up.

## Customisation

### Container width
The default container width it set to `960px`. This can be altered to fit your requirements, removing it entirely will set the container to a full width layout, which is perfectly fine to do.
```css
.g {
	width: 1024px
}
```
### Column width
You can also adjust the column width declarations to allow for different sized column widths. Firstly divide the container width by the column(s) per row. Then work out the percentage this value has of the container width. Finally take off the desired column margin. For an example - 5 column grid:
```css
.g {
	width: 960px
}
```
```css
[class^='x'] {
    margin: 0 1%  /* 2% total */
}
```
```css
.x5 {
    width: 98%  /* 960 / 1 = 960 , ((960 / 960) * 100) - 2 = 98 */
}
.x4 {
    width: 48%  /* 960 / 2 = 480 , ((480 / 960) * 100) - 2 = 48 */
}
.x3 {
    width: 31.33333333%  /* 960 / 3 = 320 , ((320 / 960) * 100) - 2 = 31.33333333 */
}
.x2 {
    width: 23%  /* 960 / 4 = 240 , ((240 / 960) * 100) - 2 = 23 */
}
.x1 {
    width: 18%  /* 960 / 5 = 192 , ((192 / 960) * 100) - 2 = 18 */
}
```
It's also the same with adjusting the column widths within the breakpoints. Using the styles above for example, to make an `.x3` span across half of the screen at `480px` and below with a column `margin: 0 1%;`, would be:

```css
@media(max-width: 480px) {
    .x3 {
        width: 48%
    }
}
```

### Column naming
This can be changed to anything you want, but you would need to bear in mind the impact this will have on the attribute selector, as highlighted above.
```css
.example12 {
	width: 98%
}
.example11 {
	width: 89.66666667%
}
/* ...and so on... */
```
```css
[class^='example'] {
    float: left;
    margin: 0 1%;
    -moz-box-sizing: border-box;
    -webkit-box-sizing: border-box;
    box-sizing: border-box
}
```
```css
@media(max-width: 767px) {
    [class^='example'] {
        width: 98%
    }
}
```

### Breakpoints
Again this is open to interpretation. The default setting is to maintain the grid layout down to `768px`, then switch to a 1 column layout below. To modify this you will need to adjust the `max-width` feature of when the `@media` query fires.
```css
@media(max-width: 480px) {
    [class^='x'] {
        width: 98%
    }
}
```

### Extras
* **Images to fit column width and scale** - This can be achieved by giving the desired image(s) a property of `max-width: 100%`.
```css
img {
    max-width: 100%
}
```

## Implementations
* Get your site/project listed here.

## Author
[@edsloan](https://twitter.com/edsloandev)
