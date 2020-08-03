# _search

## example one

**命令：**

```
GET /bank/_search
{
  "query": { "match_all": {} },
  "sort": [
    { "account_number": "asc" }
  ]
}
```

**or**

```
curl -X GET "localhost:9200/bank/_search?pretty" -H 'Content-Type: application/json' -d'
{
  "query": { "match_all": {} },
  "sort": [
    { "account_number": "asc" }
  ]
}
'
```

**结果：**

```json
{
  "took" : 1,
  "timed_out" : false,
  "_shards" : {
    "total" : 1,
    "successful" : 1,
    "skipped" : 0,
    "failed" : 0
  },
  "hits" : {
    "total" : {
      "value" : 1001,
      "relation" : "eq"
    },
    "max_score" : null,
    "hits" : [
      {
        "_index" : "bank",
        "_type" : "_doc",
        "_id" : "0",
        "_score" : null,
        "_source" : {
          "account_number" : 0,
          "balance" : 16623,
          "firstname" : "Bradshaw",
          "lastname" : "Mckenzie",
          "age" : 29,
          "gender" : "F",
          "address" : "244 Columbus Place",
          "employer" : "Euron",
          "email" : "bradshawmckenzie@euron.com",
          "city" : "Hobucken",
          "state" : "CO"
        },
        "sort" : [
          0
        ]
      }
    ]
  }
}
```

**分析：**

1. **took** – 查询时间，毫秒
2. **timed_out** – 是否超时
3. **_shards** – how many shards were searched and a breakdown of how many shards succeeded, failed, or were skipped.
4. **max_score** – the score of the most relevant document found
5. **hits.total.value** - how many matching documents were found
6. **hits.sort** - the document’s sort position (when not sorting by relevance score)
7. **hits._score** - the document’s relevance score (not applicable when using match_all)

## example two —— from+size

从查询结果的第**from**个开始，返回**size**个。

**命令：**

```
GET /bank/_search
{
  "query": { "match_all": {} },
  "sort": [
    { "account_number": "asc" }
  ],
  "from": 10,
  "size": 10
}
```

**or**

```
curl -X GET "localhost:9200/bank/_search?pretty" -H 'Content-Type: application/json' -d'
{
  "query": { "match_all": {} },
  "sort": [
    { "account_number": "asc" }
  ],
  "from": 10,
  "size": 10
}
'
```

## example three —— match

1. match_all
2. match
3. match_phrase

## example four —— bool

bool: {[must/must_not/should [match]], [filter [range]] }


























