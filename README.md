# Elasticsearch cheat sheet


#### CURL

##### Cluster information
1. Get cluster nodes:\
	```curl -S -X GET "http://localhost:9200/_cat/nodes?v"```
2. Get cluster health:\
	```curl -S -X GET 'http://localhost:9200/_cluster/health?pretty=true'```
3. Get cluster indices:\
    ```curl -S -X GET "http://localhost:9200/_cat/indices?v"```
4. Get cluster mappings:\
	```curl -S -X GET "http://localhost:9200/_mapping?pretty"```
6. Get cluster backups:\
	```curl -S -X GET "http://localhost:9200/_snapshot/_all?pretty"```
7. Get information about cluster nodes (configuration plugins,…):\
	```curl -S -X GET "http://localhost:9200/_nodes?pretty"```
8. Get cluster metadata:\
	```curl -S -X GET "http://localhost:9200/?pretty"```
9. Get master node:\
	```curl -S -X GET "http://localhost:9200/_cat/master?v"```
10. Get document count in ES cluster\
	```curl -S -X GET "http://localhost:9200/_cat/count?v"```
11. Get cluster health at indices level:\
	```curl -S -X GET "http://localhost:9200/_cluster/health?level=indices&pretty"```


##### Indices
1. View Index\
	```curl -S -X GET "http://localhost:9200/<index_name>"```
2. Create Index\
	```curl -S -X POST "http://localhost:9200/<index name>"```
3. Delete Index\
	```curl -S -X DELETE "http://localhost:9200/<index name>"```
4. Get Index mappings\
	```curl -S -X GET "http://localhost:9200/<index name>/_mappings?pretty"```
5. Get Index settings\
	```curl -S -X GET "http://localhost:9200/<index name>/_settings"```

##### Documents
1. Retrieve specific document\
	```curl -S -X GET "http://localhost:9200/<index name>/<type>/<id>"```
2. Create document\
	```curl -S -X POST "http://localhost:9200/<index name>/<type>/"```
3. Create/Update specific document\
	```curl -S -X PUT "http://localhost:9200/<index name>/<type>/<id>"```
4. Delete specific document\
	```curl -S -X DELETE "http://localhost:9200/<index name>/<type>/<id>"```




##### Search queries
1. Simple search on all types for indice:\
	```curl -S -XGET "http://localhost:9200/<index name>/_search?pretty"```
2. Search query for field:value:\
	```curl -S -XGET "http://localhost:9200/<index name>/_search?q=field:value"```
3. Search query for field:value and sort by field desc:\
	```curl -S -XGET "http://localhost:9200/<index name>/_search?q=field:value&sort=field:desc&pretty"```
4. Search query for field:value < 30:\
	```curl -S -XGET "http://localhost:9200/<index name>/_search?q=<field>:<30&pretty"```
5. Search query for field:value = value and field:value < 30:\
	```curl -S -XGET "http://localhost:9200/<index name>/_search?q=field:value%20AND%20field:<30&pretty"```
