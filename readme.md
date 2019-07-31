# class-toggle

[![Build Status](https://travis-ci.org/laat/class-toggle.svg?branch=master)](https://travis-ci.org/laatclass-toggle)

> Toggle class on HTMLElement

## Motivation ([YouMightNotNeedJQuery](http://youmightnotneedjquery.com/#toggle_class))

JQuery:

```javascript
$(el).toggleClass(className);
```

Native (IE 9+):

```javascript
if (el.classList) {
  el.classList.toggle(className);
} else {
  var classes = el.className.split(" ");
  var existingIndex = classes.indexOf(className);

  if (existingIndex >= 0) classes.splice(existingIndex, 1);
  else classes.push(className);

  el.className = classes.join(" ");
}
```

class-toggle:

```javascript
const toggleClass = require("class-toggle");
toggleClass(el, className);
```

native / [polyfill](https://github.com/eligrey/classList.js)

```javascript
el.classList.toggle(className);
```

Protip: **use native / polyfill if possible**

## Install

```
$ npm install --save class-toggle
```

## Usage

```javascript test
const toggleClass = require("class-toggle");

const div = document.createElement("div");
div.outerHTML;
//=> '<div></div>'

toggleClass(div, "my-class");

div.outerHTML;
//=> '<div class="my-class"></div>'

toggleClass(div, "other-class");

div.outerHTML;
//=> '<div class="my-class other-class"></div>'

toggleClass(div, "my-class");

div.outerHTML;
//=> '<div class="other-class"></div>'
```

## License

MIT © [Sigurd Fosseng](https://github.com/laat)
