# Bedrock Autoloader

[![Bedrock Autoloader on Packagist](https://img.shields.io/packagist/v/masonitedoors/bedrock-autoloader.svg?style=flat)](https://packagist.org/packages/masonitedoors/bedrock-autoloader)

Standalone version of the [Bedrock Autoloader](https://github.com/roots/bedrock/blob/1.8.12/web/app/mu-plugins/bedrock-autoloader.php) for must-use plugins.

## Installation

Require this package, with [Composer](https://getcomposer.org), in the root directory of your project.

```sh
composer require masonitedoors/bedrock-autoloader
```

## Usage

In order to add the drop-in file `bedrock-autoloader.php` to your site's `wp-content/mu-plugins/` directory, it is recommended that you use [koodimonni/composer-dropin-installer](https://github.com/Koodimonni/Composer-Dropin-Installer). Once installed, your project's composer.json should look similar to this:

```json
{
  "name": "masonitedoors/my-wordpress-site",
  "type": "project",
  "license": "GPL-2.0-or-later",
  "require": {
    "koodimonni/composer-dropin-installer": "*",
    "php": "^7.0",
    "composer/installers": "^1.4",
    "roots/wordpress": "5.4",
    "masonitedoors/bedrock-autoloader": "dev-master"
  },
  "extra": {
    "wordpress-install-dir": "html",
    "installer-paths": {
      "html/wp-content/mu-plugins/{$name}/": [
        "type:wordpress-muplugin",
      ],
      "html/wp-content/plugins/{$name}/": [
        "type:wordpress-plugin"
      ],
      "html/wp-content/themes/{$name}/": [
        "type:wordpress-theme"
      ]
    },
    "dropin-paths": {
      "html/wp-content/mu-plugins/": [
        "package:masonitedoors/bedrock-autoloader:bedrock-autoloader.php"
      ]
    }
  },
  "config": {
    "dropin-installer": "copy"
  }
}
```

## Credits

All credits & copyrights belongs to people behind [Bedrock](https://github.com/roots/bedrock).
