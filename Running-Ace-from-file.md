to run ace from from `file:///` url, you need to enable local XMLHttpRequests

_firefox:_  from `about:config` set `security.fileuri.strict_origin_policy=false`

_opera:_  `opera:config#UserPrefs|AllowFileXMLHttpRequest`

_chrome:_  start it with `--allow-file-access --allow-file-access-from-files` flags

_safari:_ Enable Develop menu (`Safari->Preferences->Advanced->Show Develop menu in menu bar`), then turn off local file restrictions (`Develop->Disable Local File Restrictions`)

_ie:_  ?