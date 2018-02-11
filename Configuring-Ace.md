Core ace components (`editor`, `session`, `renderer`, `mouseHandler`) implement optionProvider interface

    setOption(optionName, optionValue)
    setOptions({
        optionName : optionValue
        ...
    })
    getOption(optionName)
    getOptions()

here's a list of all supported options. Where not indicated otherwise option values are boolean.

### editor options
```
    selectionStyle: "line"|"text"
    highlightActiveLine: true|false
    highlightSelectedWord: true|false
    readOnly: true|false
    cursorStyle: "ace"|"slim"|"smooth"|"wide"
    mergeUndoDeltas: false true "always"
    behavioursEnabled: true|false
    wrapBehavioursEnabled: true|false
    autoScrollEditorIntoView: // this is needed if editor is inside scrollable page
    copyWithEmptySelection: copy/cut the full line if selection is empty, defaults to false
``` 

### renderer options
```
    hScrollBarAlwaysVisible: true|false
    vScrollBarAlwaysVisible: true|false
    highlightGutterLine:
    animatedScroll:
    showInvisibles:
    showPrintMargin:
    printMarginColumn:
    printMargin:
    fadeFoldWidgets:
    showFoldWidgets:
    showLineNumbers:
    showGutter:
    displayIndentGuides:
    fontSize: number or css font-size string
    fontFamily: css 
    maxLines: resize editor based on the contents until the number of lines reaches maxLines
    minLines:
    scrollPastEnd: 
    fixedWidthGutter:
    theme: path to a theme e.g "ace/theme/textmate"
```

### mouseHandler options
```
    scrollSpeed: number
    dragDelay:  number
    dragEnabled:
    focusTimout: number
    tooltipFollowsMouse:
```

### session options
```
    firstLineNumber: number
    overwrite:
    newLineMode:
    useWorker:
    useSoftTabs:
    tabSize: number
    wrap: 
    foldStyle:
    mode: path to a mode e.g "ace/mode/text"
```

## editor options defined by extensions
```js
    enableMultiselect:    # on by default
    enableEmmet: 
    enableBasicAutocompletion:
    enableLiveAutocompletion:   
    enableSnippets:
    spellcheck:
    useElasticTabstops:
```

`editor.setOption` will also modify options of `editor.session`, `editor.renderer` and `editor.$mouseHandler`