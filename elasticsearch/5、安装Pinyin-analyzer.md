# 5、安装Pinyin-analyzer

```shell
> unzip elasticsearch-analysis-pinyin-x.y.z.zip -d ./pinyin/
> mv pinyin /opt/elasticsearch-x.y.z/plugins
```



## 映射

```shell
curl -put "http://localhost:9200/{index}" -d {
	"settings": {
        "number_of_replicas": 0,
        "number_of_shards": 1,
        "analysis": {
            "analyzer": {
                "ik_pinyin_analyzer": {
                    "type": "custom",
                    "tokenizer": "ik_max_word",
                    "filter": ["my_pinyin", "word_delimiter"]
                }
            },
            "filter": {
                "my_pinyin": {
                    "type": "pinyin",
                    "first letter": "prefix",
                    "padding_char": " "
                }
            }
        }    
      },
      "mappings": {

          "properties": {
              "name": {
                  "type": "text",
                  "analyzer": "ik_pinyin_analyzer",
                  "search_analyzer" : "ik_pinyin_analyzer"
              },
              "suggest": {
                    "type": "completion",
                    "analyzer": "ik_pinyin_analyzer",
                    "search_analyzer" : "ik_pinyin_analyzer"
              }

          }
  	}  
}
```

