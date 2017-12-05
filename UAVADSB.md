### <br>UAVADSB

This entity contains a harmonised description of a generic UAV Automatic
Dependent Surveillance–Broadcast. This entity is primarily associated with the
control and management of Unmanned Aerial Vehicles. Each UAVADSB instance will
be related to a specific UAV instance.

&lt;UAVADSB&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**UAVADSB**".                                                                                                                                                                                                                                                                                                                                                           | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. <http://schema.org/version/2.0/>) or a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;UAVADSB&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name  | Attribute Type | Description                                                                                                                                                                                           | Mandatory/ Optional/ Recommended | May be Null |
|-----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refUAV          | Reference      | Refers to the specific UAV instance to which this **UAVADSB** record relates.                                                                                                                         | M                                | N           |
| dateObserved    | Date Time      | The date and time of this DBS broadcast in ISO8601 UTC format.                                                                                                                                        | M                                | N           |
| originator      | Boolean        | A logical indicator of source of the message. TRUE indicates it is the UAV itself, FALSE indicates that it is a different source, a listening station software application or a different UAV.        | M                                | N           |
| refOriginator   | Reference      | Refers to the specific UAV instance or software application that reported the information.                                                                                                            | O                                | Y           |
| UAVADSBroadcast | Text           | A flight message describing the current flight status encoded as a DBSB Message in a string encoded binary format. <https://media.readthedocs.org/pdf/adsb-decode-guide/latest/adsb-decode-guide.pdf> | M                                | N           |

#### UAVADSB JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/3c326f6fe66b3eeab2b1464c28563dca
```json
{

"id": "1fa179a6-b507-4857-ad72-eb5513ef05c8",

"type": "UAVADSB",

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

"originator": {

"value": true,

"type": "Boolean"

},

"refOriginator": {

"value": "23821045-33d4-46ec-b777-98f461bf4856",

"type": "Reference"

},

"UAVADSBroadcast": {

"value": "00100000001011001100001101110001110000110010110011100000",

"type": "Text"

}

}
```