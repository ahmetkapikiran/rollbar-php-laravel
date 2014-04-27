Laravel Rollbar
===============

[![Build Status](https://travis-ci.org/jenssegers/Laravel-Rollbar.svg)](https://travis-ci.org/jenssegers/Laravel-Rollbar) [![Coverage Status](https://coveralls.io/repos/jenssegers/Laravel-Rollbar/badge.png)](https://coveralls.io/r/jenssegers/Laravel-Rollbar)

Rollbar error monitoring integration for Laravel projects.

![rollbar](https://d37gvrvc0wt4s1.cloudfront.net/static/img/features-dashboard1.png?ts=1361907905)

Installation
------------

Add the package to your `composer.json` and run `composer update`.

    {
        "require": {
            "jenssegers/rollbar": "*"
        }
    }

Add the service provider in `app/config/app.php`:

    'Jenssegers\Rollbar\RollbarServiceProvider',

Configuration
-------------

Publish the included configuration file:

    php artisan config:publish jenssegers/rollbar

And change your rollbar access token:

    'token' => '',

Usage
-----

The service provider will make sure all your exceptions and log messages are passed to Rollbar automatically.

    throw new Exception('Something went wrong');

Or if you want to directly send the exception object:

    Log::error(new Exception('Something went wrong'));

Your log messages will also be sent to Rollbar:

    Log::info('Hello Rollbar', array('context'));