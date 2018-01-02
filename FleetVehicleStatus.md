### <br>FleetVehicleStatus

This entity contains a harmonised description of the status of a generic fleet
vehicle. This entity is primarily associated with the vertical segment of the
transport and logistics but may also be used many other related IoT
applications.

&lt;FleetVehicleStatus&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**FleetVehicleStatus**".                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. <http://schema.org/version/2.0/>) or a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;FleetVehicleStatus&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name          | Attribute Type                        | Description                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|-------------------------|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refFleetVehicle         | Reference                             | A a JSON encoded sequence of characters that reference the unique id of the related FleetVehicle entity to which this status report relates.                                                                                                              | M                                | N           |
| restFuelAmount          | ExtQuantitativeValue (Number)         | The level of fuel recorded when the vehicle was last at rest (i.e. stopped). The timestamp element of the attribute should indicate when the vehicle was last at rest. Data to be recorded in Litres.                                                     | M                                | N           |
| lastFuellingAmount      | ExtQuantitativeValue (Number)         | The level of fuel added to the vehicle at the last fuelling. The timestamp element of the attribute should indicate when the vehicle was fuelled. Data tobe recorded in Litres.                                                                           | M                                | N           |
| currentStatus           | Text                                  | A description of the current status of the vehicle e.g. deployed, finished, terminated, servicing, starting                                                                                                                                               | R                                | Y           |
| currentOperative        | Person                                | The current operative (e.g. driver) of the vehicle encoded as a Schema.org person. <https://schema.org/Person> Null if not known.                                                                                                                         | R                                | Y           |
| speed                   | ExtQuantitativeValue(Number)          | The current speed of the fleet vehicle (km/h). The timestamp element of the attribute should indicate when the reading was obtained.                                                                                                                      | O                                | Y           |
| bearing                 | ExtQuantitativeValue(Number)          | The current bearing of the fleet vehicle in degrees relative to North. The timestamp element of the attribute should indicate when the reading was obtained.                                                                                              | O                                | Y           |
| lastKnownPositiont      | Geo:json                              | The current, real time geo:json encoded GPS location of the fleet vehicle                                                                                                                                                                                 | M                                | N           |
| lastKnownPositionUpdate | DateTimer                             | The timestamp of the last known position update for the fleet vehicle                                                                                                                                                                                     | M                                | N           |
| inRestrictedArea        | Boolean                               | Indicates if the vehicle is known to be in a restricted area at the time of the status update                                                                                                                                                             | R                                | Y           |
| mileageFromOdometer     | Number or ExtQuantitativeValue(Number | The total distance the fleet vehicle has travelled according to the on-board odometer in kilometres (unitCode KMT) or miles (unitCode SMI). If Number is used the units are assumed to be kilometres. references Schema.org Vehicle/ mileageFromOdometer. | M                                | N           |

#### FleetVehicleStatus JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/77f5e38611740b5795415cba62468a3d

```json
{
  "id": "1fa179a6-b507-4857-ad72-eb5513ef05c6",
  "type": "FleetVehicleStatus",
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
  "restFuelAmount": {
    "type": "ExtQuantitativeValue",
    "value": {
      "timestamp": "2017-08-08T10:18:16Z",
      "unitCode": "LTR",
      "value": 10
    }
  },
  "lastFuellingAmount": {
    "type": "ExtQuantitativeValue",
    "value": {
      "timestamp": "2017-08-08T12:50:16Z",
      "unitCode": "LTR",
      "value": 50
    }
  },
  "currentStatus": {
    "value": "finished",
    "type": "Text"
  },
  "currentOperative": {
    "value": {
      "givenName": "John Smith",
      "jobTitle": "Ambulance Operator"
    },
    "type": "Person"
  },
  "speed": {
    "value": {
      "value": 50,
      "unitCode": "KMH",
      "timestamp": "2017-08-08T14:18:16Z"
    },
    "type": "ExtQuantitativeValue"
  },
  "bearing": {
    "value": {
      "value": 50,
      "unitCode": "DD",
      "timestamp": "2017-08-08T14:18:16Z"
    },
    "type": "ExtQuantitativeValue"
  },
  "lastKnownPosition": {
    "value": {
      "type": "Point",
      "coordinates": [
        -104.99404,
        39.75621
      ]
    },
    "type": "geo:json"
  },
  "lastKnownPositionUpdate": {
    "value": "2017-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "inRestrictedArea": {
    "value": false,
    "type": "Boolean"
  },
  "mileageFromOdometer": {
    "value": {
      "value": 50,
      "unitCode": "SMI"
    },
    "type": "ExtQuantitativeValue"
  }
}
```