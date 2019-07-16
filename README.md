# Exercise 3: Responsive from Scratch

In this exercise you will learn how to create a responsive layout from scratch. Bootstrap will not be used throughout the duration of this activity. Before we begin work on this exercise we will introduce the concept of `@media` queries.

***
- [Media Queries](#media-queries)
- [Resources](#resources)
***




## Media Queries

Media queries are a feature of CSS that allow us to conditionally apply styles depending on the browser window's width and height. You can also target specific devices such as printers. They can be used to conditionally load entire style sheets using the `media` attribute on a `<link>` element however we're going to stick to the most common and flexible way to utilize them by use the `@media` syntax directly in our CSS.

`@media` CSS syntax can be thought of as an _if statement_ if you're familliar with any programming language like JavaScript. Consider the following code:

```css
.rad-box {
	background-color: #e2e2e2;
}

@media (min-width: 800px) {
	.rad-box {
		backround-color: #a8a8a8;
	}
}
```

Our first CSS rule applies the background colour `#e2e2e2` onto all elements with the class `rad-box`. Underneath it we have a media query that has it's own [declaration block](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Syntax#CSS_declaration_blocks) that contains yet another CSS rule with a nested declaration block for `.rad-box` that applies the background colour `#a8a8a8`.

So what's the background colour of our `.rad-box` elements? It depends on the size of your viewport width or more simply put the width of the browser's window:

- If the viewport width is **less than `800px`** the background colour will be `#e2e2e2`
- If the viewport width is **equal or greater than `800px`** the background colour will be `#a8a8a8`




## Resources

- [MDN: Using Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [MDN: CSS Syntax](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Syntax)
