# g.css

v1.0

g.css is a fully customisable, minimalistic - css grid system. It's supported in Chrome, Firefox, Opera, Safari, IE9+ and mobile browsers.

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

#### HTML structure
```html
<div class="g">
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
</div>
```
As the column class uses the CSS [attribute selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors) for reference, it's imperative that you place it at the start of the class attribute definition.
```html
<div class="x8 a-class another-class">
	<!--content-->
</div>
```
This would also mean that you can't start with a non g.css bound class beginning with that letter (or letters), so in this case `class="xylophone x8"` would not work either.

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
The default container width it set to `960px`. This can be altered to fit your requirements, removing it entirely will set the container to a full width layout.
```css
.g {
	width: 1024px
}
```
To prevent the jumping of the container from desktop size to tablet (if the above is altered), you will need to adjust the first `@media` query. You will need to make the break point exactly however many `%`s you have set for the columns higher than the `.g` width. So with the example above:
```css
[class^='x'] {
    margin: 0 1%  /* 2% total */
}
@media(max-width: 1044px) {  /* 2% more than 1024px (rounded) */
    .g {
        width: 98%
    }
}
```
### Column width
You can also adjust the column width declarations to allow for different column widths. Firstly divide the container width by the column per row. Then work out the percentage this value has of the container width. Then take off the desired column margin.
```css
.g {
	width: 960px
}
[class^='x'] {
    margin: 0 1%  /* 2% total */
}
.x5 {
    width: 98%  /* 960 / 1 = 960 , ((960 / 960) * 100) - 2 = 98 */
}
.x4 {
    width: 48%
}
.x3 {
    width: 31.33333333%
}
.x2 {
    width: 23%
}
.x1 {
    width: 18%
}
```

### Column naming
This can be changed to anything you want, but you would need to bear in mind the attribute selector as highlighted above.
```css
.example12 {
	width: 98%
}
.example11 {
	width: 89.66666667%
}
/* ...and so on... */

@media(max-width: 767px) {
    [class^='example'] {
        width: 98%
    }
}
```
## Do's
* **Customise** - It was designed to be bare-bones allowing for as much customisation as possible. So please, tear it up as best as you can!
* **Contribute** - I'm always open to suggestions for improvement.
* **Share** - Please help this project get noticed.

## Dont's
* **Class declaration** - As noted above, make sure whatever you name the column class, is that it's defined first in the attribute.
* **Plagiarize** - I'm happy for this to be used at your hearts content, but please do give credit where it's due and point people in this direction if they are interested in finding out more.

## FAQs
* **Please add more?** - There are other related projects in the pipeline, ultimately however I wanted this to be as minuscule as possible. So in the future this repository will be aimed towards less than more.
* **Add LESS and/or SASS configurations?** - To be honest I'm still sitting on the fence about this. I'm not the biggest advocate of CSS preprocessors and it's not (at present) the direction I want to take. However if there is support for these types of features to be added I will certainly take them into consideration.
* **Why use `x` as a class name?** - In order to create a minimal system, I only wanted to use one letter for the class reference. So in order to work with the attribute selecter `x` was chosen as it appears the fewest amount times at the start of word in the english language, than any other letter.
* **Please give older versions of IE support?** - The web has moved on and there is no intention for this project to support old versions of IE.

## Implementations
* Get your site/project listed here.

## Author
[Ed Sloan](https://twitter.com/edsloandev)
