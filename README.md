# Less Compiler Plugin for [Morfy CMS](http://morfy.org/)

Plugin to compile LESS files in Morfy CMS.


## Advantages
- Easy use.
- Cache compiled files.
- Recompile only when changes to the less files.
- Use the [best php class](https://github.com/pafnuty/less.php) for less compile.


## Install
1. Place `less` folder in `plugins` folder into Morfy CMS.
2. Edit `config.php`.


## Configuration
Just add `less` to `plugins` array in `config.php`
```php
# config.php
return array(
    ...
    'plugins' => array(
        'markdown',
        'sitemap',
        'less', // <= Enable Statistics Plugin
    )
    ...
);
```


## Usage
```html
<head>
    ...
    <?php 
    // Run Less Compiler Plugin
    Morfy::factory()->runAction('getCss');
    ?>
    <link rel="stylesheet" href="<?php echo $config['site_url']?>/themes/<?php echo $config['site_theme']?>/assets/css/bootstrap.css" rel="stylesheet">
    ...
</head>
```


## Advanced configuration
**If necessary, you can configure the plugin as needed.**
```php
# config.php
return array(
    ...
    'plugins' => array(
        ...
    ),

    // Less Compiler config ->
    'less' => array(
        // Assets folder into theme folder, which contains a folder less
        // default: '/assets'
        'assetsFolder' => '/custom_styles', 

        // File names for compile without the extension
        // default:  array('bootstrap')
        'fileNames' => array('main'), 

        // Output path for CSS file
        // default: '/css'
        'outputPath' => '/styles', 

        // Compress CSS file
        // default: true
        'compress' => false, 

        // Generate Sourse Map
        // default: false
        'sourceMap' => true, 

    ),
    // <- Less Compiler config
);
```

**If you need to visually make the error output of compilation in accordance with your requirements.**

1. Copy `-less-error.css` from `less` folder to `/themes/PATH_TO_OUR_THEME/PATH_TO_ASSETS_FOLDER/css/` folder into Morfy CMS. 
2. Edit it as necessary.


## License 
[MIT](https://github.com/pafnuty/morfy-less/blob/master/LICENSE)