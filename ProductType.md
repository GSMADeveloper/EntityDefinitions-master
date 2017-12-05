### ProductType

This entity contains a harmonised description of a generic product type. This
entity is primarily associated with the product supply chain verticals and
related IoT applications. The ProductType includes a hierarchical structure that
allows product types to be grouped in a flexible way.

&lt;ProductType&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**ProductType**".                                                                                                                                                                                                                                                                                                                                                       | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;ProductType&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type    | Description                                                                                                                    | Mandatory/ Optional/ Recommended | May be Null |
|----------------|-------------------|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| name           | Text              | The name of this ProductType.                                                                                                  | M                                | N           |
| description    | Text              | A description of this ProductType.                                                                                             | M                                | N           |
| root           | Boolean           | A logical indicator that this product is the root of a ProductType hierarchy. Logical TRUE indicates it is a root.             | M                                | N           |
| refParentType  | List of Reference | A JSON encoded sequence of characters referencing the unique ids of the ProductType groupings this ProductType is a member of. | O                                | Y           |

#### ProductType JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/1cc0398be95ed4287dec068f8bc6da50
```json
{
  "id": "8bd39518-041d-4a9a-8c0c-0bf15d5f07f1",
  "type": "ProductType",
  "dateCreated": {
    "value": "2016-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "dateModified": {
    "value": "2016-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "source": {
    "value": "http://www.example.com",
    "type": "URL"
  },
  "dataProvider": {
    "value": "OperatorA",
    "type": "Text"
  },
  "schemaVersion": {
    "value": "1.0",
    "type": "Text"
  },
  "name": {
    "type": "Text",
    "value": "Refined Palm Oil"
  },
  "description": {
    "type": "Text",
    "value": "Bulk refined palm oil"
  },
  "root": {
    "type": "Boolean",
    "value": true
  },
  "refParentType": {
    "type": "List",
    "value": [
      "66edbb59-90ea-4757-aa06-5a5b95675092"
    ]
  }
}
```
