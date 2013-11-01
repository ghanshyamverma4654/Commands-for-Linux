In brief:

```js
ace.require("ace/ext/language_tools");
var editor = ace.edit("editor");
editor.setOptions({
    enableBasicAutocompletion: true
});
```

Depending on your setup with require-js, you may also need to include an additional javascript file in the html for your page:

```html
<script src="ace/ext-language_tools.js"></script>
```

You can find a demo at [https://github.com/ajaxorg/ace/blob/master/demo/autocompletion.html](https://github.com/ajaxorg/ace/blob/master/demo/autocompletion.html)