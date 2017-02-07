# MDC Toolbar

MDC Toolbar provides an `mdc-toolbar` class for easily styling a RTL-aware
toolbar. The toolbar scrolls with content by default, but supports fixed on
top as well.


## Installation

```
npm install --save @material/toolbar
```


## Usage

Wrap the items with `mdc-toolbar` class in following way:

```html
<div class="mdc-toolbar">
  <div class="mdc-toolbar__section">...</div>
</div>
```

### Fix to top

By default, toolbar scroll with the content, you can add `mdc-toolbar_fixed` to
fix toolbar to the top of screen.

**Body margin required**

You need to wrap contents with `mdc-toolbar_fixed-container-adjust`
when you apply `mdc-toolbar_fixed`, otherwise toolbar will overlay your other
contents. There is no padding applied to this adjust class, so feel free to add
your own padding.

```html
<div class="mdc-toolbar_fixed-container-adjust">
  <div class="mdc-toolbar mdc-toolbar_fixed">
  ...
  </div>
</div>
```

### Sections

By default, the item aligns to the center of the toolbar. You can change the
behavior by applying `mdc-toolbar__section--align-start` or
`mdc-toolbar__section--align-end` to align it to the beginning or ending of the
line.

```html
<div class="mdc-toolbar">
  <div class="mdc-toolbar__section mdc-toolbar__section--align-start">
  Item aligns to start.
  </div>
  <div class="mdc-toolbar__section">
  Item aligns to center.
  </div>
  <div class="mdc-toolbar__section mdc-toolbar__section--align-end">
  Item aligns to end.
  </div>
</div>
```

Behind the scene, we use `flex` for section layout and when you add multiple
sections to the toolbar, each of them will take equal amount of space along
the toolbar.

### Toolbar title

Based on [material design guideline](https://material.io/guidelines/style/typography.html),
toolbar (alias: app bar) use `Title style, Medium 20sp` for its text content.
To maximize flexibility of toolbar, we implemented this style through a wrapper
class:

```html
<div class="mdc-toolbar">
  <div class="mdc-toolbar__section">
    <span class="mdc-toolbar__title">Title</span>
  </div>
</div>
```

### RTL Support

`mdc-toolbar` is automatically RTL-aware, and will re-position elements whenever
it, or its ancestors, has a `dir="rtl"` attribute.


## Classes

### Block

The block class is `mdc-toolbar`. This defines the top-level toolbar element.

### Element
The component has `mdc-toolbar__section` and `mdc-toolbar__title` elements. You
can add multiple sections to toolbar. Refer to Sections and Toolbar title for
further details.

### Modifier

The provided modifiers are:

| Class                                | Description                             |
| -------------------------------------| --------------------------------------- |
| `mdc-toolbar--toolbar_fixed`         | Make toolbar fixed to top of screen.    |
| `mdc-toolbar__section--align-start`  | Makes section aligns to the start.      |
| `mdc-toolbar__section--align-end`    | Makes section aligns to the end.        |

