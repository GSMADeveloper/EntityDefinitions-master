### <br>UAVTMS

This entity contains a harmonised description of a specific Unmanned Aerial
Vehicle (UAV) Traffic Management Software Application that is designed to listen
to and monitor the information transmitted by UAV’s, typically this software
application would be operated at a ground station. This entity is primarily
associated with UAV command and control applications.

&lt;UAVTMS&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| Id             | Text           | Unique id of this instance of this entity. A globally unique reference to this entity instance. It is recommended ids comply with RFC4122.                                                                                                                                                                                                                                                | M                                | N           |
| Type           | Text           | Must be equal to “UAVTMS”.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp. This will usually be allocated by the storage platform.                                                                                                                                                                                                                                                                                                        | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity. This will usually be allocated by the storage platform. A null value in this field or a value equivalent to dateCreated means the entity has not been modified since being created.                                                                                                                                                     | O                                | Y           |
| source         | URL            | A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.                                                                                                                                                                                               | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the provider of the harmonised data entity.                                                                                                                                                                                                                                                                                                          | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. <http://schema.org/version/2.0/>) or a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;UAVTMS&gt;&lt;EntitySpecificAttributes&gt;

| Attribute Name         | Attribute Type                                     | Description                                                                                                                                                                                                     | Mandatory/ Optional/ Recommended | May be Null |
|------------------------|----------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refSoftwareApplication | Reference                                          | A JSON encoded sequence of characters referencing the unique Id of the Software Application. Related to a Schema.org Software Application. <https://schema.org/SoftwareApplication>                             | M                                | N           |
| operationalInstance    | URL                                                | A sequence of characters giving the URL of this operational instance.                                                                                                                                           | M                                | N           |
| owner                  | List of references to Person(s) or Organization(s) | A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s). Related to a Schema.org person or organization. <https://schema.org/Person https://schema.org/Organization> | R                                | Y           |
| operator               | List of references to Person(s) or Organization(s) | A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s). Related to a Schema.org person or organization. <https://schema.org/Person https://schema.org/Organization> | R                                | Y           |

#### UAVTMS JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/cfc36fd28d8b38313eccedd3bc6b00c1
```json
{

"id": "1fa179a6-b507-4857-ad72-eb5513ef05c8",

"type": "UAVTMS",

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

"refSoftwareApplication": {

"value": "23821045-33d4-46ec-b777-98f461bf4856",

"type": "Reference"

},

"operationalInstallation": {

"value": "http://www.example.com",

"type": "URL"

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

}

}
```