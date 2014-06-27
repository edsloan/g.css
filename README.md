# g.css

v1.0

g.css is a fully customisable, minimalistic - responsive css grid system. It's supported in Chrome, Firefox, Opera, Safari, IE9+ and all mobile browsers.

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
Or if you want to use the minfied file, point the `href` above to `href="css/g.min.css"`.

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

**Full width background**

Simply switch around the `g` and `r` classes in your markup and apply the background to the element holding the `r` class.
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
.bg {
	background: grey
}
```

## Customisation

### Container width
The default container width it set to `960px`. This can be altered to fit your requirements, removing it entirely will set the container to a full width layout, which works great also.
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
@media(max-width: 767px) {
    [class^='example'] {
        width: 98%
    }
}
```
### Breakpoints
Again this is open to interpretation. The default setting is to maintain the grid layout down to `768px`, then switch to a 1 column layout below. To modify this you will need to adjust the `max-width` of when the `@media` query fires.
```css
@media(max-width: 480px) {
    [class^='x'] {
        width: 98%
    }
}
```
## Do's
* **Customise** - It was designed to be bare-bones, allowing for as much customisation as possible. So please, tear it up as best as you can!
* **Contribute** - I'm always open to suggestions for improvement.
* **Share** - Please help this project get noticed, Feel free to fork, star and share this repository.

## Dont's
* **Class declaration** - As noted above, please make sure that whatever you name the column class, is that it's defined first within the class attribute.
* **Plagiarize** - I'm happy for this to be used at your hearts content, but please do give credit where it's due and point people in this direction if they are interested in finding out more.

## FAQs
* **Please add more?** - There are other related projects in the pipeline which will be hosted on other repositories, ultimately however, I wanted this project to be as minuscule as possible. So in the future this repository will be aimed towards less rather than more.
* **Add LESS and/or SASS configurations?** - To be honest I'm still sitting on the fence about this. I'm not the biggest advocate of CSS preprocessors and it's not (at present) the direction I want to take. However if there is support for these types of features to be added, I will certainly take them into consideration.
* **Why use `x` as a class name?** - In order to create a minimalistic system, I only wanted to use one letter for the class reference. So for this to work with the attribute selector, `x` was chosen as it appears the fewest amount of times at the start of all words in the english language.
* **Please give older versions of IE support?** - The web has moved on and there is no intention for this project to support old versions of IE.

## Implementations
* Get your site/project listed here.

## Author
[@edsloan](https://twitter.com/edsloandev)
