# What is the best text color?


A simple helper, helping to determine what color the text will look better over a monotonous color.

<p align="center">
    <img src="/.github/home-page-images/screenshot.png?raw=true" alt="What is the best text color"/>
</p>


[![StyleCI Status][badge_styleci]][link_styleci]
[![Github Workflow Status][badge_build]][link_build]
[![Stable Version][badge_stable]][link_packagist]
[![Unstable Version][badge_unstable]][link_packagist]
[![Total Downloads][badge_downloads]][link_packagist]
[![License][badge_license]][link_license]


## Installation


To get the latest version of package, simply require the project using [Composer](https://getcomposer.org):

```
composer require andrey-helldar/which-color
```

Instead, you may of course manually update your require section and run `composer update` if you so choose:

```json
{
    "require": {
        "andrey-helldar/which-color": "^2.0"
    }
}
```

The package can be used without any problems without any framework, connecting the necessary files through the function `require`.


### Upgrade from 1.x

In the file `composer.json`, replace `"andrey-helldar/black-or-white-text-color": "^1.0"` with `"andrey-helldar/which-color": "^2.0"` and call the `composer update` command.

If you are referring to classes, change the namespace from `Helldar\BlackOrWhiteTextColor` to `Helldar\WhichColor`.

Replace using the `black_is_better_text_color()` and `black_is_better()` helper with the following code:

```php
use Helldar\WhichColor\Services\Color;

return (new Color('#ffffff'))->isDark();
```

## Using


The package helps to determine what color it is better to write text over a monotonous color.

```php
use Helldar\WhichColor\Services\Color;

return (new Color('#000000'))->isLight(); // returned `TRUE`. 'A white text color is better for black background'
return (new Color('#ffffff'))->isDark(); // returned `TRUE`. 'A black text color is better for white background'

return (new Color())->of('#000000')->isLight(); // returned `TRUE`. 'A white text color is better for black background'
return (new Color())->of('#ffffff')->isDark(); // returned `TRUE`. 'A black text color is better for white background'
```

### Laravel / Lumen Frameworks

Inside Laravel or Lumen applications, you can use the `Color` facade:

```php
use Helldar\WhichColor\Facades\Color;

$color = Color::of('#000000');
$color->isLight(); // returned `TRUE`. 'A light text color is better for dark background'
$color->isDark(); // returned `FALSE`. 'A dark text color is better for light background'

$color = Color::of('#ffffff')->isDark();
$color->isLight(); // returned `TRUE`. 'A dark text color is better for light background'
$color->isDark(); // returned `TRUE`. 'A light text color is better for dark background'
```

## Color map

![map of colors](https://user-images.githubusercontent.com/10347617/43231090-85dfba92-9073-11e8-9dbc-d2968b5ef1a2.png)


[badge_build]:          https://img.shields.io/github/workflow/status/andrey-helldar/which-color/phpunit?style=flat-square

[badge_downloads]:      https://img.shields.io/packagist/dt/andrey-helldar/which-color.svg?style=flat-square

[badge_license]:        https://img.shields.io/packagist/l/andrey-helldar/which-color.svg?style=flat-square

[badge_stable]:         https://img.shields.io/github/v/release/andrey-helldar/which-color?label=stable&style=flat-square

[badge_styleci]:        https://styleci.io/repos/142359733/shield

[badge_unstable]:       https://img.shields.io/badge/unstable-dev--main-orange?style=flat-square

[link_build]:           https://github.com/andrey-helldar/which-color/actions

[link_license]:         LICENSE

[link_packagist]:       https://packagist.org/packages/andrey-helldar/which-color

[link_styleci]:         https://github.styleci.io/repos/142359733
