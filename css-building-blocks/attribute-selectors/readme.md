# Attribute selectors

As you know from your study of HTML, elements can have attributes that give further detail about the element being marked up. In CSS you can use attribute selectors to target elements with certain attributes.

## Presence and value selectors

These selectors enable the selection of an element based on the presence of an attribute alone (for example `href`), or on various different matches against the value of the attribute.

| Selector       | Example                             | Description                                                                                                              |
| -------------- | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| `[attr]`       | `a[title]`                          | Matches elements with an `attr` attribute (whose name is the value in square brackets).                                 |
| `[attr=value]` | `a[href="https://example.com"]`     | Matches elements with an `attr` attribute whose value is exactly `value` — the string inside the quotes.                 |
| `[attr~=value]`| `p[class~="special"]`               | Matches elements with an `attr` attribute whose value is exactly `value`, or contains `value` in its (space separated) list of values. |
| `[attr|=value]`| `div[lang|="zh"]`                   | Matches elements with an `attr` attribute whose value is exactly `value` or begins with `value` immediately followed by a hyphen.  |

In the example below you can see these selectors being used.

```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>presence selectors</title>
    <style>
      li[class] {
        font-size: 200%;
      }

      li[class="a"] {
        background-color: yellow;
      }

      li[class~="a"] {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>Attribute presence and value selectors</h1>
    <ul>
      <li>Item 1</li>
      <li class="a">Item 2</li>
      <li class="a b">Item 3</li>
      <li class="ab">Item 4</li>
    </ul>
  </body>
</html>
```

- By using `li[class]` we can match any list item with a class attribute. This matches all of the list items except the first one.
- `li[class="a"]` matches a selector with a class of a, but not a selector with a class of a with another space-separated class as part of the value. It selects the second list item.
- `li[class~="a"]` will match a class of a but also a value that contains the class of a as part of a whitespace-separated list. It selects the second and third list items.

## Substring matching selectors

These selectors allow for more advanced matching of substrings inside the value of your attribute.

For example, if you had classes of box-warning and box-error and wanted to match everything that started with the string `"box-"`, you could use `[class^="box-"]` to select them both (or `[class|="box"]` as described in section above).

| Selector       | Example                 | Description                                                               |
| -------------- | ----------------------- | ------------------------------------------------------------------------- |
| `[attr^=value]`| `li[class^="box-"]`     | Matches elements with an `attr` attribute, whose value begins with `value`.|
| `[attr$=value]`| `li[class$="-box"]`     | Matches elements with an `attr` attribute whose value ends with `value`.   |
| `[attr*=value]`| `li[class*="box"]`      | Matches elements with an `attr` attribute whose value contains `value` anywhere within the string. |

The next example shows usage of these selectors:

- `li[class^="a"]` matches any attribute value which starts with a, so matches the first two list items.
- `li[class$="a"]` matches any attribute value that ends with a, so matches the first and third list item.
- `li[class*="a"]` matches any attribute value where a appears anywhere in the string, so it matches all of our list items.

```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Substring matching selectors</title>
    <style>
      li[class^="a"] {
        font-size: 200%;
      }

      li[class$="a"] {
        background-color: yellow;
      }

      li[class*="a"] {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>Attribute substring matching selectors</h1>
    <ul>
      <li class="a">Item 1</li>
      <li class="ab">Item 2</li>
      <li class="bca">Item 3</li>
      <li class="bcabc">Item 4</li>
    </ul>
  </body>
</html>
```

## Case-sensitivity

If you want to match attribute values case-insensitively **you can use the value `i` before the closing bracket**. This flag tells the browser to match ASCII characters case-insensitively. Without the flag the values will be matched according to the case-sensitivity of the document language — in HTML's case it will be case sensitive.

In the example below, the first selector will match a value that begins with a — it only matches the first list item because the other two list items start with an uppercase A. The second selector uses the case-insensitive flag and so matches all of the list items.

```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Case Sensitivity</title>
    <style>
      li[class^="a"] {
        background-color: yellow;
      }

      li[class^="a" i] {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>Case-insensitivity</h1>
    <ul>
      <li class="a">Item 1</li>
      <li class="A">Item 2</li>
      <li class="Ab">Item 3</li>
    </ul>
  </body>
</html>
```
