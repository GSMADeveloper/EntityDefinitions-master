### RoadSegment

This entity contains a harmonised geographic and contextual description of a
RoadSegment. A collection of RoadSegments are used to describe a Road. This
entity is primarily associated with the Automotive and Smart City vertical
segments and related IoT applications.

&lt;RoadSegment&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**RoadSegment**".                                                                                                                                                                                                                                                                                                                                                       | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;RoadSegment&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name     | Attribute Type    | Description                                                                                                                     | Mandatory/ Optional/ Recommended | May be Null |
|--------------------|-------------------|---------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| startPoint         | geo:json          | The start point of this RoadSegment.                                                                                            | M                                | N           |
| endPoint           | geo:json          | The end point of this RoadSegment.                                                                                              | M                                | N           |
| roadClass          | Text              | The official classification of the road that this roadSegment is a part of.                                                     | R                                | Y           |
| name               | Text              | The official designation of the road that this roadSegment is a part of.                                                        | R                                | Y           |
| location           | geo:json          | A geo:json line sequence (LineString) containing all the points that make up this RoadSegment.                                  | R                                | Y           |
| refPointOfInterest | List of Reference | An List containing a JSON encoded sequence of characters referencing the Ids of the points of interest along this road segment. | O                                | Y           |

#### RoadSegment JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/127ce8f2f2b56e50d9326523fc1a221f
```json
{
  "id": "27109fe0-0c60-4302-a9eb-e7065eca876e",
  "type": "RoadSegment",
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
  "startPoint": {
    "value": {
      "type": "Point",
      "coordinates": [
        -104.99404,
        39.75621
      ]
    },
    "type": "geo:json"
  },
  "endPoint": {
    "value": {
      "type": "Point",
      "coordinates": [
        -109.99404,
        32.75621
      ]
    },
    "type": "geo:json"
  },
  "roadClass": {
    "value": "Single Carriageway",
    "type": "Text"
  },
  "name": {
    "value": "A123",
    "type": "Text"
  },
  "location": {
    "value": {
      "type": "LineString",
      "coordinates": [
        [-104.99404,39.75621],
        [-102.98,32.75],
        [-103.99,30.75],
        [-103.99,31.75],
        [-109.99404,32.75621]
      ]
    },
    "type": "geo:json"
  },
  "refPointOfInterest": {
    "value": [
      "4d798319-22b1-4714-b847-b81dbba3357b",
      "1909a43d-e5a1-46cb-bbd0-7cc16bc4fa33"
    ],
    "type": "List"
  }
}
```
