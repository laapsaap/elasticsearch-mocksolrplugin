# elasticsearch mocksolrplugin

| Mock Solr Plugin | elasticsearch | Lucene/Solr |
|:----------------:|:-------------:|:-----------:|
| master           | 0.90.3        | 4.4.0       |
| develop          | 0.90.X        | 4.4.0       |

## Overview

This plugin allows you to use elasticsearch with Solr interfaces.
The original project is [here](https://github.com/mattweber/elasticsearch-mocksolrplugin).

## Supported Solr features

* Update handlers
 * XML Update Handler (ie. /update)
 * JavaBin Update Handler (ie. /update/javabin)
* Search handler (ie. /select)
 * Basic lucene queries using the q paramter
 * start, rows, and fl parameters
 * sorting
 * filter queries (fq parameters)
 * hit highlighting (hl, hl.fl, hl.snippets, hl.fragsize, hl.simple.pre, hl.simple.post)
 * faceting (facet, facet.field, facet.query, facet.sort, facet.limit)
* XML and JavaBin request and response formats

## Download

Our plugin download site is [here](http://maven.codelibs.org/org/codelibs/elasticsearch-mocksolrplugin/).

## How do you build this plugin?

Use maven to build the package

    mvn package

Then install the plugin

    # if you've built it locally
    $ES_HOME/bin/plugin -url file:./target/releases/elasticsearch-mocksolrplugin-*.zip -install mocksolrplugin

## How to use this plugin.

Just point your Solr client/tool to your elasticsearch instance and appending /_solr to the url.

    http://localhost:9200/[index]/[type]/_solr

* [index] - the elasticsearch index you want to index/search against. Default "solr".
* [type] - the elasticsearch type you want to index/search against. Default "docs".
