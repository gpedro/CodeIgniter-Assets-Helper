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
YYou need to set your assets folder for each type (images, stylesheets or javascript). See `applications/config/assets.php` for more information.

Usage
=====

One file without custom attributes:
-----------------------------------
```php
assets_css('example.css')

# Results in
<link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/example.css">
```

```php
assets_js('example.js')

# Results in
<script type="text/javascript" src="http://www.website.com/assets/js/example.js"></script>
```

```php
assets_img('example.png')

# Results in
<img src="http://www.website.com/assets/img/example.png"/>
```

One file with optional custom attributes
```php
assets_css('example.css', array('media' => 'screen')
# Results in
<link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/example.css" media="screen">
```

```php
assets_js('example.js', array('charset' => 'utf-8')
# Results in
<script type="text/javascript" src="http://www.website.com/assets/js/example.js" charset="utf-8"></script>
```

```php
assets_img('example.png', array('title' => 'Awesome Helper')
# Results in
<img src="http://www.website.com/assets/img/example.png" title="Awesome Helper"/>
```

Multiple files, with or without custom attributes
----------------------------------------
```php
$multiple_css = array('example.css', 'style.css');
assets_css($multiple_css); 
# Results in
<link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/example.css">
<link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/style.css">
```

```php
$multiple_js = array('example.js', array('style.js', array('charset' => 'utf-8')));
assets_js($multiple_js);
# Results in
<script type="text/javascript" src="http://www.website.com/assets/js/example.js"></script>
<script type="text/javascript" src="http://www.website.com/assets/js/style.js" charset="utf-8"></script>
```

```php
$multiple_img = array(array('example.png', array('alt' => 'ranisalt rules')), array('style.css', array('title' => 'Awesome Helper')));
assets_img($multiple_img);
# Results in
<img src="http://www.website.com/assets/img/example.png" alt="ranisalt rules"/>
<img src="http://www.website.com/assets/img/style.css" title="Awesome Helper"/>
```

You probably got the hang of it.
