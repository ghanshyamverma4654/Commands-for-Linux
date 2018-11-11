Core ace components (`editor`, `session`, `renderer`, `mouseHandler`) implement optionProvider interface

    setOption(optionName, optionValue)
    setOptions({
        optionName : optionValue
        ...
    })
    getOption(optionName)
    getOptions()

here's a list of all supported options. Where not indicated otherwise option values are boolean.

`editor.setOption` will also modify options of `session/renderer/$mouseHandler` associated with it


### editor options

    selectionStyle: "line"|"text"
    highlightActiveLine: true|false
    highlightSelectedWord: true|false
    readOnly: true|false
    cursorStyle: "ace"|"slim"|"smooth"|"wide"
    mergeUndoDeltas: false|true|"always"
    behavioursEnabled: boolean
    wrapBehavioursEnabled: boolean
    // this is needed if editor is inside scrollable page
    autoScrollEditorIntoView: boolean (defaults to false)
    // copy/cut the full line if selection is empty, defaults to false
    copyWithEmptySelection: boolean 
    useSoftTabs: boolean (defaults to false)
    navigateWithinSoftTabs: boolean (defaults to false)
    enableMultiselect: boolean   # on by default
 
### renderer options
 
    hScrollBarAlwaysVisible: boolean
    vScrollBarAlwaysVisible: boolean
    highlightGutterLine: boolean
    animatedScroll: boolean
    showInvisibles: boolean
    showPrintMargin: boolean
    printMarginColumn: number (defaults to 80)
    // shortcut for showPrintMargin and printMarginColumn
    printMargin: false|number 
    fadeFoldWidgets: boolean
    showFoldWidgets: boolean (defaults to true)
    showLineNumbers: boolean (defaults to true)
    showGutter: boolean (defaults to true)
    displayIndentGuides: boolean (defaults to true)
    fontSize: number or css font-size string
    fontFamily: css font-family value
    // resize editor based on the contents of the editor until the number of lines reaches maxLines
    maxLines: number
    minLines: number
    // number of page sizes to scroll after document end (typical values are 0, 0.5, and 1)
    scrollPastEnd: number|boolean
    fixedWidthGutter: boolean (defaults to false)
    theme: path to a theme e.g "ace/theme/textmate"
 

### mouseHandler options
 
    scrollSpeed: number
    dragDelay:  number
    dragEnabled: boolean (defaults to true)
    focusTimout: number
    tooltipFollowsMouse: boolean
 
### session options
 
    firstLineNumber: number defaults to 1
    overwrite: boolean
    newLineMode: "auto" | "unix" | "windows"
    useWorker: boolean
    useSoftTabs: boolean
    tabSize: number
    wrap: boolean|number
    foldStyle: "markbegin"|"markbeginend"|"manual"
    mode: path to a mode e.g "ace/mode/text"
 

## editor options defined by extensions

to use this options the corresponding extension file needs to be loaded in addition to the ace.js

    // following options require ext-language_tools.js
    enableBasicAutocompletion: boolean
    enableLiveAutocompletion:   boolean
    enableSnippets: boolean
    // the following option requires ext-emmet.js and the emmet library 
    enableEmmet: boolean
    // the following option requires ext-elastic_tabstops_lite.js
    useElasticTabstops: boolean
 
