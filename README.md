# Exercise 3: Responsive from Scratch

In this exercise you will learn how to create a responsive layout from scratch. Bootstrap will not be used throughout the duration of this activity. We will be implementing a grid similarly to the Bootstrap based one in the previous exercise using [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) and [Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox). Before we begin work on this exercise we will introduce each of these concepts.

***
- [Media Queries](#media-queries)
- [Flexbox](#flexbox)
- [Our First Stab at Responsive CSS](#our-first-stab-at-responsive-css)
- [Resources](#resources)
***




## Media Queries

Media queries are a feature of CSS that allow us to conditionally apply styles depending on the browser window's width and height. You can also target specific devices such as printers. Media queries are what enable us to write one webpage that is able to adapt as well as respond to the constraints of the browser displaying it. Without them we need to either develop multiple pages with different designs for different devices, or design in an extremely constrained and impractical manner.

Media queries can be used to conditionally load entire style sheets using the `media` attribute on a `<link>` element however we're going to stick to the most common and flexible way to utilize them by use the `@media` [at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule) directly in our CSS.

`@media` CSS syntax can be thought of as an _if statement_ if you're familiar with any programming language like JavaScript. Consider the following code:

```css
.rad-box {
	background-color: #e2e2e2;
}

@media (min-width: 800px) {
	.rad-box {
		background-color: #a8a8a8;
	}
}
```

Our first CSS rule applies the background colour `#e2e2e2` onto all elements with the class `rad-box`. Underneath it we have a media query that has it's own [declaration block](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Syntax#CSS_declaration_blocks) that contains yet another CSS rule with a nested declaration block for `.rad-box` that applies the background colour `#a8a8a8`.

So what's the background colour of our `.rad-box` elements? It depends on the size of your viewport width or more simply put the width of the browser's window:

- **If** the viewport width is **less than `800px`** the background colour will be `#e2e2e2`
- **If** the viewport width is **equal or greater than `800px`** the background colour will be `#a8a8a8`

We can also specify media queries by a `max-width`:

```css
.rad-box {
	background-color: #e2e2e2;
}

@media (max-width: 800px) {
	.rad-box {
		background-color: #a8a8a8;
	}
}
```

- **If** the viewport width is **greater than `800px`** the background colour will be `#e2e2e2`
- **If** the viewport width is **equal or less than `800px`** the background colour will be `#a8a8a8`

We can even combine conditions to only apply rules between a specific range:

```css
.rad-box {
	background-color: #e2e2e2;
}

@media (min-width: 800px) and (max-width: 899px) {
	.rad-box {
		background-color: #a8a8a8;
	}
}
```

- **If** the viewport width is **less than `800px` _or_ greater or equal to 900px** the background colour will be `#e2e2e2`
- **If** the viewport width is **equal or greater than `800px` _and_ less than 900px** the background colour will be `#a8a8a8`

You cannot nest `@media` queries in CSS, and you cannot use them inside of a CSS [declaration block](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Syntax#CSS_declaration_blocks). You can read about the specifics of the `@media` at-rule [here](https://developer.mozilla.org/en-US/docs/Web/CSS/@media).




## Flexbox

The _Flexible Box Module_ (aka Flexbox) is a one-dimensional layout model. In the past before Flexbox was widely supported web layouts were primarily created using [floats](https://developer.mozilla.org/en-US/docs/Web/CSS/float). Floats were designed to position content, such as an image embedded in text, in a way where the text or other inline content would wrap around it much like what you see in newspapers.

The use of floats to implement a webpage's layout is rather cumbersome as they weren't designed for that purpose, yet it was the best solution before the adoption of Flexbox. Bootstrap version 4 and higher thankfully don't use floats for layout anymore, but instead use Flexbox.

CSS's [grid property](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout) won't be covered in this course as it isn't widely supported yet at the time this course was written, and isn't used by Bootstrap yet anyway. I recommend learning it outside of this course as it's an up-and-coming technology.

Complete the [Interneting is Hard Flexbox tutorial](https://internetingishard.com/html-and-css/flexbox/) to familiarize yourself with Flexbox.




## Our First Stab at Responsive CSS

If we look at our previous exercise the contents of the main header at the top of our page become centered when we resize our browser's window to a viewport width of `767px` and under. Within this repository look at the contents of `public/css/main-header.css`. There are CSS rules applying the styles for the header that already exists on our page as well as a comment:

```css
/**
 * @media: Center <h1> using `justify-content: center;`
 *   applied to .main-header when the viewport is less than
 *   or equal to 767px.
 */
```

Underneath it try implementing a `@media` query that meets these conditions. The [`justify-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content) property is a part of Flexbox and allows us to position content within a Flexbox container. Checkout the [Flexbox playground](https://codepen.io/enxaneta/full/adLPwv/) entry for this property for further clarification. Try to solve this on your own and check the solution below when complete.

<details>
  <summary>Solution</summary>

  ```css
/**
 * @media: Center <h1> using `justify-content: center;`
 *   applied to .main-header when the viewport is less than
 *   or equal to 767px.
 */
@media (max-width: 767px) {
	.main-header {
		justify-content: center;
	}
}
  ```

</details>




## Resources


### Media Queries

- [**MDN:** Using Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [**Interneting is Hard:** CSS Media Queries](https://internetingishard.com/html-and-css/responsive-design/#css-media-queries)
- [**MDN:** `@media`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)


### Flexbox

- [**Interneting is Hard:** Flexbox](https://internetingishard.com/html-and-css/flexbox/)
- [**MDN:** Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
- [**Codepen:** Flexbox Playground](https://codepen.io/enxaneta/full/adLPwv/)
