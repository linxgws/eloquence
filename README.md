# Eloquence

Eloquence is a package to extend Laravel 4's base Eloquent models and functionality.

It allows developers to continue using the PSR-0 standard when dealing with database field names in models. This package will be built on in the future to add more features to the great Eloquent library.


## Installation

Install the package via composer:

    composer require kirkbushell/eloquence ~1.0

## Changelog

#### 1.0.1

* Fixed an issue with dependency resolution

#### 1.0.0

* Initial implementation
* Camel casing of model attributes now available for both setters and getters

## Usage

First, add the eloquence service provider to your config/app.php file:

    'KirkBushell\Eloquence\EloquenceServiceProvider',

Now, update your Eloquent alias to instead point to the Eloquence model version:

    'Eloquent' => 'KirkBushell\Eloquence\Database\Model',

You should now be good to go with your models.

## Options

The default behaviour for Eloquence is to override the default way to access attributes in your models. This is done like so:

    public $enforceCamelCase = true;

You can change this if you need certain models to not use this behaviour, simply by setting it to false:

    public $enforceCamelCase = false;

## Note!

It should be noted that Eloquence DOES NOT CHANGE how you write your schema migrations. You should still be using snake_case when setting up your fields and tables in your database schema migrations.

