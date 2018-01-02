### <br>FleetVehicleOperation

This entity contains a harmonised description of a generic fleet vehicle
operation such as a delivery, or a postal collection. This entity is primarily
associated with the vertical segment of the transport and logistics but may also
be used many other related IoT applications.

&lt;FleetVehicleOperation&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**FleetVehicleOperation**".                                                                                                                                                                                                                                                                                                                                             | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. <http://schema.org/version/2.0/>) or a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;FleetVehicleOperation&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name        | Attribute Type              | Description                                                                                                                                                                                                         | Mandatory/ Optional/ Recommended | May be Null |
|-----------------------|-----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refFleetVehicle       | Reference                   | A a JSON encoded sequence of characters that reference the unique id of the related FleetVehicle entity to which this operation relates.                                                                            | M                                | N           |
| refFleetVehicleStatus | Reference                   | A a JSON encoded sequence of characters that reference the unique id of the related the current FleetVehicleStatus entity to which this operation relates. (e.g. speed, bearing, location)                          | R                                | Y           |
| initiatingLocation    | Geo:json                    | The geo:json encoded GPS location of the point from where the service was requested e.g. the location of the person who called for an ambulance.                                                                    | M                                | N           |
| eventStart            | DateTime                    | The start date and time when the event or operation was triggered                                                                                                                                                   | M                                | N           |
| eventEnd              | DateTime                    | The end date and time of the event when the event or operation is known to be over/ complete. Null if not ended.                                                                                                    | O                                | Y           |
| operationType         | Text                        | The type of the event or operation e.g. e.g. Call for a patient transportation, postal collection, delivery, close to a restricted area, overspeed                                                                  | M                                | N           |
| description           | Text                        | The description of the event or operation                                                                                                                                                                           | O                                | Y           |
| result                | Text                        | The final result of the event or operation                                                                                                                                                                          | R                                | Y           |
| responseTime          | ExtQuantitativeValue(Number | Indicates the time to respond to an event, in seconds. The date and timestamp indicates when the last update was recorded. E.g. records the response time for an ambulance to reach to a patient                    | M                                | N           |
| transportTime         | ExtQuantitativeValue(Number | Indicates the time that the fleet vehicle has spent transporting people or supplies for the current operation. E.g. indicates the time an ambulance spent transporting a patient to a hospital emergency department | M                                | N           |

#### FleetVehicleOperation JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/b60e557062647abec96d1899b66c9b01

```json
{
  "id": "1fa179a6-b507-4857-ad72-eb5513ef05c6",
  "type": "FleetVehicleOperation",
  "dateCreated": {
    "value": "2017-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "dateModified": {
    "value": "2017-08-08T10:18:16Z",
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
  "refFleetVehicle": {
    "value": "23821045-33d4-46ec-b777-98f461bf4855",
    "type": "Reference"
  },
  "refFleetVehicleStatus": {
    "value": "23821045-33d4-46ec-b777-98f461bf4856",
    "type": "Reference"
  },
  "initiatingLocation": {
    "value": {
      "type": "Point",
      "coordinates": [
        -104.99404,
        39.75621
      ]
    },
    "type": "geo:json"
  },
  "eventStart": {
    "value": "2017-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "eventEnd": {
    "value": "2017-08-08T10:19:16Z",
    "type": "DateTime"
  },
  "operationType": {
    "value": "Patient transportation",
    "type": "Text"
  },
  "description": {
    "value": "An emergency tranportation of a 3 year old boy",
    "type": "Text"
  },
  "result": {
    "value": "success",
    "type": "Text"
  },
  "responseTime": {
    "type": "ExtQuantitativeValue",
    "value": {
      "timestamp": "2017-08-08T10:18:16Z",
      "unitCode": "sec",
      "value": 10
    }
  },
  "transportTime": {
    "type": "ExtQuantitativeValue",
    "value": {
      "timestamp": "2017-08-08T10:19:16Z",
      "unitCode": "min",
      "value": 20
    }
  }
}

```