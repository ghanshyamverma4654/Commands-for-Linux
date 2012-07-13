there is a simple node script to convert textmate themes to ace themes

 * after cloning ace repo do `npm install` or (to make sure `plist` module is available)
 * go to `tool` folder and add textmate theme you want to convert into `tmthemes` folder 
 * update list of [theme names](https://github.com/ajaxorg/ace/blob/master/tool/tmtheme.js#L180) to include your new theme
 * run `node tmtheme.js`

new theme will be added into lib/ace/theme with other ace themes