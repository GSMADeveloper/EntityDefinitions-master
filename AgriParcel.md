### AgriParcel

This entity contains a harmonised description of a generic parcel of land. This
entity is primarily associated with the agricultural vertical and related IoT
applications.

&lt;AgriParcel&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**AgriParcel**".                                                                                                                                                                                                                                                                                                                                                        | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;AgriParcel&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name  | Attribute Type                          | Description                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|-----------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| location        | geo:json                                | The geo:json encoded polygon describing this parcel.                                                                                      | M                                | N           |
| area            | Number or ExtQuantitativeValue (Number) | The area of the parcel in square meters encoded as a Number or a ExtQuantitativeValue.                                                    | M                                | N           |
| description     | Text                                    | A description of the parcel.                                                                                                              | R                                | Y           |
| category        | List                                    | A choice of one or more values from an enumerated list describing the parcel category. **greenhouse, irrigated, rainfed.**                | R                                | Y           |
| refAgriCrop     | Reference                               | A reference to the unique id of the AgriCrop associated with this Parcel.                                                                 | M                                | N           |
| cropStatus      | Text                                    | A choice from an enumerated list describing the crop planting status One of: **seeded, justBorn, growing, maturing, readyForHarvesting.** | R                                | Y           |
| refAgriSoil     | Reference                               | A reference to the unique id of the soil associated with this Parcel.                                                                     | O                                | Y           |
| dateLastPlanted | DateTime                                | The ISO8601 sequence of characters at which the AgriCrop was planted in UTC.                                                              | R                                | Y           |
| refDevice       | List of Reference                       | A reference to the unique ids of the Devices used to monitor this parcel.                                                                 | O                                | Y           |

#### AgriParcel JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/b82444f8ace1a379215b0b70a93d0bf5
```json
{
  "id": "72d9fb43-53f8-4ec8-a33c-fa931360259a",
  "type": "AgriParcel",
  "dateCreated": {
    "value": "2016-08-22T10:18:16Z ",
    "type": "DateTime"
  },
  "dateModified": {
    "value": "2016-08-22T10:18:16Z ",
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
  "location": {
    "value": {
      "type": "Polygon",
      "coordinates": [
        [100,0],
        [101,0],
        [101,1],
        [100,1],
        [100,0]
      ]
    },
    "type": "geo:json"
  },
  "area": {
    "value": 2000,
    "type": "Number"
  },
  "description": {
    "value": "North greenhouse (glass)",
    "type": "Text"
  },
  "category": {
    "value": [
      "greenhouse"
    ],
    "type": "List"
  },
  "refAgriCrop": {
    "value": "af3b2a4f-3133-4747-8e00-ba5e4cf1708b",
    "type": "Reference"
  },
  "cropStatus": {
    "value": "seeded",
    "type": "Text"
  },
  "refAgriSoil": {
    "value": "791f80c4-d621-4686-9bc0-84487084b9cf",
    "type": "Reference"
  },
  "dateLastPlanted": {
    "value": "2016-08-09T10:18:16Z",
    "type": "DateTime"
  },
  "refDevice": {
    "value": [
      "276805ff-d3fb-41bf-9714-ed0ecf2ee12b",
      "59b241f5-2827-44ea-bd1f-938567d271ea"
    ],
    "type": "List"
  }
}
```
