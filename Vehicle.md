### Vehicle

This entity contains a harmonised description of a Vehicle. This entity is
primarily associated with the Automotive vertical segment but might also be
relevant to Industry, Smart City and Agriculture related IoT applications. Where
practicable <https://schema.org/Vehicle> naming conventions have been adopted.

&lt;Vehicle&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**Vehicle**".                                                                                                                                                                                                                                                                                                                                                           | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;Vehicle&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name              | Attribute Type                 | Description                                                                                                                                                                                                                                           | Mandatory/ Optional/ Recommended | May be Null |
|-----------------------------|--------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refVehicleType              | Reference                      | A JSON encoded sequence of characters referencing the Id of the vehicleType entity which describes this vehicle in more detail.                                                                                                                       | M                                | N           |
| fuelType                    | Text                           | A choice from an enumerated list describing the power source. One of: **gasoline, petrol(unleaded), petrol(leaded), petrol, diesel, electric, hydrogen, lpg autogas, cng, biodiesel, ethanol, hybrid electric/petrol, hybrid electric/diesel, other** | O                                | Y           |
| displacement                | Number                         | A number indicating the cylinder capacity of the engine in litres                                                                                                                                                                                     | O                                | Y           |
| fuelEfficiency              | QuantitativeValue              | The efficiency of the vehicle expressed as kilometres per litre or miles per gallon following the Schema.org definition at http://schema.org/fuelEfficiency                                                                                           | O                                | Y           |
| vehicleModelDate            | DateTime                       | The ISO8601 sequence of characters indicating the year of release.                                                                                                                                                                                    | O                                | Y           |
| dateDiscontinued            | DateTime                       | The ISO8601 sequence of characters indicating the year which the vehicle was discontinued.                                                                                                                                                            | O                                | Y           |
| vehicleIdentificationNumber | Text                           | The VIN (vehicle identification number) of the vehicle.                                                                                                                                                                                               | O                                | Y           |
| mileageFromOdometer         | Number or ExtQuantitativeValue | The total distance the car has travelled according to the on-board odometer in kilometres (unitCode KMT) or miles (unitCode SMI). If Number is used the units are assumed to be kilometres. references Schema.org Vehicle/ mileageFromOdometer.       | O                                | Y           |

#### Vehicle JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/0e22f3200c12c9e725148eafca6b225c
```json
{
  "id": "1fa179a6-b507-4857-ad72-eb5513ef05c6",
  "type": "Vehicle",
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
  "refVehicleType": {
    "value": "23821045-33d4-46ec-b777-98f461bf4856",
    "type": "Reference"
  },
  "fuelType": {
    "value": "diesel",
    "type": "Text"
  },
  "displacement": {
    "value": 3,
    "type": "Number"
  },
  "fuelEfficiency": {
    "value": {
      "value": 22,
      "unitText": "mpg"
    },
    "type": "QuantitativeValue"
  },
  "vehicleModelDate": {
    "value": "2013-01-01T00:00:00Z",
    "type": "DateTime"
  },
  "dateDiscontinued": {
    "value": "2016-08-23T10:18:16Z",
    "type": "DateTime"
  },
  "vehicleIdentificationNumber": {
    "value": "2T2GK31U08C041124",
    "type": "Text"
  },
  "mileageFromOdometer": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 33015,
      "unitCode": "SMI"
    },
    "type": "ExtQuantitativeValue"
  }
}

```
