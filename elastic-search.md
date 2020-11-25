# Elastic Search

## Creating an Index

- [See https://www.elastic.co/guide/en/elasticsearch/.../indices-create-index.html](https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-create-index.html)

```
PUT /my-index-000001
```

## Listing Indices

```
GET /_cat/indices
```

## Query by Post Type

```
GET /wds-raceraves-test-aubreypwd/_search
{
  "query": {
    "match": {
      "post_type": {
        "query": "race"
      }
    }
  }
}
```

## Example Index Query

```
GET /aubreypwdraceravestest-1/_search
{
  "query" : {
    "query_string" : {
      "query" : "mountain"
    }
  }
}
```

This will act as if you searched the entire index for `mountain`. And you'll get something similar to:

```json
{
  "took" : 57,
  "timed_out" : false,
  "_shards" : {
    "total" : 1,
    "successful" : 1,
    "skipped" : 0,
    "failed" : 0
  },
  "hits" : {
    "total" : {
      "value" : 3901,
      "relation" : "eq"
    },
    "max_score" : 6.6349607,
    "hits" : [...]
  }
}
```

Where `hits` will be filled with items.

- [See https://www.elastic.co/guide/...y.html#_reserved_characters](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-query-string-query.html#_reserved_characters)
