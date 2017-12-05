### AgriPest

This entity contains a harmonised description of a generic agricultural pest.
This entity is primarily associated with the agricultural vertical and related
IoT applications.

&lt;AgriPest&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**AgriPest**".                                                                                                                                                                                                                                                                                                                                                          | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;AgriPest&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type    | Description                                                                                                                      | Mandatory/ Optional/ Recommended | May be Null |
|----------------|-------------------|----------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| name           | Text              | The name of this agricultural pest.                                                                                              | M                                | N           |
| alternateName  | Text              | Alternative name of this agricultural pest.                                                                                      | O                                | Y           |
| description    | Text              | A description of this agricultural pest.                                                                                         | R                                | Y           |
| refAgriProduct | List of Reference | An List containing a JSON encoded sequence of characters referencing the unique ids of the recommended AgriProduct pesticide(s). | O                                | Y           |

#### AgriPest JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/df22eca28701a239b49cc744be8eb1ad
```json
{
  "id": "fb3f1295-500c-4aa3-b995-c909097d5c01",
  "type": "AgriPest",
  "dateCreated": {
    "value": "2016-08-22T10:18:16Z",
    "type": "DateTime"
  },
  "dateModified": {
    "value": "2016-08-22T10:18:16Z",
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
    "value": "Grasshopper",
    "type": "Text"
  },
  "alternateName": {
    "value": "Chorthippus parallelus",
    "type": "Text"
  },
  "description": {
    "value": "Common European grasshopper",
    "type": "Text"
  },
  "refAgriProduct": {
    "value": [
      "7f1d962b-0d14-479b-a50a-baaef261263a"
    ],
    "type": "List"
  }
}
```
