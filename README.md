PhpGpio
=======


** PhpGpio** is a simple PHP library to alloww access to the GPIO on the Raspberry Pi.

It provides simple tools such as reading & writing to pins

[![Build Status](https://secure.travis-ci.org/ronanguilloux/PhpGpio.png?branch=master)](http://travis-ci.org/ronanguilloux/PhpGpio)


Installation
------------

The recommended way to install PhpGpio is through [composer](http://getcomposer.org).

Just create a `composer.json` file for your project:

``` json
{
     "require": {
        "php": ">=5.3.0",
        "ronanguilloux/PhpGpio": "master-dev"
    }
}
```

And run these two commands to install it:

``` bash
$ wget http://getcomposer.org/composer.phar
$ php composer.phar install
```

Now you can add the autoloader, and you will have access to the library:

``` php
<?php

require 'vendor/autoload.php';
```

If you don't use neither **Composer** nor a _ClassLoader_ in your application, just require the provided autoloader:

``` php
<?php

require_once 'src/autoload.php';
```


Usage
-----

``` php
<?php
    echo "Setting up Pins 17 and 22\n";
    $gpio = new GPIO();
    $gpio->setup(17, "out");
    $gpio->setup(22, "out");

    echo "Turning on Pins 17 and 22\n";
    $gpio->output(17, 1);
    $gpio->output(22, 1);

    echo "Sleeping!\n";
    sleep(3);

    echo "Turning off Pins 17 and 22\n";
    $gpio->output(17, 0);
    $gpio->output(22, 0);

    echo "Unexporting all pins\n";
    $gpio->unexportAll();
```


Unit Tests
----------

To run unit tests, you'll need `cURL` and a set of dependencies you can install using Composer:

``` bash
$ php composer.phar install --dev
```

Once installed, just launch the following command:

``` bash
$ phpunit
```

Credits
-------

* Aaron Pearce, for the forked pickley/PHP-GPIO project
* Ronan Guilloux <ronan.guilloux@gmail.com>
* [All contributors](https://github.com/ronanguilloux/PhpGpio/contributors)


License
-------

PhpGpio is released under the MIT License. See the bundled LICENSE file for details.
You can find a copy of this software here: https://github.com/ronanguilloux/PhpGpio
