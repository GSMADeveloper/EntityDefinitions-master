### Building

This entity contains a harmonised description of a Building. This entity is
associated with the vertical segments of smart homes, smart cities, industry and
related IoT applications.

&lt;Building&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**Building**".                                                                                                                                                                                                                                                                                                                                                          | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;Building&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name         | Attribute Type                                     | Description                                                                                                                                                                                                          | Mandatory/ Optional/ Recommended | May be Null |
|------------------------|----------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refBuildingType        | Reference                                          | Refers to the buildingType that this building is an instance of.                                                                                                                                                     | M                                | N           |
| category               | List                                               | One or more categories relevant to the building with choices based on for example <http://wiki.openstreetmap.org/wiki/Map_Features#Building>                                                                         | R                                | Y           |
| containedInPlace       | geo:json                                           | The geo:json encoded polygon of the building plot in which this building sits.                                                                                                                                       | R                                | Y           |
| location               | geo:json                                           | The geo:json encoded polygon of this building.                                                                                                                                                                       | M                                | N           |
| address                | PostalAddress                                      | The building PostalAddress encoded as a Schema.org PostalAddress. [https://schema.org/PostalAddress](https://schema.org/Address)                                                                                     | R                                | Y           |
| owner                  | List of references to Person(s) or Organization(s) | An List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s). Related to a Schema.org person or organization. <https://schema.org/Person https://schema.org/Organization>     | R                                | Y           |
| occupier               | List of references to Person(s) or Organization(s) | An List containing a JSON encoded sequence of characters referencing the unique Ids of the occupiers(s). Related to a Schema.org person or organization. <https://schema.org/Person https://schema.org/Organization> | R                                | Y           |
| refSubscriptionService | List of Reference                                  | An List containing a JSON encoded sequence of characters of the unique Ids of the subscription service(s) related to this building.                                                                                  | O                                | Y           |
| floorsAboveGround      | Number                                             | The number of floors above ground level in this building.                                                                                                                                                            | O                                | Y           |
| floorsBelowGround      | Number                                             | The number of floors below ground level in this building.                                                                                                                                                            | O                                | Y           |
| description            | Text                                               | An optional description of the entity.                                                                                                                                                                               | R                                | Y           |
| mapUrl                 | URL                                                | A URL to a mapping service which shows the location of the building.                                                                                                                                                 | O                                | Y           |
| notes                  | List                                               | Free format notes relating to the building e.g. published occupants, opening hours etc.                                                                                                                              | O                                | Y           |

#### Building JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/69f8893b605894640e3b99f82c3f20ed
```json
{
  "id": "f95c06e3-776e-4a57-9b00-a85e3da145c1",
  "type": "Building",
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
  "refBuildingType": {
    "value": "8b1f2bf0-5093-4182-ad4b-224182bb3b9f",
    "type": "Reference"
  },
  "category": {
    "value": [
      "house"
    ],
    "type": "List"
  },
  "containedInPlace": {
    "value": {
      "type": "Polygon",
      "coordinates": [
        [100, 0],
        [101, 0],
        [101, 1],
        [100, 1],
        [100, 0]
      ]
    },
    "type": "geo:json"
  },
  "location": {
    "value": {
      "type": "Polygon",
      "coordinates": [
        [100, 0],
        [101, 0],
        [101, 1],
        [100, 1],
        [100, 0]
      ]
    },
    "type": "geo:json"
  },
  "address": {
    "type": "PostalAddress",
    "value": {
      "addressLocality": "London",
      "postalCode": "EC4N 8AF",
      "streetAddress": "25 Walbrook"
    }
  },
  "owner": {
    "value": [
      "cdfd9cb8-ae2b-47cb-a43a-b9767ffd5c84",
      "1be9cd61-ef59-421f-a326-4b6c84411ad4"
    ],
    "type": "List"
  },
  "occupier": {
    "value": [
      "9830f692-7677-11e6-838b-4f9fb3dc5a4f"
    ],
    "type": "List"
  },
  "refSubscriptionService": {
    "value": [
      "b4fb8bff-1a8f-455f-8cc0-ca43c069f865onService1",
      "55c24793-3437-4157-9bda-667c9e1531fc"
    ],
    "type": "List
  },
  "floorsAboveGround": {
    "value": 7,
    "type": "Number"
  },
  "floorsBelowGround": {
    "value": 0,
    "type": "Number"
  },
  "description": {
    "value": "Multi-tenant office block",
    "type": "Text"
  },
  "mapUrl": {
    "value": "https://www.google.co.uk/maps/place/The+Walbrook,+Walbrook,+London+EC4N+8AF/@51.5120758,-0.0920769",
    "type": "URL"
  },
  "notes": {
    "value": ["Intelligent entry barrier system", "Intelligent air conditioning units", "Normal opening 07:00 – 20:00"],
    "type": "List"
  }
}
```
