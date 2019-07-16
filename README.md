# Exercise 3: Responsive from Scratch

In this exercise you will learn how to create a responsive layout from scratch. Bootstrap will not be used throughout the duration of this activity. We will be implementing a grid similarly to the Bootstrap based one in the previous exercise using [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) and [Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox). Before we begin work on this exercise we will introduce each of these concepts.

***
- [Media Queries](#media-queries)
- [Flexbox](#flexbox)
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

TODO




## Resources


### Media Queries

- [**MDN:** Using Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [**MDN:** `@media`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media)


### Flexbox

- [**MDN:** Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
