# Users

The `Accept` header parameter set to `application/json` will return only basic user information on all active users. 
Not setting the parameter will return very detailed information but will be trucated to 10 results. Use URL parameters to return
more information.

```html
GET /v3/users
```

|Parameter|Value|Default|Comment|
|---|---|---|---|
|limit|_number_|10||
|activeOnly|_boolean_|true||
|mappedOnly|_boolean_|true||

```html
GET /v3/users/{user ID}
```
