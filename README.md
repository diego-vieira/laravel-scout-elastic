# Laravel Scout Elasticsearch Driver

[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)

This package makes is the [Elasticsearch](https://www.elastic.co/products/elasticsearch) v6.x driver for Laravel Scout 5.x.

## Contents

- [Installation](#installation)
- [Usage](#usage)
- [Credits](#credits)
- [License](#license)

## Installation

Add to your composer.json

```
"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/diego-vieira/laravel-scout-elastic"
    }
]
```

Then run

``` bash
composer require diego-vieira/laravel-scout-elastic dev-master
```

Unless Laravel 5.5 or above, you must add the Scout service provider and the package service provider in your app.php config:

```php
// config/app.php
'providers' => [
    ...
    Laravel\Scout\ScoutServiceProvider::class,
    ...
    ScoutEngines\Elasticsearch\ElasticsearchProvider::class,
],
```

### Install Laravel Scout
https://laravel.com/docs/5.6/scout#installation

### Set up Elasticsearch configuration
You must have a Elasticsearch server up and running.

If you need help with this please refer to the [Elasticsearch documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)

After you've published the Laravel Scout package configuration:

```php
// config/scout.php
// Set your driver to elasticsearch
    'driver' => env('SCOUT_DRIVER', 'elasticsearch'),

...

'elasticsearch' => [
        'hosts' => [
            [
                'host'   => env('ELASTICSEARCH_HOST', 'localhost'),
                'port'   => env('ELASTICSEARCH_PORT', '9200'),
                'scheme' => env('ELASTICSEARCH_SSL', true) ? 'https' : 'http',
                // 'user'   => 'username',
                // 'pass'   => 'password!#$?*abc'
            ],
        ],
    ],
...
```

## Usage

Now you can use Laravel Scout as described in the [official documentation](https://laravel.com/docs/5.6/scout)

## Credits

- [Erick Tamayo](https://github.com/ericktamayo)  - Fork from
- [Aobo](https://github.com/aobozhang)

## License

The MIT License (MIT).
