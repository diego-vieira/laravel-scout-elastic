# Laravel Scout Elasticsearch Driver

[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)

This package makes is the [Elasticsearch](https://www.elastic.co/products/elasticsearch) v6.x driver for Laravel Scout 4.x.

## Contents

- [Installation](#installation)
- [Usage](#usage)
- [Credits](#credits)
- [License](#license)

## Installation

You can install the package via composer:

``` bash
composer require C10ne/laravel-scout-elastic @dev
```

Unless Laravel 5.5 or Above, You must add the Scout service provider and the package service provider in your app.php config:

```php
// config/app.php
'providers' => [
    ...
    Laravel\Scout\ScoutServiceProvider::class,
    ...
    ScoutEngines\Elasticsearch\ElasticsearchProvider::class,
],
```

### Setting up Elasticsearch configuration
You must have a Elasticsearch server up and running with the index you want to use created

If you need help with this please refer to the [Elasticsearch documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)

After you've published the Laravel Scout package configuration:

```php
// config/scout.php
// Set your driver to elasticsearch
    'driver' => env('SCOUT_DRIVER', 'elasticsearch'),

...

'elasticsearch' => [
        'default_index' => env('ELASTICSEARCH_INDEX', 'default'),
        'index_prefix'  => env('ELASTICSEARCH_INDEX_PREFIX', true),
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

Now you can use Laravel Scout as described in the [official documentation](https://laravel.com/docs/5.3/scout)
## Credits

- [Erick Tamayo](https://github.com/ericktamayo)  - Fork from
- [Aobo](https://github.com/aobozhang)

## License

The MIT License (MIT).
