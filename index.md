---
layout: home
---
## WAT?

There are lots of frameworks out there for doing layouts, but most of them require less-than-semantic `<div>` nesting. CSS Grids will help eventually, but the browser support just isn't there yet. Flexbox is here now, but only intended for one-dimensional layouts. With some clever nesting, we can use `flex-direction: column` to make a set of classes (or less/sass mixins) that make single-page application layouts straight forward. No floats, no absolute positioning, just semantic markup.

## The Styles

```css
html, body, .container {
  width: 100%;
  height: 100%;
  margin: 0;
}

.container {
  display: flex;
}

.column {
  display: flex;
  flex-direction: column;
}

.scrollable {
  overflow-y: scroll;
}

.fixed {
  flex-grow: 0;
  flex-shrink: 0;
}

.expandable {
  flex-grow: 1;
}

.compressible {
  flex-shrink: 1;
}
```

## The Markup

```html
<div class="container">
  <div class="column">
    <h1>Sidebar</h1>
    <div class="scrollable">
      <!-- sidebar links -->
    </div>
  </div>
  <div class="column">
    <h1>Main Title</h1>
    <div class="scrollable">
      <!-- body content -->
    </div>
  </div>
</div>
```

## Examples

- [Three Column Layout]({{ '/pages/three-column-app.html' | prepend: site.baseurl }})
- [Four Column Layout]({{ '/pages/four-column-app.html' | prepend: site.baseurl }})
