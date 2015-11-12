# Less Compiler Plugin for [Morfy CMS](http://morfy.org/)

![version](https://img.shields.io/badge/version-2.1.0--dev-brightgreen.svg?style=flat-square "Version")
![DLE](https://img.shields.io/badge/Morfy-1.1.x-green.svg?style=flat-square "Morfy Version")
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://raw.githubusercontent.com/pafnuty/morfy-less/master/LICENSE)

Plugin to compile LESS files in Morfy CMS.

**If You use the old version of Morfy :older_man: go to [1.0.0 branch](https://github.com/pafnuty/morfy-less/tree/v1.0.0)**


## Advantages
- Easy use.
- Cache compiled files.
- Recompile only when changes to the less files.
- Use the [best php class](https://github.com/oyejorge/less.php) for less compile.


## Install & Configuration
See [this instruction](http://morfy.org/documentation/plugins/plugins-installation)


## Usage
- Place less files in the folder **/themes/YOUR_THEME/less/**
- Place `{Morfy::runAction('getCss')}` in **layout.tpl** file.

**Example:**

```smarty
{* layout.tpl *}
<head>
    ...
    {Morfy::runAction('getCss')}
    <link href="{$.site.url}/themes/{$.site.theme}/assets/css/bootstrap.css" rel="stylesheet">
    ...
</head>
```


## Advanced configuration
**If necessary, you can configure the plugin as needed.**
```yml
# /plugins/less/less.yml

...
enabled: true
config: 
  assetsFolder: '/styles'
  fileNames: 
    - 'main'
  outputPath: '/styles'
  compress: false
  sourceMap: true
```

<table>
    <tr>
        <th>Variable</th>
        <th>Description</th>
        <th>Default Value</th>
    </tr>
    <tr>
        <td><code>assetsFolder</code></td>
        <td>Assets folder into theme folder, which contains a folder less</td>
        <td><code>/assets</code></td>
    </tr>
    <tr>
        <td><code>fileNames</code></td>
        <td>File names for compile without the extension</td>
        <td><code>array('bootstrap')</code></td>
    </tr>
    <tr>
        <td><code>outputPath</code></td>
        <td>Output path for CSS file</td>
        <td><code>/css</code></td>
    </tr>
    <tr>
        <td><code>compress</code></td>
        <td>Compress CSS file</td>
        <td><code>false</code></td>
    </tr>
    <tr>
        <td><code>sourceMap</code></td>
        <td>Generate Sourse Map</td>
        <td><code>false</code></td>
    </tr>
</table>


**If you need to visually make the error output of compilation in accordance with your requirements.**

1. Copy `-less-error.css` from `less` folder to `/themes/PATH_TO_OUR_THEME/PATH_TO_ASSETS_FOLDER/css/` folder into Morfy CMS. 
2. Edit it as necessary.


## License 
[MIT](https://github.com/pafnuty/morfy-less/blob/master/LICENSE)