# Filter Example

* Query search:
  ```
  curl -XPOST 'localhost:9200/collisions/_search?pretty=true' \
  -H 'content-type:application/json' \
  -d '{
  "query": {
    "term": { "COUNTY_NAME": "worcester" }
  }
  }'
  ```
* Filter search:
  ```
  curl -XPOST 'localhost:9200/collisions/_search?pretty=true' \
  -H 'content-type:application/json' \
  -d '
  {
  "query": {
    "bool": {
      "filter": {
        "term": { "COUNTY_NAME": "worcester" }
      }
    }
  }
  }'
  ```
* Psst: convert the term value to lower case, or face empty hits.hits response



