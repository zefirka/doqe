# doqe

## Usage 

### doqefile.js

```js

var doqe = require('doqe');

doqe.set('mp', doqe.library(['method', 'property']));

doqe.set('front', doqe.library({
  Angular: {
    Directives: {
     Directive : doqe.get('mp'),
     Dependencies : doqe.link()
    },
    Secrvies : {
      Service: doqe.get('mp'),
      Dependencies : doqe.link()
    },
    Controllers : {
      Controller : doqe.get('mp'),
      Dependencies : doqe.link()
    }
  },
  CSS : {
    Blocks : {
      Block : 'rules'
    }
  },
  Launcher : 'static'
}));

doqe.books({
  front : doqe.get('front'),
  back : doqe.get('back')
}).main('front');

module.exports = doqe.export();
```
