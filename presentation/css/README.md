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
.item2 { width: 15px; }
.item3 { width: 20px; }
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

## Folder Structure

All CSS files should be stored in the `assets/stylesheets` folder in either the
`app`, `lib`, or `vendor` folder.

### App

The `app` folder is where the majority of a project's CSS will live. It should
contain all CSS specific to the project. This includes all of the site's layout
setup in addition to modules unique to the site's design.

### Lib

The `lib` folder should contain any design patterns that are used throughout the
project. Some examples may include image replacement mixins or inline-block
style lists. Determining whether a pattern belongs in `app` or `lib` can be
difficult, so use your best judgement.

### Vendor

Any CSS used in a third-party plugin should be stored in the `vendor` folder and
should be contained in a folder named after the plugin. For example, the CSS for
Fancybox should be located at `vendor/fancybox/jquery.fancybox.css`.
