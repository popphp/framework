Pop PHP Framework
=================

<img src="http://www.popphp.org/assets/img/pop-php-logo.png" width="180" height="180" />

[![Join the chat at https://discord.gg/TZjgT74U7E](https://media.popphp.org/img/discord.svg)](https://discord.gg/TZjgT74U7E)

* [Overview](#overview)
* [New Features](#new-features)
* [Install](#install)
* [Kettle](#kettle)
* [Support](#support)

Release Information
-------------------
Pop PHP Framework 7.0.0 [Beta]  
Released August TBD, 2026

Overview
--------
This repository contains the `composer.json` file to install the full Pop PHP Framework.
The core Pop PHP components and the additional components below will be installed. For
more information on the full framework and its individual components, visit
[popphp/popphp-framework](https://github.com/popphp/popphp-framework/).

New Features
------------
* A large number of improvements, upgrades and refactors across many components.
* Support for PHP 8.4+.
* PHPUnit tests refactored for PHPUnit 12.5+.
* Reference the [CHANGELOG.md](https://github.com/popphp/popphp-framework/blob/master/CHANGELOG.md) for further details.

Install
-------
There are multiple ways you can get Pop PHP Framework into your project.

##### Option 1: Create a New Project

You can create a new project with the `composer create-project` command, which is recommended.
This way, you will have access to the CLI-helper script `kettle` in the main project folder:

```bash
$ composer create-project popphp/framework project-folder
```

##### Option 2: Clone the Repo

You can clone this repository directly, which will also install the `kettle` script
in the main project folder:

```bash
git clone https://github.com/popphp/framework.git project-folder
cd project-folder
composer install
```

##### Option 3: Use `composer require`

You can add it to an existing project with the `composer require` command:

```bash
composer require popphp/framework
```

##### Option 4: Use `composer.json`

You can add it your project's `composer.json` file:

    "require": {
        "popphp/framework": "^7.0.0"
    }


[Top](#pop-php-framework)

Kettle
------

### CLI Helper

If choose to install the framework in a way that the `pop-kettle` CLI-helper script is not available
in the main project folder (options 3 and 4), you can place a copy of the script from the
`vendor/popphp/pop-kettle/kettle` location in the main project folder (adjacent to the `vendor` folder):

```bash
cp vendor/popphp/pop-kettle/kettle .
cp vendor/popphp/pop-kettle/kettle.inc.php .
```
Once you've copied the scripts over, you have to change the reference to the script's
config file from:

```php
    $app = new Pop\Application(
        $autoloader, include __DIR__ . '/config/app.console.php'
    );
```

to

```php
    $app = new Pop\Application(
        $autoloader, include __DIR__ . '/vendor/popphp/pop-kettle/config/app.console.php'
    );
```

and make sure the newly copied `kettle` script is set to execute (755)

```bash
$ chmod 755 kettle
```

Support
-------

The best way to directly interact with Pop PHP is here on GitHub. You can:

- Contribute code
- Request a feature
- Report an issue

but please do so under the pertinent repository related to the topic at hand. 

Besides interacting with the various repositories here on GitHub, there are
a few other ways to participate in the Pop PHP community:

- [Discord](https://discord.gg/TZjgT74U7E)
- [X](https://x.com/popphpframework)

[Top](#pop-php-framework)
