### <br>FleetVehicle

This entity contains a harmonised description of a generic fleet vehicle such as
a delivery vehicle, an ambulance or a postal vehicle. This entity is primarily
associated with the vertical segment of the transport and logistics but may also
be used many other related IoT applications.

&lt;FleetVehicle&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**FleetVehicle**".                                                                                                                                                                                                                                                                                                                                                      | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. <http://schema.org/version/2.0/>) or a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;FleetVehicle&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name   | Attribute Type | Description                                                                                                                                                                              | Mandatory/ Optional/ Recommended | May be Null |
|------------------|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refVehicle       | Reference      | A a JSON encoded sequence of characters that reference the unique id of the related Vehicle entity that describes the core attributes of this Fleet Vehicle.                             | M                                | N           |
| fleetVehicleType | Text           | The type of the Vehicle for example, Taxi, Ambulance, Postal, Fire & Rescue, Delivery. This is free text.                                                                                | M                                | N           |
| operatingCompany | Organization   | A JSON encoded sequence of characters referencing the unique Ids of the operating company of this fleet vehicle. Related to a Schema.org organization. <https://schema.org/Organization> | M                                | N           |
| operator         | Person         | The usual operator/driver/keeper of this fleet vehicle encoded as a Schema.org person. <https://schema.org/Person> Should be null if there is no usual operator/driver/keeper.           | R                                | Y           |

#### FleetVehicle JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/0bc781dd5279766aa50edcb1ee03907d

```json
{
  "id": "1fa179a6-b507-4857-ad72-eb5513ef05c6",
  "type": "FleetVehicle",
  "dateCreated": {
    "value": "2017-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "dateModified": {
    "value": "2017-08-08T10:18:16Z",
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
    "value": "23821045-33d4-46ec-b777-98f461bf4856",
    "type": "Reference"
  },
  "fleetVehiclelType": {
    "value": "Ambulance",
    "type": "Text"
  },
  "operatingCompany": {
    "type": "Organization",
    "value": {
      "name": "NHS"
    }
  },
  "operator": {
    "value": {
      "givenName": "John Smith",
      "jobTitle": "Ambulance Operator"
    },
    "type": "Person"
  }
}
```