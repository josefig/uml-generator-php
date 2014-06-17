uml-generator-php
=================

[![Build Status](https://travis-ci.org/clemens-tolboom/uml-generator-php.svg?branch=master)](https://travis-ci.org/clemens-tolboom/uml-generator-php)

Website
-------

Visit our [website](http://clemens-tolboom.github.io/uml-generator-php/).

Installation
------------
Clone the git repository
```
$ git clone git@github.com:clemens-tolboom/uml-generator-php.git
```
Install composer dependencies
```
$ cd uml-generator-php
$ composer install
```
And install graphviz with your distro's package manager or from git. 
uml-generator-php requires graphviz versions later than 15 September 2013 (See [issue #16](https://github.com/clemens-tolboom/uml-generator-php/issues/16))

Usage
-----
To parse your source tree for Class Interface and Traits run

```
$ mkdir tests/output
$ bin/oop2json /Users/clemens/Sites/drupal/d8/www tests/output
```

Next generate their dot files by running

```
$ bin/json2dot -u drupal -d tests/output
```

or even generate SVG files

```
$ bin/json2dot -u drupal -d tests/output | xargs -I {} dot -Tsvg -O {}
```

In case you want to monitor progress use the `xargs -t` switch

```
$ bin/json2dot  -u drupal -d tests/output | xargs -t -I {} dot -Tsvg -O {}
```