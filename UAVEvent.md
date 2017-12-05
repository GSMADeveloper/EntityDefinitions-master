### UAVEvent

The UAVEvent records the incursion of a specific UAV into or near protected
airspace or locations. It also records the control measure taken. This entity is
primarily associated with UAV command and control and related UAV transport
applications.

&lt;UAVEvent&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| Id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "UAVEvent".                                                                                                                                                                                                                                                                                                                                                              | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. <http://schema.org/version/2.0/>) or a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;UAVEvent&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type       | Description                                                                                                                    | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------------|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refUAV         | Reference            | A JSON encode sequence of characters referencing the Id of the UAV entity, which is associated with this event.                | M                                | N           |
| refOriginator  | Reference            | Refers to the specific software application that reported the information.                                                     | M                                | N           |
| location       | Geo:json             | The geo:json encoded map location of the UAV point where the event is triggered.                                               | M                                | N           |
| elevation      | ExtQuantitativeValue | A number indicating the elevation of the UAV when the event is triggered. Specify value and units of measure                   | M                                | N           |
| eventStart     | DateTime             | The start date and time of this event in ISO8601 UTC format.                                                                   | M                                | N           |
| eventType      | Text                 | The type of the UAV event, a choice from: illegal flight , close to unpermitted airspace, overspeed, over height, illegal work | M                                | N           |
| description    | Text                 | The description of this event                                                                                                  | R                                | Y           |
| eventEnd       | DateTime             | The end date and time of this event in ISO8601 UTC format.                                                                     | R                                | Y           |
| eventResult    | Text                 | The handle result of the event, a choice from: logged, notify, alarm, force land, force back, force hover                      | R                                | Y           |

#### UAVEvent JSON

The JSON code can be downloaded from:
https://gist.github.com/GSMADeveloper/050f4f160371a087845e17214904f3e8
```json
{

"id": "1fa179a6-b507-4857-ad72-eb5513ef05c8",

"type": "UAVEvent",

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

"refUAV": {

"value": "23821045-33d4-46ec-b777-98f461bf4856",

"type": "Reference"

},

"refOriginator": {

"value": "23821045-33d4-46ec-b777-98f461bf4856",

"type": "Reference"

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

"eventStart": {

"value": "2016-08-22T10:18:16Z",

"type": "DateTime"

},

"eventType": {

"value": "over height",

"type": "text"

},

"description": {

"value": "the UAV is flying over a height limit",

"type": "text"

},

"eventEnd": {

"value": "2016-08-22T10:19:16Z",

"type": "DateTime"

},

"eventResult": {

"value": "alarm",

"type": "text"

}

}
```