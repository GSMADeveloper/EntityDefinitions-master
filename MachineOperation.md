### MachineOperation

This entity contains a harmonised description of a generic machine operation.
This entity is primarily associated with the industry segment and related IoT
applications. Each MachineOperation instance will be related to a specific
Machine instance.

&lt;MachineOperation&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**MachineOperation**".                                                                                                                                                                                                                                                                                                                                                  | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;MachineOperation&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name  | Attribute Type | Description                                                                                                                                                                                                                                                                  | Mandatory/ Optional/ Recommended | May be Null |
|-----------------|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refMachine      | Reference      | Refers to the specific machine instance that this machineOperation record relates to.                                                                                                                                                                                        | M                                | N           |
| operationType   | Text           | Defines the type of operation conducted/ requested. This will be one of a defined list of operation types specific to the machine/ machineModel. Including; process, setup，maintenance, repair，breakdown. The list of operation types highly depends on the machine model. | M                                | N           |
| description     | Text           | A description of the operation conducted or applied.                                                                                                                                                                                                                         | R                                | Y           |
| result          | Text           | A description of the results of the operation. One of: **ok**, **success,suspended, aborted, failed.**                                                                                                                                                                       | R                                | Y           |
| startDate       | DateTime       | The planned start timestamp for the operation.                                                                                                                                                                                                                               | R                                | Y           |
| endDate         | DateTime       | The planned end timestamp for the operation. Note that this is advisory and the actual time the operation finishes may be before or after the planned endDate.                                                                                                               | R                                | Y           |
| status          | Text           | A choice from an enumerated list describing the status. One of: **planned, ongoing, finished, scheduled, cancelled.**                                                                                                                                                        | R                                | Y           |
| operator        | Person         | The operator performing this action encoded as a Schema.org person. <https://schema.org/Person>                                                                                                                                                                              | O                                | Y           |
| dateStarted     | DateTime       | Timestamp when the operation actually started to be performed.                                                                                                                                                                                                               | O                                | Y           |
| dateFinished    | DateTime       | Timestamp when the operation actually finished.                                                                                                                                                                                                                              | O                                | Y           |
| commandSequence | Text           | The command sequence executed/ requested for the machine in a representation format relevant to the machine.                                                                                                                                                                 | O                                | Y           |
| operationOutput | Text           | The text describing the output data of the operation. The schema of the output highly depends the machine model. One example of the output is for the processed goods of the machine, and the format can be: [“length XX”, “type XX”]                                        | O                                | Y           |


#### MachineOperation JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/32169966d47e0e128bb37fe08937dfd3
```json
{
	"id": "27577638-bd8a-4732-b418-fc8b949a0b0f",
	"type": "MachineOperation",
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
	"refMachine": {
		"value": "2033a7c7-d31b-48e7-91c2-014dc426c29e",
		"type": "Reference"
	},
	"operationType": {
		"value": "Process",
		"type": "Text"
	},
	"description": {
		"value": "Printing of 1000 T-shirts",
		"type": "Text"
	},
	"result": {
		"value": "ok",
		"type": "Text"
	},
	"startDate": {
		"value": "2016-08-20T10:18:16Z",
		"type": "DateTime"
	},
	"endDate": {
		"value": "2016-08-18T14:18:16Z",
		"type": "DateTime"
	},
	"status": {
		"value": "finished",
		"type": "Text"
	},
	"operator": {
		"value": {
			"name": "Fred Quimby",
			"jobTitle": "Print Supervisor"
		},
		"type": "Person"
	},
	"dateStarted": {
		"value": "2016-08-20T10:18:16Z",
		"type": "DateTime"
	},
	"dateFinished": {
		"value": "2016-08-18T14:18:16Z",
		"type": "DateTime"
	},
	"commandSequence": {
		"value": "Select inks. Prepare print masks. Print shirts. Clean print heads and rollers ",
		"type": "Text"
	},
	"operationOutput": {
		"value": "2 shirts were printed",
		"type": "Text"
	}
}
```
