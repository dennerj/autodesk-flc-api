# Workspaces

The official documentation of the v3 API is not very accurate or complete. The following infomation is an attempt to fill in the gaps
and provide more detailed information.

## Workspace Types

```html
GET /v3/workspace-types
```

## Workspaces

```html
GET /v3/workspaces
```

|Parameter|Value|Default|Comment|
|---|---|---|---|
|limit|_number|10||
|unlimited|_boolean_|false||

### Specific Workspace

```html
GET /v3/workspaces/{workspace ID}
```

### Fields

```html
GET /v3/workspaces/{workspace ID}/fields
```

## Sections

```html
GET /v3/workspaces/{workspace ID}/sections
```

## Tabs

Not really sure the usefulness of this endpoint by itself. Gives information about the workspace configuration.

```html
GET /v3/workspaces/{workspace ID}/views

GET /v3/workspaces/{workspace ID}/views/{view ID}

GET /v3/workspaces/{workspace ID}/views/{view ID}/fields

GET /v3/workspaces/{workspace ID}/views/{view ID}/fields/{FIELD_NAME}

GET /v3/workspaces/{workspace ID}/views/{view ID}/fields/{FIELD_NAME}/validators
```

## Views

These are the user defined views of the workspace.

```html
GET /v3/workspaces/{workspace ID}/tableaus
```

Seeting the header parameter `Accept` to `application/json/` will return detailed information. Omitting the parameter will
return basic information. 

```html
GET /v3/workspaces/{workspace ID}/tableaus/{tableau ID}
```
