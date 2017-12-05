### UAVModel

This entity contains a harmonised description of a generic Unmanned Ariel
Vehicle (UAV) model and is applicable to UAV command and control and related UAV
transport applications.

&lt;UAVModel&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity. A globally unique reference to this entity instance. It is recommended ids comply with RFC4122.                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to “UAVModel”.                                                                                                                                                                                                                                                                                                                                                              | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp. This will usually be allocated by the storage platform.                                                                                                                                                                                                                                                                                                        | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity. This will usually be allocated by the storage platform. A null value in this field or a value equivalent to dateCreated means the entity has not been modified since being created.                                                                                                                                                     | O                                | Y           |
| source         | URL            | A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.                                                                                                                                                                                               | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the provider of the harmonised data entity.                                                                                                                                                                                                                                                                                                          | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. <http://schema.org/version/2.0/>) or a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;UAVModel&gt;&lt;EntitySpecificAttributes&gt;

| Attribute Name    | Attribute Type    | Description                                                                                                                                                                                                                                                                            | Mandatory/ Optional/ Recommended | May be Null |
|-------------------|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| model             | Text              | The UAV model’s identifier, which may be a UAVModel name.                                                                                                                                                                                                                              | M                                | N           |
| doc               | URL               | Reference to Product Data Sheet or other manufacturer’s documentation about this UAVModel.                                                                                                                                                                                             | R                                | Y           |
| description       | Text              | A description of this UAVModel.                                                                                                                                                                                                                                                        | R                                | Y           |
| manufacturerName  | Text              | The name of manufacturer of this UAVModel.                                                                                                                                                                                                                                             | R                                | Y           |
| brandName         | Text              | A description of the brand name of this UAVModel.                                                                                                                                                                                                                                      | R                                | Y           |
| category          | Text              | The work category of the UAVModel A choice from the following list: “Aerial_photography, Plant_protection, Industry, Routing_inspection, Mailing, Transportation”                                                                                                                      | R                                | Y           |
| rotorNumber       | Number            | The number of the rotors of the UAVModel                                                                                                                                                                                                                                               | R                                | Y           |
| fuelType          | Text              | The fuel type powering the UAVModel. A choice from an enumerated list describing the power source. One of: gasoline, petrol(unleaded), petrol(leaded), petrol, diesel, electric, hydrogen, lpg autogas, cng, biodiesel, ethanol, hybrid electric/petrol, hybrid electric/diesel, other | R                                | Y           |
| maxFlightTime     | QuantitativeValue | The maximum duration of flight of the UAVModel with full fuel and no load. Specify value and units of measure                                                                                                                                                                          | R                                | Y           |
| maxFlightAltitude | QuantitativeValue | The maximum flight altitude of the UAVModel above ground. Specify value and units of measure                                                                                                                                                                                           | R                                | Y           |
| maxGroundVelocity | QuantitativeValue | The maximum ground velocity of the UAVModel. Specify value and units of measure                                                                                                                                                                                                        | R                                | Y           |
| minWeight         | QuantitativeValue | The weight of the UAV without fuel or load. Specify value and units of measure                                                                                                                                                                                                         | O                                | Y           |
| minUnladenWeight  | QuantitativeValue | The weight of the UAV with full fuel but no load. Specify value and units of measure                                                                                                                                                                                                   | O                                | Y           |
| maxLoad           | QuantitativeValue | The maximum load that the UAV is permitted to transport. Specify value and units of measure.                                                                                                                                                                                           | O                                | Y           |

#### UAVModel JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/ef967e9b0f6837603af191f69b975ae7
```json
{

"id": "1fa179a6-b507-4857-ad72-eb5513ef05c8",

"type": "UAVModel",

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

"model": {

"value": "UASUSA Recon",

"type": "text"

},

"doc": {

"value": "http://www.uasusa.com/products-services/aircraft/the-recon.html",

"type": "URL"

},

"description": {

"value": "The Recon was constructed and designed to offer a clear payload view,
with the motor and propeller system aft of the payload. It is smaller and more
versatile than many drones, yet robust enough for harsh environment operations.
The wingspan is 2.3 meters. An affordable, versatile, and flexible drone for a
multitude of uses",

"type": "text"

},

"manufactureName": {

"value": "UASVSA",

"type": "text"

},

"brandName": {

"value": "UASVSA",

"type": "text"

},

"category": {

"value": "Industry",

"type": "text"

},

"rotorNumber": {

"value": 4,

"type": "Number"

},

"fuelType": {

"value": "gasoline",

"type": "text"

},

"maxFlightTime": {

"value": {

"value": 100,

"unitCode": "HUR"

},

"type": "QuantitativeValue"

},

"maxFlightAltitude": {

"value": {

"value": 1000,

"unitCode": "MTR"

},

"type": "QuantitativeValue"

},

"maxGroundVelocity": {

"value": {

"value": 100,

"unitCode": "MTS"

},

"type": "QuantitativeValue"

},

"minWeight": {

"value": {

"value": 1,

"unitCode": "KGM"

},

"type": "QuantitativeValue"

},

"minUnladenWeight": {

"value": {

"value": 1.5,

"unitCode": "KGM"

},

"type": "QuantitativeValue"

},

"maxLoad": {

"value": {

"value": 2,

"unitCode": "KGM"

},

"type": "QuantitativeValue"

}

}
```