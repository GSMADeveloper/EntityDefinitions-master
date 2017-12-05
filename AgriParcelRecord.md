### AgriParcelRecord

This entity contains a harmonised description of the conditions recorded on a
generic parcel of land. This entity is primarily associated with the
agricultural vertical and related IoT applications.

&lt;AgriParcelRecord&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**AgriParcelRecord**".                                                                                                                                                                                                                                                                                                                                                  | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;AgriParcelRecord&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name      | Attribute Type                | Description                                                                                                                                 | Mandatory/ Optional/ Recommended | May be Null |
|---------------------|-------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refAgriParcel       | Reference                     | Unique id of the AgriParcel to which this record relates.                                                                                   | M                                | N           |
| location            | geo:json                      | The geo:json encoded polygon of this AgriParcelRecord.                                                                                      | M                                | N           |
| soilTemperature     | ExtQuantitativeValue(Number)  | The observed soil temperature in degrees centigrade encoded as a ExtQuantitativeValue.                                                      | O                                | Y           |
| temperature         | ExtQuantitativeValue(Number)  | The observed air temperature in degrees centigrade encoded as a ExtQuantitativeValue.                                                       | R                                | Y           |
| soilMoistureVwc     | ExtQuantitativeValue(Number)  | Measured as Volumetric Water Content, VWC as a percentage. 0 ≤soilMoistureVwc ≤ 1 encoded as a ExtQuantitativeValue                         | O                                | Y           |
| soilMoistureEc      | ExtQuantitativeValue(Number)  | Measured as Electrical Conductivity, EC in units of Siemens per meter (S/m) encoded as a ExtQuantitativeValue                               | O                                | Y           |
| solarRadiation      | ExtQuantitativeValue (Number) | Measured in kW/m2 encoded as a ExtQuantitativeValue.                                                                                        | O                                | Y           |
| relativeHumidity    | ExtQuantitativeValue(Number)  | Relative Humidity a number between 0 and 1 representing the range of 0% to 100% 0 ≤ relativeHumidity ≤ 1 encoded as a ExtQuantitativeValue. | R                                | Y           |
| atmosphericPressure | ExtQuantitativeValue(Number)  | Atmospheric Pressure in units of hecto Pascals encoded as a ExtQuantitativeValue.                                                           | O                                | Y           |
| description         | Text                          | Description of this AgriParcelRecord.                                                                                                       | R                                | Y           |

#### AgriParcelRecord JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/fbd5aeff87e6b73322bea447d5b0bb94
```json
{
  "id": "8f5445e6-f49b-496e-833b-e65fc97fcab7",
  "type": "AgriParcelRecord",
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
  "refAgriParcel": {
    "value": "d3676010-d815-468c-9e01-25739c5a25ed",
    "type": "Reference"
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
  "soilTemperature": {
    "value": {
      "value": 27,
      "unitCode": "CEL"
    },
    "type": "ExtQuantitativeValue"
  },
  "temperature": {
    "value": {
      "value": 33,
      "unitCode": "CEL"
    },
    "type": "ExtQuantitativeValue"
  },
  "soilMoistureVwc": {
    "value": {
      "value": 0.08,
      "unitCode": "C62"
    },
    "type": "ExtQuantitativeValue"
  },
  "soilMoistureEc": {
    "value": {
      "value": 17,
      "unitCode": "D10"
    },
    "type": "ExtQuantitativeValue"
  },
  "solarRadiation": {
    "value": {
      "value": 15,
      "unitCode": "N78"
    },
    "type": "ExtQuantitativeValue"
  },
  "relativeHumidity": {
    "value": {
      "value": 0.15,
      "unitCode": "C62"
    },
    "type": "ExtQuantitativeValue"
  },
  "atmosphericPressure": {
    "value": {
      "value": 1013.25,
      "unitCode": "A97"
    },
    "type": "ExtQuantitativeValue"
  },
  "description": {
    "value": "North greenhouse. Planting zone A ",
    "type": "Text"
  }
}
```
