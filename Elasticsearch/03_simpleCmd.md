## 添加文档

**命令：**

```
PUT /customer/_doc/1
{
  "name": "John Doe"
}
```

**or**

```
curl -XPUT "http://localhost:9200/customer/_doc/1" -H 'Content-Type: application/json' -d'{  "name": "John Doe"}'
```

**结果:**

```json
{
  "_index" : "customer",
  "_type" : "_doc",
  "_id" : "1",
  "_version" : 4,
  "result" : "updated",
  "_shards" : {
    "total" : 2,
    "successful" : 1,
    "failed" : 0
  },
  "_seq_no" : 3,
  "_primary_term" : 1
}
```

**分析：**

## 获得文档

**命令：**

```
GET /customer/_doc/1
```

**or**

```
curl -X GET "localhost:9200/customer/_doc/1?pretty"
```

**结果:**

```json
{
  "_index" : "customer",
  "_type" : "_doc",
  "_id" : "1",
  "_version" : 5,
  "_seq_no" : 4,
  "_primary_term" : 1,
  "found" : true,
  "_source" : {
    "name" : "John Doe"
  }
}
```

**分析：**

## 批量操作/导入——bulk

**适用：**
1. 1000-5000文档；
2. 内存：5MB-15MB。

**案例：**./data/acount.json

```
curl -H "Content-Type: application/json" -XPOST "localhost:9200/bank/_bulk?pretty&refresh" --data-binary "@accounts.json"
```

