##Custom Sidebars Generator
This plugin generates as many sidebars as you need. Then allows you to place them on any page you wish.
* Current version : **2.0 beta**
* Last edit : August 13, 2013 20:14
* Author : Smartik - http://smartik.ws/
 
**Note:** To use this plugin you'll need to modify the source code of your theme or paste the generated shortcode where you want to show a specific sidebar. Read below for instructions.

####How to install this plugin?
Like any other Wordpress plugin. <br />
Drop `smk-sidebar-generator` to `wp-content/plugins/`.<br />
More info here: http://codex.wordpress.org/Managing_Plugins#Installing_Plugins
 
<img src="http://i.imgur.com/hSOdoGc.jpg" />

**Get all sidebars in an array**
```php
if( class_exists('SMK_Sidebar_Generator') ) {
    $the_sidebars = SMK_Sidebar_Generator::get_all_sidebars();
}
```
*result of the above code(example)*
```php
array(
  "sidebarID" => "Default Sidebar",
  "anotherID" => "Sidebar Name",
  "smk_sbg_18" => "Sidebar Name 1",
  "smk_sbg_7" => "Sidebar Name Something"
)
```
*Now you can output this anywhere in page/post metaboxes, theme options, etc.*

*Example with php `foreach`:*
```php
echo '<select>';
  foreach($the_sidebars as $key => $value){
    echo '<option value="'. $key .'">'. $value .'</option>';
  }
echo '</select>';
```


**Display a sidebar using `smk_sidebar` function:**
```php
if(function_exists('smk_sidebar'){
 smk_sidebar('sidebarID');
}
```
**Display a sidebar using wp native function:**
```php
if(function_exists('dynamic_sidebar') && dynamic_sidebar('sidebarID')) : 
				endif;
```

**Display a sidebar using built-in shortcode:**
```php
[smk_sidebar id="18"]
```
*18 is an example, this is the sidebar number, it is created automatically when a new sidebar is generated*

##TO DO:
* Multilanguage support
* Create demo theme

##Releases and Changelog 
https://github.com/Smartik89/Wordpress-Sidebar-Generator/releases
