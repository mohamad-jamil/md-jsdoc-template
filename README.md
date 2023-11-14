# Aon JSDoc Template
nhn/tui-jsdoc-template with added enhancements

## Install

```
npm install -D aon-jsdoc-template
```

## Feature

Aon JSDoc template has the following additional features:

* Navigation:
  * AutoComplete Searchbox
  * Collapsible
  * Members / Methods / Events
  * API / Examples (Tutorials) switcher
  * Resizable

![Example](https://cloud.githubusercontent.com/assets/12269563/20049432/69d2ed42-a506-11e6-980e-53b991e5ee5b.png)

### Template

```
"opts": {
    "template": "node_modules/aon-jsdoc-template"
}
```

### Page title

```
"templates": {
    "name": "Aon JSDoc Template"
}
```

### Footer text

```
"templates": {
    "footerText": "My awesome footer text"
}
```

### Use collapsible api list

*Default: `true`*
```
"templates": {
    "useCollapsibles": true
}
```

### Tab Names

```
"templates": {
    "tabNames": {
        "api": "API",
        "tutorials": "Examples"
    }
}
```

`api` defaults to the value `API` and `tutorials` defaults to the value `Examples`.

### Custom Styles

With a folder structure like this:
```
static
└── styles
    └── custom.css
    └── another.css
```
And a config like this:
```js
"templates": {
    "default": {
        "staticFiles": {
            "include": ["static/"]
        }
    },
    "css": [
        "styles/custom.css",
        "styles/another.css",
        "http://example.com/remote.css"
    ]
}
```

`styles/custom.css`, `styles/another.css`, and `remote.css` get included in the layout.
`default.staticFiles` is the build-in jsdoc way of copying extra files.

## Expose the html/js code to example page

If `script` or `div` elements have `code-js` or `code-html` class, expose their innerHTML.

1. innerHTML of `script.code-js` tag
2. innerHTML of `div.code-html` tag

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>example</title>
</head>
<body>
    <div class="code-html">
        <h3> Base Example </h3>
        <p> Hello world </p>
    </div>

    <script class="code-js">
        console.log('hello world');
    </script>
</body>
</html>

```

## Development

1. Use `npm run serve` or `gulp serve` command to ascertain realtime.
3. Api-Example tab, Auto-Complete and Resize functions are written in the `static/scripts/aon-doc.js` file.
