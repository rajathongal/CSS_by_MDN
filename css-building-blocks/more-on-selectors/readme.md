# Type, class, and ID selectors

## Type selectors

A type selector is sometimes referred to as a tag name selector or element selector because it selects an HTML tag/element in your document. Type selectors are not case-sensitive. In the example below, we have used the span, em and strong selectors.

Try adding a CSS rule to select the `<h1>` element and change its color to blue.

```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Type Selector</title>
    <style>
      span {
        background-color: yellow;
      }

      strong {
        color: rebeccapurple;
      }

      em {
        color: rebeccapurple;
      }
    </style>
  </head>
  <body>
    <h1>Type selectors</h1>
    <p>
      Veggies es bonus vobis, proinde vos postulo essum magis
      <span>kohlrabi welsh onion</span> daikon amaranth tatsoi tomatillo melon
      azuki bean garlic.
    </p>

    <p>
      Gumbo beet greens corn soko <strong>endive</strong> gumbo gourd. Parsley
      shallot courgette tatsoi pea sprouts fava bean collard greens dandelion
      okra wakame tomato. Dandelion cucumber earthnut pea peanut soko zucchini.
    </p>

    <p>
      Turnip greens yarrow ricebean rutabaga <em>endive cauliflower</em> sea
      lettuce kohlrabi amaranth water spinach avocado daikon napa cabbage
      asparagus winter purslane kale. Celery potato scallion desert raisin
      horseradish spinach
    </p>
  </body>
</html>

```

## The universal selector

The universal selector is indicated by an asterisk (*). It selects everything in the document (or inside the parent element if it is being chained together with another element and a descendant combinator).

In the following example, we use the universal selector to remove the margins on all elements. Instead of the default styling added by the browser — which spaces out headings and paragraphs with margins — everything is close together.

```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>universal selector</title>
     <style>
      * {
        margin: 0;
      }
     </style>
  </head>
  <body>
    <h1>Universal selector</h1>
    <p>
      Veggies es bonus vobis, proinde vos postulo essum magis
      <span>kohlrabi welsh onion</span> daikon amaranth tatsoi tomatillo melon
      azuki bean garlic.
    </p>

    <p>
      Gumbo beet greens corn soko <strong>endive</strong> gumbo gourd. Parsley
      shallot courgette tatsoi pea sprouts fava bean collard greens dandelion
      okra wakame tomato. Dandelion cucumber earthnut pea peanut soko zucchini.
    </p>
  </body>
</html>
```

This kind of behavior can sometimes be seen in "reset stylesheets", which strip out all of the browser styling. Since the universal selector makes global changes, we use it for very specific situations, such as the one described below.

### Using the universal selector to make your selectors easier to read

One use of the universal selector is to make selectors easier to read and more obvious in terms of what they are doing. For example, if we wanted to select any descendant elements of an `<article>` element that are the first child of their parent, including direct children, and make them bold, we could use the :first-child pseudo-class. We will learn more about this in the lesson on pseudo-classes and pseudo-elements, as a descendant selector along with the `<article>` element selector:

```CSS
article :first-child {
  font-weight: bold;
}
```

However, this selector could be confused with `article:first-child`, which will select any `<article>` element that is the first child of another element.

To avoid this confusion, we can add the universal selector to the `:first-child` pseudo-class, so it is more obvious what the selector is doing. It is selecting any element which is the first-child of an `<article>` element, or the first-child of any descendant element of `<article>`:

```CSS
article *:first-child {
  font-weight: bold;
}
```

Although both do the same thing, the readability is significantly improved.

## Class selectors

The case-sensitive class selector starts with a dot (.) character. It will select everything in the document with that class applied to it. In the live example below we have created a class called `highlight`, and have applied it to several places in my document. All of the elements that have the class applied are highlighted.

```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Class selectors</title>
    <style>
      .highlight {
        background-color: yellow;
      }
    </style>
  </head>
  <body>
    <h1 class="highlight">Class selectors</h1>
    <p>
      Veggies es bonus vobis, proinde vos postulo essum magis
      <span class="highlight">kohlrabi welsh onion</span> daikon amaranth tatsoi
      tomatillo melon azuki bean garlic.
    </p>

    <p class="highlight">
      Gumbo beet greens corn soko <strong>endive</strong> gumbo gourd. Parsley
      shallot courgette tatsoi pea sprouts fava bean collard greens dandelion
      okra wakame tomato. Dandelion cucumber earthnut pea peanut soko zucchini.
    </p>
  </body>
</html>
```

### Targeting classes on particular elements

You can create a selector that will target specific elements with the class applied. In this next example, we will highlight a `<span>` with a class of highlight differently to an `<h1>` heading with a class of highlight. We do this by using the type selector for the element we want to target, with the class appended using a dot, with no white space in between.

```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Targeted Class selectors</title>
    <style>
      span.highlight {
        background-color: yellow;
      }

      h1.highlight {
        background-color: pink;
      }
    </style>
  </head>
  <body>
    <h1 class="highlight">Class selectors</h1>
    <p>
      Veggies es bonus vobis, proinde vos postulo essum magis
      <span class="highlight">kohlrabi welsh onion</span> daikon amaranth tatsoi
      tomatillo melon azuki bean garlic.
    </p>

    <p class="highlight">
      Gumbo beet greens corn soko <strong>endive</strong> gumbo gourd. Parsley
      shallot courgette tatsoi pea sprouts fava bean collard greens dandelion
      okra wakame tomato. Dandelion cucumber earthnut pea peanut soko zucchini.
    </p>
  </body>
</html>

```

This approach reduces the scope of a rule. The rule will only apply to that particular element and class combination. You would need to add another selector if you decided the rule should apply to other elements too.

### Target an element if it has more than one class applied

You can apply multiple classes to an element and target them individually, or only select the element when all of the classes in the selector are present. This can be helpful when building up components that can be combined in different ways on your site.

In the example below, we have a `<div>` that contains a note. The grey border is applied when the box has a class of `notebox`. If it also has a class of `warning` or `danger`, we change the `border-color`.

We can tell the browser that we only want to match the element if it has two classes applied by chaining them together with no white space between them. You'll see that the last `<div>` doesn't get any styling applied, as it only has the `danger` class; it needs `notebox` as well to get anything applied.

## ID selectors

The case-sensitive ID selector **begins with a # rather than a dot** character, but is used in the same way as a class selector.

However, an ID can be used only once per page, and elements can only have a single id value applied to them. It can select an element that has the id set on it, and you can precede the ID with a type selector to only target the element if both the element and ID match. You can see both of these uses in the following example:

```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Id Selectors</title>
    <style>
      #one {
        background-color: yellow;
      }

      h1#heading {
        color: rebeccapurple;
      }
    </style>
  </head>
  <body>
    <h1 id="heading">ID selector</h1>
    <p>
      Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi welsh
      onion daikon amaranth tatsoi tomatillo melon azuki bean garlic.
    </p>

    <p id="one">
      Gumbo beet greens corn soko <strong>endive</strong> gumbo gourd. Parsley
      shallot courgette tatsoi pea sprouts fava bean collard greens dandelion
      okra wakame tomato. Dandelion cucumber earthnut pea peanut soko zucchini.
    </p>
  </body>
</html>
```

**Warning**: Using the same ID multiple times in a document may appear to work for styling purposes, but don't do this. It results in invalid code, and will cause strange behavior in many places.

**Note**: The ID selector has high `specificity`. This means styles applied based on matching an ID selector will overrule styles applied based on other selector, including class and type selectors. Because an ID can only occur once on a page and because of the high specificity of ID selectors, it is preferable to add a class to an element instead of an ID. If using the ID is the only way to target the element — perhaps because you do not have access to the markup and cannot edit it — consider using the ID within an an [attribute selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors), such as `p[id="header"]`. [Learn specificity](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance).
