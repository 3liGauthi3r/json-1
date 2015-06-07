# [Json](http://github.com/yadakhov/json)

A simple wrapper class for Json.

The goal of the package is to provide dot notation syntax to work with Json datatype in PHP.

Use Json as a first class object in PHP.  Use get() or set() to access any elements in the json tree. 

## Installation

<a name="install-composer"/>
### With Composer

```
$ composer require yadakhov/json
```

```json
{
    "require": {
        "yadakhov/json": "~1.0"
    }
}
```

```php
<?php
require __DIR__.'/vendor/autoload.php';

use Yadakhov\Json;


$data = array(
    'developer' => array(
        'firstName' => 'Yada'
    )
);
// Instantiate a new Json object using standard PHP array
$json = new Json($data);

echo $json.PHP_EOL;  // print: {"developer":{"firstName":"Yada"}}

$json->set('developer.lastName', 'Khov');

echo $json.PHP_EOL;  // print: {"developer":{"firstName":"Yada","lastName":"Khov"}}

echo $json->get('developer.firstName').PHP_EOL;  // print: Yada

var_dump($json->toArray());

/*
array(1) {
  ["developer"]=>
  array(2) {
    ["firstName"]=>
    string(4) "Yada"
    ["lastName"]=>
    string(4) "Khov"
  }
}
*/

// It is json JsonSerializable
echo json_encode($json, JSON_PRETTY_PRINT);

/*
{
    "developer": {
    "firstName": "Yada",
        "lastName": "Khov"
    }
}
*/

```

## Dependencies
PHP 5.4 for short array syntax.

This package uses illuminate/support for the array and string helpers. Standing on the shoulders of giants.
