# CSS Guidelines

---

## Whitespace

* Use soft tabs (spaces) with a tab size of two spaces.
* Never mix tabs and spaces.
* Delete trailing whitespace.

## Formatting

* Put a single space before `{` in rule declarations.
* Put a single space after `:` in property declarations.
* Use lowercase hex values, e.g. `#eebc9a`.
* Use shorthand hex values when possible, e.g. `#000`.
* Separate each rule by a single blank line.
* Separate each comma-separated value with a space, e.g. `rgba(0, 0, 0, 0.5)`.
* Use single quotes, e.g. `background: url('/img/pattern.png')`.
* Use quotes in selectors with attribute values, e.g. `input[type='checkbox']`.
* Use shorthand properties when possible, e.g. `padding: 10px 20px`.
* Avoid specifying units for values of zero, e.g. `margin: 0 10px 0 25px`.

### Vendor Prefixes

Align multiple vendor-prefixed rules so the values line up.

```css
.box {
  -webkit-box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
     -moz-box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
          box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
}
```

### Exceptions

Numerous rules with single declarations should be written on a single line. One
space should be placed after the opening brace and before the closing brace.
This can be helpful when making single adjustments to multiple selectors.

```css
.item1,
.item2,
.item3 {
  float: left;
  margin-right: 10px;
}

.item1 { width: 10px; }
.item2 { width: 20px; }
.item3 { width: 10px; }
```

Comma-separated values should be broken up onto multiple lines and indented one
level further than the property.

```css
.callout {
  background:
    url('/img/gradient.png') left top repeat-x,
    url('/img/noise.png') left top repeat;
  box-shadow:
    0 0 10px #222,
    0 0 10px #ccc inset;
}
```
