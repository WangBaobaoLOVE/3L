## 浏览器查看地址和应用程序嵌入

### elasticsearch
```
http://localhost:9200/
```

### kibana
```
http://localhost:5601/app/kibana
```

### kibana -> elasticsearch
```
http://localhost:5601/app/kibana#/dev_tools/console
```

### Java API
```
Package org.elasticsearch.transport.client
```
### Python API
```
下载：pip install elasticsearch
```

```
from datetime import datetime
from elasticsearch import Elasticsearch
# by default we connect to localhost:9200
es = Elasticsearch()
# datetimes will be serialized
es.index(index="my-index", doc_type="test-type", id=42, body={"any": "data", "timestamp": datetime.now()})
{u'_id': u'42', u'_index': u'my-index', u'_type': u'test-type', u'_version': 1, u'ok': True}
# but not deserialized
es.get(index="my-index", doc_type="test-type", id=42)['_source']
{u'any': u'data', u'timestamp': u'2013-05-12T19:45:31.804229'}
```

## 启动和停止服务

### elasticsearch

```
sudo systemctl start elasticsearch.service
sudo systemctl stop elasticsearch.service
```

检查elasticsearch是否运行
```
curl:curl -X GET "localhost:9200/?pretty"
kibana:GET /
```

### kibana

```
sudo systemctl start kibana.service
sudo systemctl stop kibana.service
```

检查kibana的状态
```
http://localhost:5601/status
```

## index or indice

- 查看当前所有索引
    - curl：curl -XGET "http://localhost:9200/_cat/indices?v"
    - kibana：GET /_cat/indices?v
- 删除指定索引
    - curl：curl -XDELETE "http://localhost:9200/eke_work"
    - kibana：DELETE /eke_work


## import file to elasticsearch

### import file with json format

```curl
curl -H "Content-Type: application/json" -XPOST "localhost:9200/bank/_bulk?pretty&refresh" --data-binary "@accounts.json"
```

```curl
curl -H "Content-Type: application/json" -XPOST "localhost:9200/bank/_bulk?pretty&refresh" --data-binary "@<filename>.json"
```

## 错误解决方案

