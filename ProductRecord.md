### ProductRecord

This entity contains a harmonised description of the conditions recorded as a
product (generally a physical instance of a product) moves through the supply
chain. This entity is primarily associated with the retail supply vertical and
related IoT applications.

&lt;ProductRecord&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**ProductRecord**".                                                                                                                                                                                                                                                                                                                                                     | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;ProductRecord&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name      | Attribute Type       | Description                                                                                                                                                                                                                           | Mandatory/ Optional/ Recommended | May be Null |
|---------------------|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refProduct          | Reference            | Unique id of the Product to which this record relates.                                                                                                                                                                                | M                                | N           |
| location            | geo:json             | The geo:json encoded current location.                                                                                                                                                                                                | M                                | N           |
| temperature         | ExtQuantitativeValue | The observed local air temperature in degrees centigrade encoded as an ExtQuantitativeValue.                                                                                                                                          | O                                | Y           |
| relativeHumidity    | ExtQuantitativeValue | Relative Humidity a number between 0 and 1 representing the range 0% to 100 (%) 0 ≤ relativeHumidity ≤ 1 encoded as a ExtQuantitativeValue.                                                                                           | O                                | Y           |
| atmosphericPressure | ExtQuantitativeValue | Atmospheric Pressure in units of hecto Pascals encoded as a ExtQuantitativeValue.                                                                                                                                                     | O                                | Y           |
| description         | Text                 | Description of this ProductRecord.                                                                                                                                                                                                    | R                                | Y           |
| weight              | ExtQuantitativeValue | Current (i.e. measured) weight of the product including packaging. This may differ from the original weight due to additional packaging or losses during shipment e.g. evaporation                                                    | O                                | Y           |
| netWeight           | QuantitativeValue    | Weight of the Agri-Product itself in a package with GS1 code Used to identify the net weight of the product. Net Weight excludes all packaging material, including the packaging material of all lower-level GTINs. Example:11.5 kgm. | O                                | Y           |
| volume              | QuantitativeValue    | The current volume of the product including packaging.                                                                                                                                                                                | O                                | Y           |
| dateObserved        | DateTime             | The timestamp at which this ProductRecord was generated.                                                                                                                                                                              | R                                | Y           |
| O2                  | QuantitativeValue    | The level of gaseous Oxygen (O2) present in the atmosphere as measured around the product. (M1)                                                                                                                                       | O                                | Y           |

#### ProductRecord JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/4c2fc701cf2bf121b360613cf27ba8d4
```json
{
  "id": "85d05a21-6907-44b3-83d8-85d8a713d003",
  "type": "ProductRecord",
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
  "refProduct": {
    "type": "Reference",
    "value": "6223903a-d8c5-4e7e-af24-cc90967feb61"
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
  "temperature": {
    "type": "ExtQuantitativeValue",
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "unitCode": "CEL",
      "value": 3.823
    }
  },
  "relativeHumidity": {
    "type": "ExtQuantitativeValue",
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "unitCode": "C62",
      "value": 0.70
    }
  },
  "atmosphericPressure": {
    "type": "ExtQuantitativeValue",
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "unitCode": "A97",
      "value": 1006.19
    }
  },
  "description": {
    "type": "Text",
    "value": "Palm oil consignment arrived at port for shipment"
  },
  "weight": {
    "type": "ExtQuantitativeValue",
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "unitText": "grammes",
      "unitCode": "GRM",
      "value": 2550
    }
  },
  "netWeight": {
    "type": "QuantitativeValue",
    "value": {
      "unitText": "grammes",
      "unitCode": "GRM",
      "value": 2500
    }
  },
  "volume": {
    "type": "QuantitativeValue",
    "value": {
      "unitCode": "MTQ",
      "value": 1.7
    }
  },
  "dateObserved": {
    "value": "2016-08-08T10:00:00Z",
    "type": "DateTime"
  },
  "O2": {
    "type": "ExtQuantitativeValue",
    "value": {
      "value": 300,
      "unitCode": "GQ"
    }
  }
}
```
