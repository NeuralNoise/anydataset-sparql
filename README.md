# SparQL AnyDataset

[![Opensource ByJG](https://img.shields.io/badge/opensource-byjg.com-brightgreen.svg)](http://opensource.byjg.com)
[![Build Status](https://travis-ci.org/byjg/anydataset-sparql.svg?branch=master)](https://travis-ci.org/byjg/anydataset-sparql)

## Description

SparQL abstraction dataset. Anydataset is an agnostic data source abstraction layer in PHP. 

See more about Anydataset [here](https://github.com/byjg/anydataset).

## Examples

### Simple Manipulation

```php
<?php

$sparqlEndpoint = 'http://dbpedia.org/sparql';

$namespace = [
    'dbo' => 'http://dbpedia.org/ontology/',
    'dbp' => 'http://dbpedia.org/property/'
];

$dataset = new \ByJG\AnyDataset\Semantic\SparQLDataset($sparqlEndpoint, $namespace);
$iterator = $dataset->getIterator("select distinct ?Concept where {[] a ?Concept} LIMIT 5");

foreach ($iterator as $row) {
    echo $row->get("Concept");
    echo $row->get("Concept.type");
}
```

## Install

Just type: 

```
composer require "byjg/anydataset-sparql=4.0.*"
```

## Running the Unit tests

```php
vendor/bin/phpunit
```

----
[Open source ByJG](http://opensource.byjg.com)
