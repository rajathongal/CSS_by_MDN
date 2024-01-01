# CSS first steps overview

CSS (Cascading Style Sheets) is used to style and lay out web pages — for example, to alter the font, color, size, and spacing of your content, split it into multiple columns, or add animations and other decorative features.

## What is CSS for?

CSS is a language for specifying how documents are presented to users — how they are styled, laid out, etc.

A document is usually a text file structured using a markup language — HTML is the most common markup language, but you may also come across other markup languages such as SVG or XML.

Presenting a document to a user means converting it into a form usable by your audience. Browsers, like Firefox, Chrome, or Edge, are designed to present documents visually, for example, on a computer screen, projector, or printer.

**Note**: A browser is sometimes called a user agent, which basically means a computer program that represents a person inside a computer system. Browsers are the main type of user agents we think of when talking about CSS, however, they are not the only ones. There are other user agents available, such as those that convert HTML and CSS documents into PDFs to be printed.

## CSS syntax

CSS is a rule-based language — you define the rules by specifying groups of styles that should be applied to particular elements or groups of elements on your web page.

For example, you can decide to have the main heading on your page to be shown as large red text. The following code shows a very simple CSS rule that would achieve the styling described above:

```CSS
h1 {
  color: red;
  font-size: 5em;
}
```

- In the above example, the CSS rule opens with a selector. This selects the HTML element that we are going to style. In this case, we are styling level one headings (h1).
- We then have a set of curly braces { }.
- Inside the braces will be one or more declarations, which take the form of property and value pairs. We specify the property (color in the above example) before the colon, and we specify the value of the property after the colon (red in this example).
- This example contains two declarations, one for color and the other for font-size. Each pair specifies a property of the element(s) we are selecting (h1 in this case), then a value that we'd like to give the property.

CSS properties have different allowable values, depending on which property is being specified. In our example, we have the color property, which can take various color values. We also have the font-size property. This property can take various size units as a value.

A CSS stylesheet will contain many such rules, written one after the other.

```CSS
h1 {
  color: red;
  font-size: 5em;
}

p {
  color: black;
}
```

## CSS modules

As there are so many things that you could style using CSS, the language is broken down into modules. You'll see reference to these modules as you explore MDN. Many of the documentation pages are organized around a particular module. For example, you could take a look at the MDN reference to the Backgrounds and Borders module to find out what its purpose is and the properties and features it contains. In that module, you will also find a link to Specifications that defines the technology (also see the section below).

## CSS specifications

All web standards technologies (HTML, CSS, JavaScript, etc.) are defined in giant documents called specifications (or "specs"), which are published by standards organizations (such as the W3C, WHATWG, ECMA, or Khronos) and define precisely how those technologies are supposed to behave.

CSS is no different — it is developed by a group within the W3C called the CSS Working Group. This group is made of representatives of browser vendors and other companies who have an interest in CSS. There are also other people, known as invited experts, who act as independent voices; they are not linked to a member organization.

## Browser support information

After a CSS feature has been specified, then it is only useful for us in developing web pages if one or more browsers have implemented the feature. This means that the code has been written to turn the instruction in our CSS file into something that can be output to the screen. We'll look at this process more in the lesson How CSS works. It is unusual for all browsers to implement a feature at the same time, and so there is usually a gap where you can use some part of CSS in some browsers and not in others. For this reason, being able to check implementation status is useful.

The browser support status is shown on every MDN CSS property page in a table named "Browser compatibility". Consult the information in that table to check if the property can be used on your website. For an example, [see the browser compatibility table for the CSS `font-family` property](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family#browser_compatibility).
