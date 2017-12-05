### AgriSoil

This entity contains a harmonised description of soil. This entity is primarily
associated with the agricultural vertical and related IoT applications.

&lt;AgriSoil&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**AgriSoil**".                                                                                                                                                                                                                                                                                                                                                          | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;AgriSoil&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type    | Description                                                                                                                                          | Mandatory/ Optional/ Recommended | May be Null |
|----------------|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| name           | Text              | The name of this soil type.                                                                                                                          | M                                | N           |
| alternateName  | Text              | Alternative name of this soil type.                                                                                                                  | O                                | Y           |
| description    | Text              | A description of this soil.                                                                                                                          | R                                | Y           |
| refAgriProduct | List of Reference | An List containing a JSON encoded sequence of characters referencing the unique ids of the recommended AgriProduct fertiliser (or other) product(s). | O                                | Y           |

#### AgriSoil JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/a3eae9503c856c835b56c8c98603cd5f
```json
{
  "id": "789363b4-c771-43d6-8505-ca582efe8fcd",
  "type": "AgriSoil",
  "dateCreated": {
    "value": "2016-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "dateModified": {
    "value": "2016-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "source": {
    "value": "http://www.samplefarmproduct.com",
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
    "value": "Clay",
    "type": "Text"
  },
  "alternateName": {
    "value": "Heavy soil",
    "type": "Text"
  },
  "description": {
    "value": "Fine grained, poor draining soil. Particle size less than 0.002mm",
    "type": "Text"
  },
  "refAgriProduct": {
    "value": [
      "ea54eedf-d5a7-4e44-bddd-50e9935237c0",
      "275b4c08-5e52-4bb7-8523-74ce5d0007de"
    ],
    "type": "List"
  }
}
```
