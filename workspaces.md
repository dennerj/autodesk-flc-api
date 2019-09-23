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

Not really sure the usefulness of this endpoint by its self.

```html
GET /v3/workspaces/{workspace ID}/views
```

## Views

```html
GET /v3/workspaces/{workspace ID}/tableaus
```

Seeting the header parameter `Accept` to `application/json/` will return detailed information. Omitting the parameter will
return basic information. 

```html
GET /v3/workspaces/{workspace ID}/tableaus/{tableau ID}
```
