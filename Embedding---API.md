## API
Set content:
`editor.getSession().getDocument().setValue("the new text here")`

Get content:
`editor.getSession().getDocument().getValue()`

Go to line:
`editor.gotoLine(line_number)`

Tab size:
`editor.getSession().setTabSize(4);`

Word Wrap:
`editor.getSession().setUseWrapMode(true);`

Highlight line:
`editor.setHighlightActiveLine(false);`

## Events
OnChange:
`editor.getSession().doc.on('change', callback);`

Selection change
`editor.getSession().selection.on('changeSelection', callback);`

Cursor change
`editor.getSession().selection.on('changeCursor', callback);`

## Still to work out
* Find API
* Get selected text
* Assign key binding
* Fontsize