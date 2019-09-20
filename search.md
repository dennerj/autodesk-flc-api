# Search

|Parameter|Value|Default|Comment|
|---|---|---|---|
|query|_search string_||Required.|
|workspace|_number_||Search on a specfic workspace. Multiple workspaces require multiple `workspace` parameters.|
|limit|_number_|10| Optional. Number of results to return.|
|offset|_number_|0| Optional. Number of results "skip". `offset=9` would return the 10th result and up.|
|revision|_number_|1|?|

### Endpoint
```http
GET /v3/search-results?query={query string}
```

### Examples
```http
Searches entire tenant for "test text" and returns 10 results
GET /v3/search-results?query=test text 

Searches entire tenant for "test text" and returns 100 results
GET /v3/search-results?query=test text&limit=100 

Searches workspace 9 for "test text" and returns 10 results
GET /v3/search-results?query=test text&workspace=9 

Searches workspace 9 and 20 for "test text" and returns 10 results
GET /v3/search-results?query=test text&workspace=9&workspace=20 
```
