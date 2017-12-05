### UAVStateVector

This entity contains a harmonised description of a generic UAV State Vector,
which is an Interpretation and aggregation of Automatic Dependent
Surveillance–Broadcast messages. This entity is primarily associated with the
control and management of Unmanned Aerial Vehicles. Each UAVStateVector instance
is related to a specific UAV instance.

&lt;UAVStateVector&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "UAVStateVector ".                                                                                                                                                                                                                                                                                                                                                       | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. <http://schema.org/version/2.0/>) or a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;UAVStateVector&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                 | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refUAV         | Reference      | Refers to the specific UAV instance to which this UAVstateVector record relates.                                                                                                                            | M                                | N           |
| dateObserved   | DateTime       | The date and time relating to this state vector in ISO8601 UTC format.                                                                                                                                      | M                                | N           |
| refOriginator  | Reference      | Refers to the specific software application that reported the information.                                                                                                                                  | M                                | N           |
| stateVector    | List           | A state vector describing the current flight status encoded as an opensky-network.org StateVector encoded as a JSON object. <https://opensky-network.org/apidoc/javadoc/org/opensky/model/StateVector.html> | M                                | N           |

#### UAVStateVector JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/0ef3d716a8303580f4fec17ca32d8af0
```json
{

"id": "1fa179a6-b507-4857-ad72-eb5513ef05c8",

"type": "UAVStateVector",

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

"dateObserved": {

"value": "2016-08-08T10:18:16Z",

"type": "DateTime"

},

"refOriginator": {

"value": "13821045-33d4-46ec-b777-98f461bf4123",

"type": "Reference"

},

"stateVector": {

"value": [

100,

200,

300,

400

],

"type": "List"

}

}
```