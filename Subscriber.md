### Subscriber

This entity contains a harmonised description of a subscriber to a service. This
entity is primarily associated with the Smart Home vertical segment and related
IoT applications.

&lt;Subscriber&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**Subscribe**r".                                                                                                                                                                                                                                                                                                                                                        | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;Subscriber&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name       | Attribute Type              | Description                                                                                                                                                                                                                                                             | Mandatory/ Optional/ Recommended | May be Null |
|----------------------|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| subscriptionId       | Reference                   | A reference to the unique id of the subscription service.                                                                                                                                                                                                               | M                                | N           |
| startDate            | DateTime                    | The start timestamp for this subscription as an ISO8601 sequence of characters in UTC.                                                                                                                                                                                  | R                                | Y           |
| endDate              | DateTime                    | The end timestamp for this subscription as an ISO8601 sequence of characters in UTC.                                                                                                                                                                                    | R                                | Y           |
| duration             | Number                      | The duration of the subscription in calendar months.                                                                                                                                                                                                                    | O                                | Y           |
| category             | List                        | The category of subscription. A selection from an enumerated list including: **prepay, postpay, utility, broadband, electric, gas, heat, water, landline, mobile, tv, security, financial, energy management, other.**                                                  | O                                | Y           |
| averageMonthly Usage | Number or QuantitativeValue | Average monthly usage of the subscription service.                                                                                                                                                                                                                      | O                                | Y           |
| subscribed           | List of Reference           | An List containing a JSON encoded sequence of characters referencing the unique ids of those persons or organisations that have subscribed to this service. Related to a Schema.org person or organization. <https://schema.org/Person https://schema.org/Organization> | O                                | Y           |

#### Subscriber JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/4bdc07091dd7fd8af7abcb58103ba513
```json
{
  "id": "c1716dea-6a4d-4171-a733-916123942f09",
  "type": "Subscriber",
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
  "subscriptionId": {
    "value": "65b1ccb0-ee32-41c1-9746-7ba83fb0f0f1",
    "type": "Reference"
  },
  "startDate": {
    "value": "2016-08-22T10:18:16Z",
    "type": "DateTime"
  },
  "endDate": {
    "value": "2017-08-22T23:59:59Z",
    "type": "DateTime"
  },
  "duration": {
    "value": 12,
    "type": "Number"
  },
  "category": {
    "value": [
      "utility"
    ],
    "type": "List"
  },
  "averageMonthlyUsage": {
    "value": 28,
    "type": "Number"
  },
  "subscribed": {
    "value": [
      "31dd0e29-45b6-476f-9756-a70f8141dcf3"
    ],
    "type": "List"
  }
}
```
