# Run Scripts

Unless stated otherwise, standard header is `Accept application/json` 

## Single Item

The script must be listed in the workspaces Behaviors section of the Workspace Manager. This is the area where you list On Create, On Edit, and On Demand scripts.

`GET v2/scripts/{script ID}/workspace/{workspace ID}/item/{item ID}`

## Multiple Items - USE WITH CAUTION

Running a script on multiple items makes an API call for each record. Making rapid fire API calls on too many records will probably cause problems. How many is too many? I don't know. But you'll know when Autodesk steps in and asks why you're bombarding the servers with API calls.

This procedure uses Postman.

The primary API call is a simple v1 workspace item GET. This will give us a series of items to run the script on.

|Parameter|Value|Default|Comment|
|---|---|---|---|
|size|_number_| 10 | Optional. Number of items to return. |
|filterDeleted| _booleon_| false | Optional |

`GET v1/workspaces/{workspace ID}/items`

`GET v1/workspaces/{workspace ID}/items?size=50?filterDeleted=true`

Paste this code into the Tests tab in Postman.

```js
var jsonResponse = pm.response.json().list;
var dmsIDs = [];

for (var i = 0; i < Object.keys(jsonResponse.item).length; i++) {
    dmsIDs.push(jsonResponse.item[i].id);
    pm.sendRequest("https://{your tenant}.autodeskplm360.net/api/v2/scripts/{script ID}/workspace/{workspace ID}/item/" + dmsIDs[i]), function (err, response) {
        console.log(response.json());
    };
}
```

How it works: Postman will make the primary API call. The response gets saved into the variable `jsonResponse`. Finally the script will loop over each record in the response, extract the dmsID and use it to make the actual v2 script call.

### With a report

This is essentialy the same as above but querying a report returns a diffrent response object.

#### Primary API Call

```GET /v1/reports/{report ID}```

```js
var jsonResponse = pm.response.json().reportResult; // Difference: .reportResult
var dmsIDs = [];

for (var i = 0; i < Object.keys(jsonResponse.row).length; i++) { // Difference: .row
    dmsIDs.push(jsonResponse.row[i].dmsId); // Difference: .dmsId
    pm.sendRequest("https://{your tenant}.autodeskplm360.net/api/v2/scripts/{script ID}/workspace/{workspace ID}/item/" + dmsIDs[i]), function (err, response) {
        console.log(response.json());
    };
}
```
