##Embedding Ace

Ace can be easily embedded into any existing web page. The Ace git repository ships with a pre-packaged version of Ace inside of the build directory. The same packaged files are also available as a separate download. Simply copy the contents of the src subdirectory somewhere into your project and take a look at the included demos of how to use Ace.

The easiest version is simply:

`<div id="editor">some text</div>`
`<script src="src/ace.js" type="text/javascript" charset="utf-8"></script>`
`<script>`
`window.onload = function() {`
`    var editor = ace.edit("editor");`
`};`
`</script>`

To change the theme simply include the Theme's JavaScript file

`<script src="src/theme-twilight.js" type="text/javascript" charset="utf-8"></script>`

and configure the editor to use the theme:

`editor.setTheme("ace/theme/twilight");`


By default the editor only supports plain text mode. However all other language modes are available as separate modules. After including the mode's Javascript file

`<script src="src/mode-javascript.js" type="text/javascript" charset="utf-8"></script>`

the mode can be used like this:

`var JavaScriptMode = require("ace/mode/javascript").Mode;
editor.getSession().setMode(new JavaScriptMode());`

## API
Set content:
`editor.getSession().setValue("the new text here")`

Get content:
`editor.getSession().getValue()`

Get selection:
`editor.getSession().doc.getTextRange(editor.getSelectionRange())`

Go to line:
`editor.gotoLine(line_number)`

Tab size:
`editor.getSession().setTabSize(4);`

Font size:
`document.getElementById('editor').style.fontSize='12px';`

Toggle Word Wrap:
`editor.getSession().setUseWrapMode(true);`

Toggle Highlight line:
`editor.setHighlightActiveLine(false);`

Set to read-only:
`editor.getSession().setReadOnly(true);  // false for the editable` 


Find
`editor.find('needle',{`
`        backwards: false,`
`        wrap: false,`
`        caseSensitive: false,`
`        wholeWord: false,`
`        regExp: false`
`    });`
`editor.findNext();`
`editor.findPrevious();`

Replace
`editor.find('foo');`
`editor.replace('bar');`

Replace All
`editor.replaceAll('bar');`

## Events
OnChange:
`editor.getSession().on('change', callback);`

Selection change
`editor.getSession().selection.on('changeSelection', callback);`

Cursor change
`editor.getSession().selection.on('changeCursor', callback);`

## Still to work out
* Assign key binding to custom function