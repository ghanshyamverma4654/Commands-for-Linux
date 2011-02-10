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

Toggle Word Wrap:
`editor.getSession().setUseWrapMode(true);`

Toggle Highlight line:
`editor.setHighlightActiveLine(false);`

Set to read-only:
`editor.getSession().setReadOnly(true);  // false for the editable` 


Find
`editor.find('needle',{
        backwards: false,
        wrap: false,
        caseSensitive: false,
        wholeWord: false,
        regExp: false
    });`
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
* Set fontsize