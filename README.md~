CodeIgniter-Assets-Helper
=========================

Helper to load assets (img, css or js).

## Requirements
* CodeIgniter configured to autoload `url_helper`

## Installation
Copy and Paste `assets_helper.php` to your `applications/helpers` and `assets.php` to `applications/config`.

## Configuration
You need set your assets base, css, img and js folder. See `applications/config/assets.php`.

##Usage

####Once file without custom attributes
```php
assets_css('example.css')
# Returns: <link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/example.css">

assets_js('example.js')
# Returns: <script type="text/javascript" src="http://www.website.com/assets/js/example.js"></script>

assets_img('example.png')
# Returns: <img src="http://www.website.com/assets/img/example.png"/>
```

#### Once file with custom attributes
```php
assets_css('example.css', array('media' => 'screen')
# Returns: <link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/example.css" media="screen">

assets_js('example.js', array('charset' => 'utf-8')
# Returns: <script type="text/javascript" src="http://www.website.com/assets/js/example.js" charset="utf-8"></script>

assets_img('example.png', array('title' => 'Awesome Helper')
# Returns: <img src="http://www.website.com/assets/img/example.png" title="Awesome Helper"/>
```

#### Multiple files without custom attributes
```php
$multiple_css = array('example.css', 'style.css');
assets_css($multiple_css); 
# Returns:
# <link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/example.css">
# <link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/style.css">

$multiple_js = array('example.js', 'style.js');
assets_js($multiple_css); 
# Returns:
# <script type="text/javascript" src="http://www.website.com/assets/js/example.js"></script>
# <script type="text/javascript" src="http://www.website.com/assets/js/style.js"></script>

$multiple_img = array('example.png', 'style.png');
assets_img($multiple_img); 
# Returns:
# <img src="http://www.website.com/assets/img/example.png"/>
# <img src="http://www.website.com/assets/img/style.png"/>
```

#### Multiple files with custom attributes
```php
$multiple_css = array('example.css', array('style.css', array('media' => 'screen')));
assets_css($multiple_css);
# Returns:
# <link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/example.css">
# <link rel="stylesheet" type="text/css" href="http://www.website.com/assets/css/style.css" media="screen">

$multiple_js = array('example.js', array('style.js', array('charset' => 'utf-8')));
assets_js($multiple_js);
# Returns:
#<script type="text/javascript" src="http://www.website.com/assets/js/example.js"></script>
#<script type="text/javascript" src="http://www.website.com/assets/js/style.js" charset="utf-8"></script>

$multiple_img = array('example.png', array('style.css', array('title' => 'Awesome Helper')));
assets_img($multiple_img);
# Returns:
#<img src="http://www.website.com/assets/img/example.png"/>
#<img src="http://www.website.com/assets/img/style.css" title="Awesome Helper"/>

```

##License
[See more](https://github.com/gpedro/CodeIgniter-Assets-Helper/blob/master/LICENSE)
