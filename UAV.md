### UAV

This entity contains a harmonised description of a specific Unmanned Aerial
Vehicle (UAV). This entity is primarily associated with UAV command and control
and related UAV transport applications.

&lt;UAV&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity. A globally unique reference to this entity instance. It is recommended ids comply with RFC4122.                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to “UAV”.                                                                                                                                                                                                                                                                                                                                                                   | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp. This will usually be allocated by the storage platform.                                                                                                                                                                                                                                                                                                        | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity. This will usually be allocated by the storage platform. A null value in this field or a value equivalent to dateCreated means the entity has not been modified since being created.                                                                                                                                                     | O                                | Y           |
| source         | URL            | A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.                                                                                                                                                                                               | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the provider of the harmonised data entity.                                                                                                                                                                                                                                                                                                          | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. <http://schema.org/version/2.0/>) or a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;UAV&gt;&lt;EntitySpecificAttributes&gt;

| Attribute Name | Attribute Type                                     | Description                                                                                                                                                                                                     | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refUAVModel    | Reference                                          | A JSON encode sequence of characters referencing the Id of the UAVModel entity, which describes this UAV in more detail.                                                                                        | M                                | N           |
| owner          | List of references to Person(s) or Organization(s) | A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s). Related to a Schema.org person or organization. <https://schema.org/Person https://schema.org/Organization> | R                                | Y           |
| operator       | List of references to Person(s) or Organization(s) | A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s). Related to a Schema.org person or organization. <https://schema.org/Person https://schema.org/Organization> | R                                | Y           |
| operationMode  | Text                                               | Text describing the choice from "vlos", "evlos", "bvlos", "automated" Note: descriptions align with UTM Flight message.                                                                                         | R                                | Y           |
| location       | Geo:json                                           | The current geo:json encoded map location of the UAV                                                                                                                                                            | M                                | N           |
| elevation      | ExtQuantitativeValue                               | The elevation of the UAV. Specify value and units of measure                                                                                                                                                    | M                                | N           |
| dateObserved   | DateTime                                           | The date and time of this monitoring report in ISO8601 UTC format.                                                                                                                                              | M                                | N           |
| flightStatus   | Text                                               | The flight status of the UAV, including stop, takeoff, flight, hover, land                                                                                                                                      | M                                | N           |
| workStatus     | Text                                               | The work status of the UAV, including stop, prepare, work, finish                                                                                                                                               | O                                | Y           |
| groundSpeed    | ExtQuantitativeValue                               | The real-time speed of the UAV. Specify value and units of measure                                                                                                                                              | O                                | Y           |
| fuel           | ExtQuantitativeValue                               | Current fuel load of the UAV. Specify value and units of measure                                                                                                                                                | O                                | Y           |

#### UAV JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/c4797bcbb68497feee3769df50ce12e0
```json
{

"id": "1fa179a6-b507-4857-ad72-eb5513ef05c8",

"type": "UAV",

"dateCreated": {

"value": "2017-08-08T10:18:16Z",

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

"refUAVModel": {

"value": "23821045-33d4-46ec-b777-98f461bf4856",

"type": "Reference"

},

"owner": {

"value": [

"cdfd9cb8-ae2b-47cb-a43a-b9767ffd5c84",

"1be9cd61-ef59-421f-a326-4b6c84411ad4"

],

"type": "List"

},

"operator": {

"value": [

"cdfd9cb8-ae2b-47cb-a43a-b9767ffd5c84",

"1be9cd61-ef59-421f-a326-4b6c84411ad4"

],

"type": "List"

},

"operationMode": {

"value": "vlos",

"type": "text"

},

"location": {

"value": {

"type": "Point",

"coordinates": [

\-103.9904,

39.7564

]

},

"type": "geo:json"

},

"elevation": {

"value": {

"value": 1000,

"unitCode": "MTR",

"timestamp": "2016-09-20T10:15:16Z"

},

"type": "ExtQuantitativeValue"

},

"dateObserved": {

"value": "2016-08-08T10:18:16Z",

"type": "DateTime"

},

"flightStatus": {

"value": "takeoff",

"type": "text"

},

"workStatus": {

"value": "finish",

"type": "text"

},

"groundSpeed": {

"value": {

"value": 50,

"unitCode": "MTS",

"timestamp": "2016-09-20T10:15:16Z"

},

"type": "ExtQuantitativeValue"

},

"fuel": {

"value": {

"value": 50,

"unitCode": "GLI",

"timestamp": "2016-08-08T10:18:16Z"

},

"type": "ExtQuantitativeValue"

}

}
```