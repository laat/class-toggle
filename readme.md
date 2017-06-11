# toggle-class
[![Build Status](https://travis-ci.org/laat/toggle-class.svg?branch=master)](https://travis-ci.org/laat/toggle-class)

> Remove children from DOM-node

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
  var classes = el.className.split(' ');
  var existingIndex = classes.indexOf(className);

  if (existingIndex >= 0)
    classes.splice(existingIndex, 1);
  else
    classes.push(className);

  el.className = classes.join(' ');
}
```

toggle-class:
```javascript
const toggleClass = require('toggle-class');
toggleClass(el, className);
```

## Install

```
$ npm install --save toggle-class
```

## Usage

```javascript
const toggleClass = require('toggle-class');

const div = document.createElement('div')
div.outerHTML
//=> '<div></div>'

toggleClass(div, 'my-class');

div.outerHTML
//=> '<div class="my-class"></div>'

toggleClass(div, 'other-class');

div.outerHTML
//=> '<div class="my-class other-class"></div>'

toggleClass(div, 'my-class');

div.outerHTML
//=> '<div class="other-class"></div>'
```

## License

MIT © [Sigurd Fosseng](https://github.com/laat)
