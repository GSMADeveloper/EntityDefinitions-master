### PointOfInterest

This entity contains a harmonised geographic description of a Point of Interest.
This entity is used in applications that use spatial data and is applicable to
Automotive, Environment, Industry and Smart City vertical segments and related
IoT applications.

&lt;PointOfInterest&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**PointOfInterest**".                                                                                                                                                                                                                                                                                                                                                   | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;PointOfInterest&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                           | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| location       | geo:json       | The geo:json encoded map location (point or polygon or multi-polygon), of this point of interest.                                                                                                                                                                                                     | M                                | N           |
| category       | List           | A JSON encoded List of one or more sequence of characters referring to category codes as per the taxonomy definition at <https://github.com/Factual/places/blob/master/categories/factual_taxonomy.json> The respective locale specific category can be accessed via a lookup of the JSON dictionary. | M                                | Y           |
| description    | Text           | An optional description of the entity.                                                                                                                                                                                                                                                                | R                                | Y           |
| place          | Place          | The schema.org place definition for this Point Of Interest. See <https://schema.org/Place>                                                                                                                                                                                                            | R                                | Y           |

#### PointOfInterest JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/4cd7203d66ccf2caf2123cf4519f5f74
```json
{
  "id": "44e47705-90c3-4dbc-a0ae-7810306de5e9",
  "type": "PointOfInterest",
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
  "location": {
    "value": {
      "type": "Point",
      "coordinates": [
        -104.99404,
        39.75621
      ]
    },
    "type": "geo:json"
  },
  "category": {
    "value": [
      "school"
    ],
    "type": "List"
  },
  "description": {
    "value": "Learn all about mobile at the GSMA Academy",
    "type": "Text"
  },
  "place": {
    "type": "Place",
    "value": {
      "name": "GSMA Academy",
      "address": {
        "type": "PostalAddress",
        "addressLocality": "London",
        "postalCode": "EC4N 8AF",
        "streetAddress": "25 Walbrook"
      },
      "telephone": "0212345678"
    }
  }
}
```
