node-parameterize
=================

parameterize.js is a port of django admin [urlify.js](https://github.com/django/django/blob/master/django/contrib/admin/static/admin/js/urlify.js)

Installing
--------------------------------
npm install parameterize


Supports
--------------------------------
Turkish, Greek, Russian, Ukranian, Czech, Polish, Latvanian and Latin special chars.


Require
--------------------------------
```javascript
var parameterize = require('parameterize');
```


Using
--------------------------------
```javascript
parameterize('parameterized url with special characters, öçıŞÇ');
// parameterized-url-with-special-characters-ocisc
```


Using in express.js 3 view files as view helper
--------------------------------

paste in app.configure in app.js before app.use(app.router)



app.configure
--------------------------------


```javascript
  app.use(function(req, res, next) {
    res.locals.parameterize = parameterize
    next();
  });
  
  app.use(app.router);
```


using with jade template engine
----
index.jade

```html
#{parameterize('parameterized url with special characters, öçıŞÇ')}
// parameterized-url-with-special-characters-ocisc
```


using with ejs template engine
---
index.ejs

```ejs
<% parameterize('parameterized url with special characters, öçıŞÇ') %>
// parameterized-url-with-special-characters-ocisc
```

