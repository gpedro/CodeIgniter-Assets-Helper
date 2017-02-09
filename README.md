CodeIgniter-Assets-Helper
=========================

Helper to load assets (images, stylesheets or javascript).

Requirements
------------
* CodeIgniter should be configured to load `url_helper` automatically.

Installation
------------
Copy `assets_helper.php` into the `applications/helpers` directory and copy `assets.php` into the `applications/config` directory.

Configuration
-------------
You need to set your assets folder for each type (images, stylesheets or javascript). See `applications/config/assets.php` for more information.

Usage
=====

One file without custom attributes:
-----------------------------------
```php
echo assets_css('example.css');

# Results in
<link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/example.css">
```

```php
echo assets_js('example.js');

# Results in
<script type="text/javascript" src="http://www.website.com/assets/js/example.js"></script>
```

```php
echo assets_img('example.png');

# Results in
<img src="http://www.website.com/assets/img/example.png"/>
```

One file with optional custom attributes
```php
echo assets_css('example.css', array('media' => 'screen'));
# Results in
<link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/example.css" media="screen">
```

```php
echo assets_js('example.js', array('charset' => 'utf-8'));
# Results in
<script type="text/javascript" src="http://www.website.com/assets/js/example.js" charset="utf-8"></script>
```

```php
echo assets_img('example.png', array('title' => 'Awesome Helper'));
# Results in
<img src="http://www.website.com/assets/img/example.png" title="Awesome Helper"/>
```

Multiple files, with or without custom attributes
----------------------------------------
```php
$multiple_css = array('example.css', 'style.css');
echo assets_css($multiple_css); 
# Results in
<link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/example.css">
<link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/style.css">
```

```php
$multiple_js = array('example.js', array('style.js', array('charset' => 'utf-8')));
echo assets_js($multiple_js);
# Results in
<script type="text/javascript" src="http://www.website.com/assets/js/example.js"></script>
<script type="text/javascript" src="http://www.website.com/assets/js/style.js" charset="utf-8"></script>
```

```php
$multiple_img = array(array('pic_1.png', array('alt' => 'ranisalt rules')), array('pic_2.jpg', array('title' => 'Awesome Helper')));
echo assets_img($multiple_img);
# Results in
<img src="http://www.website.com/assets/img/pic_1.png" alt="ranisalt rules"/>
<img src="http://www.website.com/assets/img/pic_2.jpg" title="Awesome Helper"/>
```

If you want to use the subfolder
----------------------------------------
Example:
```
        assets /
                site/
                       -css
                       -js
                       -img
                admin/
                       -css
                        -js
                        -img
                sub_one/sub_tow/
                                -css
                                -js
                                -img
```
 In all of the above in the form below:
 ```
 $multiple_img = array(array('site/pic_1.png', array('alt' => 'ranisalt rules')), array('admin/pic_2.jpg', array('title' => 'Awesome Helper')));
# Results in
<img src="http://www.website.com/assets/site/img/pic_1.png" alt="ranisalt rules"/>
<img src="http://www.website.com/assets/admin/img/pic_2.jpg" title="Awesome Helper"/>
```
```
$multiple_css = array('site/s_style.css', 'admin/a_style.css');
echo assets_css($multiple_css); 
# Results in
<link rel="stylesheet" type="text/css" href="http://www.website.com/assets/site/css/s_style.css">
<link rel="stylesheet" type="text/css" href="http://www.website.com/assets/admin/css/a_style.css">
```
```
echo assets_js('sub_one/sub_tow/example.js', array('charset' => 'utf-8'));
# Results in
<script type="text/javascript" src="http://www.website.com/assets/sub_one/sub_tow/js/example.js" charset="utf-8"></script>
```                       
                       
You probably got the hang of it.
