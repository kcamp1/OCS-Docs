---
uid: Data RetrievalApi
---

# Data Retrieval

APIs for Retrieving Data

***

## `Get Data View Data`

Get data for the provided index parameters with paging

### Request
`GET api/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/data/interpolated`

### Parameters

Id of tenant:
```csharp
string tenantId  [Required] [No Default Value]
```


Id of namespace:
```csharp
string namespaceId  [Required] [No Default Value]
```


Id of dataview:
```csharp
string id  [Required] [No Default Value]
```


Start time of the data:
```csharp
string startIndex [FromQuery] [Required] [No Default Value]
```


End time of the data:
```csharp
string endIndex [FromQuery] [Required] [No Default Value]
```


Data interval:
```csharp
string interval [FromQuery] [Required] [No Default Value]
```


Cache:
```csharp
string cache [FromQuery] [Required] [No Default Value]
```


Data form:
```csharp
string form [FromQuery] [Required] [No Default Value]
```


Paging Token:
```csharp
string continuationToken [FromQuery] [Required] [No Default Value]
```


Count of data points to retrieve per page:
```csharp
Int32 pageSize [FromQuery] [Optional] [Default = 1000]
```


Cancellation token:
```csharp
CancellationToken cancellationToken  [Optional] [Default = ""]
```


### Returns

#### 200

Successfully retrieved data. Return type: ContentResult

```json
Returns data formatted according to the user settings. Output formats: Default, Table, Tableh, Csv, Csvh
```

#### 400

Bad request


#### 403

Unauthorized


#### 404

Specified data view Id not found


#### 500

Internal server error

***

## `Get Data Groups`

Get Data Groups for a specified Data View

### Request
`GET api/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/datagroups`

### Parameters

Id of tenant:
```csharp
string tenantId  [Required] [No Default Value]
```


Id of namespace:
```csharp
string namespaceId  [Required] [No Default Value]
```


Id of dataview:
```csharp
string id  [Required] [No Default Value]
```


The number of items to skip:
```csharp
Int32 skip [FromQuery] [Required] [No Default Value]
```


The number of items to display per page:
```csharp
Int32 count [FromQuery] [Required] [No Default Value]
```


Cache behavior to use:
```csharp
string cache  [Required] [No Default Value]
```


Cancellation token:
```csharp
CancellationToken cancellationToken  [Optional] [Default = ""]
```


### Returns

#### 200

Successfully retrieved data. Return type: DataGroupCollection

```json
{
  "TimeOfResolution": "TimeOfResolution",
  "Errors": {
    "OperationId": "OperationId",
    "Error": "Error",
    "Reason": "Reason",
    "Resolution": "Resolution",
    "AdditionalParameters": {
      "Chars": "Chars",
      "Length": "Length"
    }
  },
  "DataGroups": {
    "TimeOfResolution": "TimeOfResolution",
    "Id": "Id",
    "ItemCount": "ItemCount",
    "Errors": {
      "OperationId": "OperationId",
      "Error": "Error",
      "Reason": "Reason",
      "Resolution": "Resolution",
      "AdditionalParameters": {
        "Chars": "Chars",
        "Length": "Length"
      }
    },
    "Tokens": {
      "Chars": "Chars",
      "Length": "Length"
    },
    "DataItems": {
      "ItemType": "ItemType enumeration",
      "Id": "Id",
      "Name": "Name",
      "TenantId": "TenantId",
      "NamespaceId": "NamespaceId"
    }
  }
}
```

#### 207

Multi-status. Look at response message. Return type: DataGroupCollection

```json
{
  "TimeOfResolution": "TimeOfResolution",
  "Errors": {
    "OperationId": "OperationId",
    "Error": "Error",
    "Reason": "Reason",
    "Resolution": "Resolution",
    "AdditionalParameters": {
      "Chars": "Chars",
      "Length": "Length"
    }
  },
  "DataGroups": {
    "TimeOfResolution": "TimeOfResolution",
    "Id": "Id",
    "ItemCount": "ItemCount",
    "Errors": {
      "OperationId": "OperationId",
      "Error": "Error",
      "Reason": "Reason",
      "Resolution": "Resolution",
      "AdditionalParameters": {
        "Chars": "Chars",
        "Length": "Length"
      }
    },
    "Tokens": {
      "Chars": "Chars",
      "Length": "Length"
    },
    "DataItems": {
      "ItemType": "ItemType enumeration",
      "Id": "Id",
      "Name": "Name",
      "TenantId": "TenantId",
      "NamespaceId": "NamespaceId"
    }
  }
}
```

#### 403

Unauthorized


#### 404

Specified Data View Id not found


#### 500

Internal server error

***

## `Get Data Group`

Get a specific Data Group

### Request
`GET api/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/dataGroups/{dataGroupId}`

### Parameters

Id of tenant:
```csharp
string tenantId  [Required] [No Default Value]
```


Id of namespace:
```csharp
string namespaceId  [Required] [No Default Value]
```


Id of Data View:
```csharp
string id  [Required] [No Default Value]
```


Id of the data group:
```csharp
string dataGroupId  [Required] [No Default Value]
```


Cache behavior to use:
```csharp
string cache  [Required] [No Default Value]
```


Cancellation token:
```csharp
CancellationToken cancellationToken  [Optional] [Default = ""]
```


### Returns

#### 200

Successfully retrieved data group. Return type: DataGroup

```json
{
  "TimeOfResolution": "TimeOfResolution",
  "Id": "Id",
  "ItemCount": "ItemCount",
  "Errors": {
    "OperationId": "OperationId",
    "Error": "Error",
    "Reason": "Reason",
    "Resolution": "Resolution",
    "AdditionalParameters": {
      "Chars": "Chars",
      "Length": "Length"
    }
  },
  "Tokens": {
    "Chars": "Chars",
    "Length": "Length"
  },
  "DataItems": {
    "ItemType": "ItemType enumeration",
    "Id": "Id",
    "Name": "Name",
    "TenantId": "TenantId",
    "NamespaceId": "NamespaceId"
  }
}
```

#### 403

Unauthorized


#### 404

Specified Data View Id not found


#### 500

Internal server error

***

## `Get Data Mappings`

Get mappings for a dataview by Id

### Request
`GET api/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/datamappings`

### Parameters

Id of the dataview:
```csharp
string id  [Required] [No Default Value]
```


Cache behavior to use:
```csharp
string cache [FromQuery] [Required] [No Default Value]
```


Cancellation Token:
```csharp
CancellationToken cancellationToken  [Optional] [Default = ""]
```


### Returns

#### 200

Successfully retrieved data mappings. Return type: Mappings

```json
{
  "SharedMappingRules": {
    "Id": "Id",
    "Token": "Token",
    "MappingRulePattern": {
      "PropertyPaths": {
        "Chars": "Chars",
        "Length": "Length"
      },
      "ItemIdentifier": {
        "FilterResource": "FilterResource enumeration",
        "FilterField": "FilterField enumeration",
        "Name": "Name",
        "Value": "Value",
        "FilterFunction": "FilterFunction enumeration"
      }
    }
  },
  "Columns": {
    "Name": "Name",
    "NamespaceId": "NamespaceId",
    "MappingRule": {},
    "IsKey": "IsKey",
    "DataType": "DataType",
    "UOM": "UOM"
  },
  "IsDefault": "IsDefault"
}
```

#### 403

Unauthorized


#### 404

Specified data view Id not found


#### 500

Internal server error

***

## `Get DataItems`

Get data items for a dataview by Id

### Request
`GET api/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/dataitems`

### Parameters

Id of the dataview:
```csharp
string id  [Required] [No Default Value]
```


The number of items to skip:
```csharp
Int32 skip [FromQuery] [Required] [No Default Value]
```


The number of items to display per page:
```csharp
Int32 count [FromQuery] [Required] [No Default Value]
```


Cache behavior to use:
```csharp
string cache [FromQuery] [Required] [No Default Value]
```


Cancellation Token:
```csharp
CancellationToken cancellationToken  [Optional] [Default = ""]
```


### Returns

#### 200

Successfully retrieved data items. Return type: DataItemCollection

```json
{
  "TimeOfResolution": "TimeOfResolution",
  "Count": "Count",
  "Items": {
    "ItemType": "ItemType enumeration",
    "Id": "Id",
    "Name": "Name",
    "TenantId": "TenantId",
    "NamespaceId": "NamespaceId"
  }
}
```

#### 403

Unauthorized


#### 404

Specified data view Id not found


#### 500

Internal server error

***

## `Get Statistics`

Get statistics for a dataview by Id

### Request
`GET api/tenants/{tenantId}/namespaces/{namespaceId}/dataviews/{id}/statistics`

### Parameters

Id of the dataview:
```csharp
string id  [Required] [No Default Value]
```


Cache behavior to use:
```csharp
string cache [FromQuery] [Required] [No Default Value]
```


Cancellation Token:
```csharp
CancellationToken cancellationToken  [Optional] [Default = ""]
```


### Returns

#### 200

Successfully retrieved data view statistics. Return type: DataViewInstanceStatistics

```json
{
  "TimeOfResolution": "TimeOfResolution",
  "DataItemsCount": "DataItemsCount",
  "DataGroupsCount": "DataGroupsCount",
  "ColumnCount": "ColumnCount"
}
```

#### 403

Unauthorized


#### 404

Specified data view Id not found


#### 500

Internal server error

***

