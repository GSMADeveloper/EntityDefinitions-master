### Device

This entity contains a harmonised description of a generic device. This entity
provides an essentially static description of a generic device and is therefore
applicable to all IoT segments and related IoT applications.

&lt;Device&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**Device**".                                                                                                                                                                                                                                                                                                                                                            | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;Device&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name      | Attribute Type                | Description                                                                                                                                                                                                      | Mandatory/ Optional/ Recommended | May be Null |
|---------------------|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refDeviceModel      | Reference                     | Unique id of this device model selected from DeviceModel.                                                                                                                                                        | M                                | N           |
| serialNumber        | Text                          | The serial number assigned by the manufacturer.                                                                                                                                                                  | M                                | N           |
| supplierName        | Text                          | The details of the supplier of this device.                                                                                                                                                                      | R                                | Y           |
| manufacturerCountry | Text                          | The country where this device was manufactured.                                                                                                                                                                  | R                                | Y           |
| factory             | Text                          | The factory name/code manufacturing this device.                                                                                                                                                                 | O                                | Y           |
| dateManufactured    | DateTime                      | The ISO8601 sequence of characters at which the device was manufactured in UTC.                                                                                                                                  | M                                | N           |
| description         | Text                          | An optional description of this device.                                                                                                                                                                          | R                                | Y           |
| owner               | List of Reference             | An List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s). Related to a Schema.org person or organization. <https://schema.org/Person https://schema.org/Organization> | O                                | Y           |
| dateInstalled       | DateTime                      | The ISO8601 sequence of characters at which the device was installed in UTC.                                                                                                                                     | R                                | N           |
| dateFirstUsed       | DateTime                      | The ISO8601 sequence of characters at which the device was first used in UTC.                                                                                                                                    | R                                | N           |
| hardwareVersion     | Text                          | The hardware version of this device.                                                                                                                                                                             | R                                | N           |
| firmwareVersion     | Text                          | The firmware version of this device.                                                                                                                                                                             | R                                | N           |
| softwareVersion     | Text                          | The software version of this device.                                                                                                                                                                             | R                                | N           |
| osVersion           | Text                          | The operating system version of this device.                                                                                                                                                                     | R                                | N           |
| supportedProtocol   | List                          | An List element per supported communication protocol.                                                                                                                                                            | O                                | N           |
| location            | geo:json                      | The geo:json encoded location, of this device.                                                                                                                                                                   | O                                | Y           |
| online              | Boolean                       | The communication status of this device. A logical representation of Offline (false) or Online (true).                                                                                                           | O                                | N           |
| status              | Text                          | The text format (current) device status code or description. Expected to be the manufacturer or device specific status code generated by the device.                                                             | R                                | Y           |
| dateLastCalibration | DateTime                      | The date this device was last calibrated.                                                                                                                                                                        | O                                | Y           |
| batteryLevel        | ExtQuantitativeValue (Number) | Battery level. It must be equal to: 1.0 When the battery charge is full. 0.0 When the battery charge empty. Null when it cannot be determined. Normally encoded as an ExtQuantitativeValue.                      | O                                | Y           |
| value               | ExtQuantitativeValue (Number) | The observed or reported value of the device. For control applications the value can be updated to change the device/ actuator setting. The value is encoded as an ExtQuantitativeValue.                         | R                                | Y           |

#### Device JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/b29f6f3841d778d455e58fcad74c637d
```json
{
  "id": "ba2d4fd9-f57f-4610-a589-2d52670d14f3",
  "type": "Device",
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
  "refDeviceModel": {
    "value": "d1be2e61-d9e7-43cd-9c68-51e0861b3a49",
    "type": "Reference"
  },
  "serialNumber": {
    "value": "123456789",
    "type": "Text"
  },
  "supplierName": {
    "value": "ACME Direct, Inc.",
    "type": "Text"
  },
  "manufacturerCountry": {
    "value": "UK",
    "type": "Text"
  },
  "factory": {
    "value": "56A8",
    "type": "Text"
  },
  "dateManufactured": {
    "value": "2016-08-21T10:18:16Z",
    "type": "DateTime"
  },
  "description": {
    "value": "Thermocouple",
    "type": "Text"
  },
  "owner": {
    "value": [
      "43c46ff2-b0f7-4e4f-838a-adee1c9cae88",
      "ebf421c9-363b-4ed4-97a0-93a6e39786ff"
    ],
    "type": "List"
  },
  "dateInstalled": {
    "value": "2016-08-22T10:18:16Z",
    "type": "DateTime"
  },
  "dateFirstUsed": {
    "value": "2016-08-22T10:18:16Z",
    "type": "DateTime"
  },
  "hardwareVersion": {
    "value": "1.2",
    "type": "Text"
  },
  "firmwareVersion": {
    "value": "2.8.56",
    "type": "Text"
  },
  "softwareVersion": {
    "value": "2.5.11",
    "type": "Text"
  },
  "osVersion": {
    "value": "8.1",
    "type": "Text"
  },
  "supportedProtocol": {
    "value": [
      "HTTP",
      "HTTPS",
      "FTP"
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
  "online": {
    "value": true,
    "type": "Boolean"
  },
  "status": {
    "value": "SC1001",
    "type": "Text"
  },
  "dateLastCalibration": {
    "value": "2016-08-22T10:18:16Z",
    "type": "DateTime"
  },
  "batteryLevel": {
    "value": {
      "value": 0.7
    },
    "type": "ExtQuantitativeValue"
  },
  "value": {
    "value": {
      "value": 1
    },
    "type": "ExtQuantitativeValue"
  }
}
```
