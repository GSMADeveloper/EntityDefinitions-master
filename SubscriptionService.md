### SubscriptionService

This entity contains a harmonised description of a subscription service. This
entity is primarily associated with the Smart Home vertical segment and related
IoT applications.

&lt;SubscriptionService&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**SubscriptionService**".                                                                                                                                                                                                                                                                                                                                               | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;SubscriptionService&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type | Description                                             | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|---------------------------------------------------------|----------------------------------|-------------|
| description    | Text           | The description of this service.                        | M                                | N           |
| offer          | Offer          | Encoded as Schema.org offer. <https://schema.org/Offer> | R                                | Y           |

#### SubscriptionService JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/08c9d422617b832bc1c04d164973c172
```json
{
  "id": "a1e76f95-c627-4ec4-86dc-483431d25352",
  "type": "SubscriptionService",
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
  "description": {
    "value": "Broadband supply service",
    "type": "Text"
  },
  "offer": {
    "type": "Offer",
    "value": {
      "priceCurrency": "USD",
      "price": 50,
      "description": "100 mbps fibre broadband service"
    }
  }
}
```
