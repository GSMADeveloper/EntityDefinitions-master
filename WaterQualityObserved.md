### WaterQualityObserved

This entity contains a harmonised description of the water quality at a
particular location and time. This entity is primarily associated with the
vertical segments of agricultural and environment and related IoT applications.

&lt;WaterQualityObserved&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**WaterQualityObserved**".                                                                                                                                                                                                                                                                                                                                              | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;WaterQualityObserved&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type                 | Description                                                                                                              | Mandatory/ Optional/ Recommended | May be Null |
|----------------|--------------------------------|--------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refDevice      | List of Reference              | A reference to the unique entity Ids of the devices that originated this observation data.                               | M                                | N           |
| location       | geo:json                       | The geo:json encoded map location, that is related to this observation.                                                  | M                                | N           |
| dateObserved   | DateTime                       | The date and time of this observation in ISO8601 UTCformat.                                                              | M                                | N           |
| depth          | ExtQuantitativeValue (Number)  | Depth where the observation was taken. (*m*) encoded as a ExtQuantitativeValue.                                          | O                                | Y           |
| pressure       | ExtQuantitativeValue (Number)  | Hydrostatic pressure where the observation was taken. (ector Pascals) encoded as a ExtQuantitativeValue.                 | O                                | Y           |
| conductivity   | ExtQuantitativeValue (Number)  | Electrical conductivity. (*S/m*) encoded as a ExtQuantitativeValue.                                                      | O                                | Y           |
| conductance    | ExtQuantitativeValue (Number)  | Specific conductivity / 25 ºC /. (*S/m*) encoded as a ExtQuantitativeValue.                                              | O                                | Y           |
| temperature    | ExtQuantitativeValue (Number)  | The temperature expressed in degrees Celsius encoded as a ExtQuantitativeValue.                                          | O                                | Y           |
| tss            | ExtQuantitativeValue (Number)r | Total suspended solids. (*M1*) encoded as a ExtQuantitativeValue                                                         | O                                | Y           |
| tds            | ExtQuantitativeValue (Number)  | Total dissolved solids. (*M1*) encoded as a ExtQuantitativeValue.                                                        | O                                | Y           |
| turbidity      | ExtQuantitativeValue (Number)  | Amount of light scattered by particles in the water column. (*FTU*). encoded as a ExtQuantitativeValue.                  | O                                | Y           |
| salinity       | ExtQuantitativeValue (Number)  | Derived from the conductivity measurement. (*parts per thousand, ppt*) encoded as a ExtQuantitativeValue.                | O                                | Y           |
| pH             | ExtQuantitativeValue (Number)  | pH measurement (typically a number between *0 and 14*) encoded as a ExtQuantitativeValue.                                | O                                | Y           |
| orp            | ExtQuantitativeValue (Number)  | Oxidation-Reduction potential (*mV*) encoded as a ExtQuantitativeValue.                                                  | O                                | Y           |
| cdom           | ExtQuantitativeValue (Number)  | Color dissolved organic matter (*RFU*) encoded as a ExtQuantitativeValue.                                                | O                                | Y           |
| Chla           | ExtQuantitativeValue (Number)  | Concentration of chlorophyll A. (H29)                                                                                    | O                                | Y           |
| Cl             | ExtQuantitativeValue (Number)  | Concentration of chlorides. (M1)                                                                                         | O                                | Y           |
| CO             | ExtQuantitativeValue (Number)  | The level of free non-compound carbon monoxide present. (M1)                                                             | O                                | Y           |
| CO2            | ExtQuantitativeValue (Number)  | The level of free non-compound carbon dioxide present. (M1)                                                              | O                                | Y           |
| Hg             | ExtQuantitativeValue (Number)  | The level of compound mercury present. (M1)                                                                              | O                                | Y           |
| NH3            | ExtQuantitativeValue (Number)  | Concentration of ammonia. (M1)                                                                                           | O                                | Y           |
| NH4            | ExtQuantitativeValue (Number)  | Concentration of ammonium. (M1)                                                                                          | O                                | Y           |
| NO3            | ExtQuantitativeValue (Number)  | Concentration of nitrates. (M1)                                                                                          | O                                | Y           |
| O2             | ExtQuantitativeValue (Number)  | The level of free non-compound oxygen present. (M1)                                                                      | O                                | Y           |
| PC             | ExtQuantitativeValue (Number)  | Concentration of pigment phycocyanin which can be measured to estimate cyanobacteria concentrations specifically. (H29)  | O                                | Y           |
| PE             | ExtQuantitativeValue (Number)  | Concentration of pigment phycoerythrin which can be measured to estimate cyanobacteria concentrations specifically.(H29) | O                                | Y           |

#### WaterQualityObserved JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/e23befb590592ddefa6fd817d38919f0
```json
{
  "id": "72a30ca8-888e-49a2-8d8d-a5bebc19e98b",
  "type": "WaterQualityObserved",
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
  "refDevice": {
    "value": [
      "2033a7c7-d31b-48e7-91c2-014dc426c29e"
    ],
    "type": "List"
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
  "dateObserved": {
    "value": "2016-08-16T10:18:16Z",
    "type": "DateTime"
  },
  "depth": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 4,
      "unitCode": "MTR"
    },
    "type": "ExtQuantitativeValue"
  },
  "pressure": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 1020.2,
      "unitCode": "A97"
    },
    "type": "ExtQuantitativeValue"
  },
  "conductivity": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 10,
      "unitCode": "D10"
    },
    "type": "ExtQuantitativeValue"
  },
  "conductance": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 25,
      "unitCode": "SIE"
    },
    "type": "ExtQuantitativeValue"
  },
  "temperature": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 15,
      "unitCode": "CEL"
    },
    "type": "ExtQuantitativeValue"
  },
  "tss": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 200,
      "unitCode": "M1"
    },
    "type": "ExtQuantitativeValue"
  },
  "tds": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 150,
      "unitCode": "M1"
    },
    "type": "ExtQuantitativeValue"
  },
  "turbidity": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 343,
      "unitCode": "FTU"
    },
    "type": "ExtQuantitativeValue"
  },
  "salinity": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 220,
      "unitCode": "NX"
    },
    "type": "ExtQuantitativeValue"
  },
  "pH": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 5
    },
    "type": "ExtQuantitativeValue"
  },
  "orp": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 225,
      "unitCode": "2Z"
    },
    "type": "ExtQuantitativeValue"
  },
  "cdom": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 22,
      "unitCode": "RFU"
    },
    "type": "ExtQuantitativeValue"
  },
  "Chla": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 11,
      "unitCode": "H29"
    },
    "type": "ExtQuantitativeValue"
  },
  "CI": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 1000,
      "unitCode": "M1"
    },
    "type": "ExtQuantitativeValue"
  },
  "CO": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 40,
      "unitCode": "M1"
    },
    "type": "ExtQuantitativeValue"
  },
  "CO2": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 1,
      "unitCode": "M1"
    },
    "type": "ExtQuantitativeValue"
  },
  "Hg": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 0.2,
      "unitCode": "M1"
    },
    "type": "ExtQuantitativeValue"
  },
  "NH3": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 0.03,
      "unitCode": "M1"
    },
    "type": "ExtQuantitativeValue"
  },
  "NH4": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 0.02,
      "unitCode": "M1"
    },
    "type": "ExtQuantitativeValue"
  },
  "N03": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 1,
      "unitCode": "M1"
    },
    "type": "ExtQuantitativeValue"
  },
  "O2": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 50,
      "unitCode": "M1"
    },
    "type": "ExtQuantitativeValue"
  },
  "PC": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 52,
      "unitCode": "H29"
    },
    "type": "ExtQuantitativeValue"
  },
  "PE": {
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "value": 66,
      "unitCode": "H29"
    },
    "type": "ExtQuantitativeValue"
  }
}

```
