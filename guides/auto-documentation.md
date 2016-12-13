---
title: How to Auto Document Web Components
summary: "Auto Documentation"
tags: ['beginner']
elements: []
updated: 2016-12-13
---

<style>
.demo {
  background-color: #ccc;
  padding: 4px;
  margin: 12px;
}

.demo div {
  background-color: white;
  padding: 12px;
  margin: 4px;
}

.tall {
  height: 124px;
}

.demo.vertical {
  height: 250px;
}

demo-tabs::shadow #results {
  width: 40%;
  max-width: initial;
}

table {
  margin: 16px 20px;
}
td,th {
  padding 0px 8px;
}
</style>

# How to Document a Web Component


## Summary
Viewing the documentation for an individual web component can be a bit obscure, so this guide will show you how to get it set up.

Note that this is for web components inside the `assets/elements/*` folders.

## Creating the Documentation Page
Add an `index.html` file into the root folder of the component (i.e. `assets/elements/life-events`). Copy and paste the following into the file:

```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <script src="/components/webcomponentsjs/webcomponents-lite.js"></script>
  <link rel="import" href="/components/iron-component-page/iron-component-page.html">
</head>
<body unresolved>
  <!-- Note: if the main element for this repository doesn't
       match the folder name, add a src="&lt;main-component&gt;.html" attribute,
       where &lt;main-component&gt;.html" is a file that imports all of the
       components you want documented. -->
  <iron-component-page></iron-component-page>
</body>
</html>
```

No other changes need to be made to this file (unless the hrefs to `webcomponents-lite.js` or `iron-component-page.html` need to be updated).


## Viewing the Documentation Page
Run `gulp` at the root of the tree-v8 app.

Open the browser to `localhost:5000/elements/<web-component>` to see what documentation already exists (it's automatically generated based on comments in the `<web-component>.html` file).


## Altering the Documentation
Since the documentation is based off of the JSDocs of the html file, any changes to those comments will be reflected in the documentation. The same goes for the automatically generated documentation on the Polymer properties.

For additional guidance visit [Polymer's documentation tools](https://www.polymer-project.org/1.0/docs/tools/documentation).
