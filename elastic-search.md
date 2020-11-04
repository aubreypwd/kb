# Elastic Search

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