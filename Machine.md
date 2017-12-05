###  Machine

This entity contains a harmonised description of an industrial machine for
example for use in CAM (Computer Aided Manufacturing). This entity provides an
essentially static description of a generic automation machine. This entity is
primarily associated with the industry segment in the automated manufacturing
industry, including CNC (Computer Numerical Control) machines, 3D printers and
all kinds of industrial robots.

&lt;Machine&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**Machine**".                                                                                                                                                                                                                                                                                                                                                           | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;Machine&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name         | Attribute Type           | Description                                                                                                                                                                                                     | Mandatory/ Optional/ Recommended | May be Null |
|------------------------|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refMachineModel        | Reference                | Refers to the machineModel that this machine is an instance of.                                                                                                                                                 | M                                | N           |
| serialNumber           | Text                     | The serial number assigned by the manufacturer.                                                                                                                                                                 | R                                | N           |
| status                 | Text                     | A manufacturer specific text format machine status code or description. It is an aggregation of dynamic information about the machine.                                                                          | R                                | Y           |
| assetIdentifier        | Text                     | An asset identifier (e.g. asset tag number) assigned by the owner.                                                                                                                                              | O                                | Y           |
| manufacturerCountry    | Text                     | The country where this machine instance was manufactured.                                                                                                                                                       | O                                | Y           |
| factory                | Text                     | The factory name/code manufacturing this machine.                                                                                                                                                               | O                                | Y           |
| dateManufactured       | DateTime                 | The ISO8601 sequence of characters at which date and time the machine was manufactured in UTC.                                                                                                                  | R                                | Y           |
| dateInstalled          | DateTime                 | The ISO8601 sequence of characters at which date and time the machine was installed in UTC.                                                                                                                     | R                                | Y           |
| dateFirstUsed          | DateTime                 | The ISO8601 sequence of characters at which date and time the machine was first used in UTC.                                                                                                                    | R                                | Y           |
| online                 | Boolean                  | Identifies the communication status of the machine, online if set to TRUE.                                                                                                                                      | R                                | Y           |
| installationNotes      | Text or URL              | Notes relating to this machine installation.                                                                                                                                                                    | O                                | Y           |
| location               | geo:json                 | The geo:json encoded location, of this machine.                                                                                                                                                                 | M                                | N           |
| refBuilding            | Reference                | Refers to the building instance into which this machine is installed.                                                                                                                                           | O                                | Y           |
| owner                  | List of Reference        | A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s). Related to a Schema.org person or organization. <https://schema.org/Person https://schema.org/Organization> | O                                | Y           |
| refSubscriptionService | List of Reference        | A List containing a JSON encoded sequence of characters of the unique Ids of any subscription service(s) associated with this machine.                                                                          | O                                | Y           |
| description            | Text                     | An optional description of this machine.                                                                                                                                                                        | R                                | Y           |
| voltage                | ExtQuantitativeValue     | The required supply voltage, in volts                                                                                                                                                                           | R                                | Y           |
| current                | ExtQuantitativeValue     | The required supply current, in amps                                                                                                                                                                            | R                                | Y           |
| power                  | ExtQuantitativeValue     | The nominal rated power consumption of the machine in kW                                                                                                                                                        | R                                | Y           |
| speed                  | ExtcurrQuantitativeValue | The maximum rotational speed in rpm                                                                                                                                                                             | R                                | Y           |

#### Machine JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/7b8303207db9fd5b7cf933ca360a5dd7
```json
{
	"id": "9166c528-9c98-4579-a5d3-8068aea5d6c0",
	"type": "Machine",
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
	"refMachineModel": {
		"value": "00b42701-43e1-482d-aa7a-e2956cfd69c3",
		"type": "Reference"
	},
	"serialNumber": {
		"value": "123456789",
		"type": "Text"
	},
	"status": {
		"value": "Ready/Idle : Machine operational",
		"type": "Text"
	},
	"assetIdentifier": {
		"value": "1234567",
		"type": "Text"
	},
	"manufacturerCountry": {
		"value": "UK",
		"type": "Text"
	},
	"factory": {
		"value": "ACME NorthEast Inc.",
		"type": "Text"
	},
	"dateManufactured": {
		"value": "2016-08-21T10:18:16Z",
		"type": "DateTime"
	},
	"dateInstalled": {
		"value": "2016-08-22T10:18:16Z",
		"type": "DateTime"
	},
	"dateFirstUsed": {
		"value": "2016-08-22T10:18:16Z",
		"type": "DateTime"
	},
	"online": {
		"value": true,
		"type": "Boolean"
	},
	"installationNotes": {
		"value": "http://www.example.com/installationNote1.txt",
		"type": "URL"
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
	"refBuilding": {
		"value": "8683b757-649c-49e0-ac89-ad392c9a0d0c",
		"type": "Reference"
	},
	"owner": {
		"value": [
			"247d402f-3e0b-4e7c-a2c0-335590c27f90",
			"a7995eb7-6bec-4176-b2e8-af545e2bb3b9"
		],
		"type": "List"
	},
	"refSubscriptionService": {
		"value": [
			"92158a14-f6c6-4d29-85d1-5d305cc87982",
			"3c6bac7b-9398-4529-8d89-766435b7490b"
		],
		"type": "List"
	},
	"description": {
		"value": "Industrial machine to create plastic bottles",
		"type": "Text"
	},
	"voltage": {
		"value": {
			"value": 220,
			"unitCode": "VLT",
			"timestamp": "2016-08-08T10:18:16Z"
		},
		"type": "ExtQuantitativeValue"
	},
	"current": {
		"value": {
			"value": 20,
			"unitCode": "AMP",
			"timestamp": "2016-08-08T10:18:16Z"
		},
		"type": "ExtQuantitativeValue"
	},
	"power": {
		"value": {
			"value": 4.4,
			"unitCode": "KWT",
			"timestamp": "2016-08-08T10:18:16Z"
		},
		"type": "ExtQuantitativeValue"
	},
	"speed": {
		"value": {
			"value": 10,
			"unitCode": "RPM",
			"timestamp": "2016-08-08T10:18:16Z"
		},
		"type": "ExtQuantitativeValue"
	}
}
```
