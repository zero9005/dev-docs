# 关于 ELK

>  https://blog.csdn.net/e_wsq/article/details/81303713 
>
>  https://blog.csdn.net/qiushisoftware/article/details/100298046 

## 1、ELK是？

ELK 是elastic公司提供的**一套完整的日志收集以及展示的解决方案**，是三个产品的首字母缩写，分别是ElasticSearch、Logstash 和 Kibana。 

- ElasticSearch简称ES， 是一个实时的分布式搜索和分析引擎，它可以用于全文搜索，结构化搜索以及分析。它是一个建立在全文搜索引擎Apache Lucene基础上的搜索引擎，使用Java语言编写。
- Logstash是一个具有实时传输能力的数据收集引擎，用来进行数据收集(如：读取文本文件)、解析，并将数据发送给ES。
- Kibana为ElasticSearch提供分析和可视化的Web平台。它可以在ElasticSearch的索引中查找，交互数据，并生成各种维度表格、图形。