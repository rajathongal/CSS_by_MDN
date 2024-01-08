# CSS Selectors

In CSS, selectors are used to target the HTML elements on our web pages that we want to style.

There are a wide variety of CSS selectors available, allowing for fine-grained precision when selecting elements to style.

## What is a selector?

A CSS selector is the first part of a CSS Rule. It is a pattern of elements and other terms that tell the browser which HTML elements should be selected to have the CSS property values inside the rule applied to them. The element or elements which are selected by the selector are referred to as the subject of the selector.

In other articles you may have met some different selectors, and learned that there are selectors that target the document in different ways — for example by selecting an element such as h1, or a `class` such as `.special`.

In CSS, selectors are defined in the CSS Selectors specification; like any other part of CSS they need to have support in browsers for them to work. The majority of selectors that you will come across are defined in the [Level 3 Selectors specification](https://www.w3.org/TR/selectors-3/) and [Level 4 Selectors specification](https://www.w3.org/TR/selectors-4/), which are both mature specifications, therefore you will find excellent browser support for these selectors. **(important)**

## Selector lists

If you have more than one thing which uses the same CSS then the individual selectors can be combined into a selector list so that the rule is applied to all of the individual selectors. For example, if I have the same CSS for an h1 and also a class of .special, I could write this as two separate rules.

```CSS
h1 {
  color: blue;
}

.special {
  color: blue;
}
```

I could also combine these into a selector list, by adding a comma between them.

```CSS
h1, .special {
  color: blue;
}
```

White space is valid before or after the comma. You may also find the selectors more readable if each is on a new line.

```CSS
h1,
.special {
  color: blue;
}
```

When you group selectors in this way, if any selector is syntactically invalid, the whole rule will be ignored.

In the following example, the invalid class selector rule will be ignored, whereas the `h1` would still be styled.

```CSS
h1 {
  color: blue;
}

..special {
  color: blue;
}
```

When combined however, neither the h1 nor the class will be styled as the entire rule is deemed invalid.

```CSS
h1, ..special {
  color: blue;
}
```

## Types of selectors

There are a few different groupings of selectors, and knowing which type of selector you might need will help you to find the right tool for the job. In this article's subarticles we will look at the different groups of selectors in more detail.

### Type, class, and ID selectors

**Type selectors** target an HTML element such as an `<h1>`:

```CSS
h1 {
}
```

**Class selectors** target an element that has a specific value for its `class` attribute:

```CSS
.box {
}
```

**ID selectors** target an element that has a specific value for its `id` attribute:

```CSS
#unique {
}
```

### Attribute selectors

This group of selectors gives you different ways to select elements based on the presence of a certain attribute on an element:

```CSS
a[title] {
}
```

Or even make a selection based on the presence of an attribute with a particular value:

```CSS
a[href="https://example.com"]
{
}
```

### Pseudo-classes and pseudo-elements

This group of selectors includes pseudo-classes, which style certain states of an element.

The `:hover` pseudo-class for example selects an element only when it is being hovered over by the mouse pointer:

```CSS
a:hover {
}
```

It also includes pseudo-elements, which select a certain part of an element rather than the element itself. For example, `::first-line` always selects the first line of text inside an element (a `<p>` in the below case), acting as if a `<span>` was wrapped around the first formatted line and then selected.

```CSS
p::first-line {
}
```

Some more information from AI

Pseudo-elements in CSS allow you to style specific parts of an element. Here are a few examples:

- `::first-line`:
This example selects the first line of text within a `<p>` element and applies styles such as red color and bold font weight.

```CSS
p::first-line {
color: red;
font-weight: bold;

}

```

- `::before`:
This will insert ">> " before the content of each `<p>` element and style it with a blue color.

```CSS
p::before {
   content: ">> ";
   color: blue;
}
```

- `::after`:
This will insert " [Read more]" after the content of each `<p>` element and style it with a green color.

```CSS
p::after {
   content: " [Read more]";
   color: green;
}
```

- `::selection:`
This example styles the text that the user has selected within a `<p>` element, setting the background color to yellow and the text color to black.

```CSS
p::selection {
   background-color: yellow;
   color: black;
}
```

- `::placeholder:`

This targets the placeholder text within an `<input>` element, giving it a gray color and italic font style.

```CSS
input::placeholder {
   color: gray;
   font-style: italic;
}
```

- `nth-child:`
This selects even-numbered `<li>` elements within a `<ul>` and gives them a light gray background color.

```CSS
ul li:nth-child(even) {
   background-color: #f2f2f2;
}
```
