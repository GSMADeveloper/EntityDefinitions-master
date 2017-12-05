###  MachineModel

This entity contains a harmonised description of a generic machine model. This
entity is primarily associated with the industry segment and related IoT
applications. The machineModel includes a hierarchical structure that allows
machine models to be grouped in a flexible way.

&lt;MachineModel&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**MachineModel**".                                                                                                                                                                                                                                                                                                                                                      | M                                | N           |
| dateCreated    | Date           | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | Date           | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;MachineModel&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name     | Attribute Type    | Description                                                                                                                                                                                                                                                                  | Mandatory/ Optional/ Recommended | May be Null |
|--------------------|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| name               | Text              | The name given to this machine model.                                                                                                                                                                                                                                        | M                                | N           |
| description        | Text              | A description of this machine model.                                                                                                                                                                                                                                         | R                                | Y           |
| manufacturerName   | Text              | The name of manufacturer of this machine model.                                                                                                                                                                                                                              | R                                | Y           |
| brandName          | Text              | A description of this machine model brand name.                                                                                                                                                                                                                              | R                                | Y           |
| version            | Text              | The manufacturer defined version number for the machine model.                                                                                                                                                                                                               | R                                | Y           |
| category           | List              | An List of functional categories which this machineModel supports. Examples include: **robot, cnc, 2dPrinter, 3dPrinter, 3dScanner, lathe, injectionMolding, laserCutter, millingMachine, grindingMachine, stampingMachine, oven, kiln, packaging, mixer, dryer, fan, saw.** | O                                | Y           |
| doc                | URL               | Reference to Product Data Sheet or other manufacturers documentation about this machine.                                                                                                                                                                                     | R                                | Y           |
| root               | Boolean           | A logical indicator that this machineModel is the root of a machineModel hierarchy. **true** indicates it is the root, **false** indicates that it is not the root.                                                                                                          | R                                | Y           |
| refParentModel     | List of Reference | A List containing a JSON encoded sequence of characters referencing the ids of other machine models which this is related to.                                                                                                                                                | O                                | Y           |
| processDescription | Text              | A description of the industrial process carried out by this machine.                                                                                                                                                                                                         | O                                | Y           |
| standardOperations | List              | Lists the standard set of operations supported by this machineModel.                                                                                                                                                                                                         | O                                | Y           |

#### MachineModel JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/d292853b17e78269856715a005b7a733
```json
{
  "id": "e01f13d1-fea4-4cc4-92c9-0d9fadb2c509",
  "type": "MachineModel",
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
  "name": {
    "value": "CA1256b",
    "type": "Text"
  },
  "description": {
    "value": "Machine to screen print t-shirts",
    "type": "Text"
  },
  "manufacturerName": {
    "value": "ScreenOPrint, Inc.",
    "type": "Text"
  },
  "brandName": {
    "value": "QuickT",
    "type": "Text"
  },
  "version": {
    "value": "v1",
    "type": "Text"
  },
  "category": {
    "value": [
      "2dPrinter"
    ],
    "type": "List"
  },
  "doc": {
    "value": "http://www.example.com",
    "type": "URL"
  },
  "root": {
    "value": false,
    "type": "Boolean"
  },
  "refParentModel": {
    "value": [
      "4146335f-839f-4ff9-a575-6b4e6232b734",
      "c44fc765-51a7-4f71-bf1e-22e874c35180"
    ],
    "type": "List"
  },
  "processDescription": {
    "value": "Industrial printer used to mass print t-shirts",
    "type": "Text"
  },
  "standardOperations": {
    "value": [
      "print"
    ],
    "type": "List"
  }
}
```
