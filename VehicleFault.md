### VehicleFault

This entity contains a harmonised description of a Vehicle Fault. This entity is
primarily associated with the Automotive vertical segment but might also be
relevant to Industry, Smart City and Agriculture related IoT applications.

&lt;VehicleFault&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**VehicleFault**".                                                                                                                                                                                                                                                                                                                                                      | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;VehicleFault&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type    | Description                                                                                                                                                                                  | Mandatory/ Optional/ Recommended | May be Null |
|----------------|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refVehicle     | List of Reference | A JSON encoded sequence of characters referencing the id of the vehicle in which this fault occurred or multiple ids in the case a common fault can be identified against multiple vehicles. | M                                | N           |
| dateIdentified | DateTime          | An ISO8601 sequence of characters indicating the date and time the fault was detected or identified.                                                                                         | M                                | N           |
| eventType      | Text              | The event type descriptor, a choice from an enumerated list including: **collision, emergency, harshAccel, harshDecel, auxBatteryWarn, milWarn**.                                            | M                                | N           |
| location       | geo:json          | The geo location where the fault was detected.                                                                                                                                               | R                                | Y           |
| processingType | Text              | Indicates how the fault was dealt with, e.g. **systemHandled,** or not present if the issue has not been resolved.                                                                           | O                                | Y           |
| dateProcessed  | DateTime          | The ISO8601 sequence of characters indicating the data and time at which the issue was solved, or not present if the issue has not been resolved.                                            | O                                | Y           |
| dtCode         | Text              | DTC or Diagnostic Trouble Codes are codes generated by the vehicle's computer diagnostic system. These may be manufacturer, equipment or vehicle specific.                                   | R                                | Y           |
| faultLog       | Text              | Free text that records information about the initial fault incident, ongoing updates and fault resolution.                                                                                   | O                                | Y           |

#### VehicleFault JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/9a70cc18bd403c7115d0ffec8ecc2ecf
```json
{
  "id": "4939200a-5ef5-4266-8c91-1f82ad3b543b",
  "type": "VehicleFault",
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
  "refVehicle": {
    "value": [
      "e64a2ecb-a8ae-4f51-ab66-2e9729c02d22"
    ],
    "type": "List"
  },
  "dateIdentified": {
    "value": "2016-08-20T10:18:16Z",
    "type": "DateTime"
  },
  "eventType": {
    "value": "emergency",
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
  "processingType": {
    "value": "systemHandled",
    "type": "Text"
  },
  "dateProcessed": {
    "value": "2016-08-21T10:18:16Z",
    "type": "DateTime"
  },
  "dtCode": {
    "value": "EMERG-1234-a",
    "type": "Text"
  },
  "faultLog": {
    "value": "Emergency stop. Fault with engine",
    "type": "Text"
  }
}
```
