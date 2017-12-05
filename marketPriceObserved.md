### marketPriceObserved

This entity contains a harmonised description of a generic commodity, crop or
product price that varies over time (a spot price). This entity is primarily
associated with the agricultural vertical and related IoT applications.

&lt;marketPriceObserved&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity. A globally unique reference to this entity instance. It is recommended ids comply with RFC4122.                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to “marketPriceObserved”.                                                                                                                                                                                                                                                                                                                                                   | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp. This will usually be allocated by the storage platform.                                                                                                                                                                                                                                                                                                        | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity. This will usually be allocated by the storage platform. A null value in this field or a value equivalent to dateCreated means the entity has not been modified since being created.                                                                                                                                                     | O                                | Y           |
| source         | URL            | A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.                                                                                                                                                                                               | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the provider of the harmonised data entity.                                                                                                                                                                                                                                                                                                          | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. <http://schema.org/version/2.0/>) or a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;marketPriceObserved&gt;&lt;EntitySpecificAttributes&gt;

| Attribute Name     | Attribute Type  | Description                                                                                                                                                                                                                             | Mandatory/ Optional/ Recommended | May be Null |
|--------------------|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refEntityInstance  | Reference       | A reference to the unique id of the Entity to which this record relates.                                                                                                                                                                | M                                | N           |
| priceObserved      | StructuredValue | The market price observed represented using schema.org PriceSpecification attributes <http://schema.org/PriceSpecification>                                                                                                             | M                                | N           |
| address            | PostalAddress   | The market location encoded as a Schema.org PostalAddress. <https://schema.org/PostalAddress>                                                                                                                                           | M                                | N           |
| marketScale        | StructuredValue | Unique code assigned to market scale type. The content includes both a name and a value.                                                                                                                                                | M                                | N           |
|                    |                 | "Wholesale":Wholesale market price                                                                                                                                                                                                      |                                  |             |
|                    |                 | "Retail":Retail market price                                                                                                                                                                                                            |                                  |             |
|                    |                 | for example {'name':'Wholesale', 'value':"02"} or {'name':'Retail', 'value':"01"}                                                                                                                                                       |                                  |             |
| priceAverage       | StructuredValue | The five year average market price observed represented using schema.org PriceSpecification attributes <http://schema.org/PriceSpecification>                                                                                           | O                                | Y           |
| refWeatherObserved | Reference       | A reference to the unique id of the related weather observed record.                                                                                                                                                                    | O                                | Y           |

#### marketPriceObserved JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/xxxx

``` json
{
	"id": "398aa5f4-6a81-4dea-9f85-e9869441a257",
	"type": "marketPriceObserved",
	"dateCreated": {
		"value": "2017-06-13T23:59:15.76Z",
		"type": "DateTime"
	},
	"dateModified": {
		"value": "2017-06-13T23:59:15.76Z",
		"type": "DateTime"
	},
	"source": {
		"value": "http://www.samplefarmproduct.com",
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
	"refEntityInstance": {
		"value": "cdfd9cb8-ae2b-47cb-a43a-b9767ffd5c84",
		"type": "Reference"
	},
	"priceObserved": {
		"value": {
			"price": 5,
			"priceCurrency": "USD",
			"validFrom": {
				"value": "2017-08-22T10:18:16Z",
				"type": "DateTime"
			},
			"validThrough": {
				"value": "2017-08-23T10:18:16Z",
				"type": "DateTime"
			}
		},
		"type": "StructuredValue"
	},
	"address": {
		"type": "PostalAddress",
		"value": {
			"addressCountry": "UK",
			"addressLocality": "London"
		}
	},
	"marketScale": {
		"value": {
			"name": "Wholesale",
			"value": "02"
		},
		"type": "StructuredValue"
	},
	"priceAverage": {
		"value": {
			"price": 15,
			"priceCurrency": "USD",
			"validFrom": {
				"value": "2012-08-23T10:18:16Z",
				"type": "DateTime"
			},
			"validThrough": {
				"value": "2017-08-23T10:18:16Z",
				"type": "DateTime"
			}
		},
		"type": "StructuredValue"
	},
	"refWeatherOberserve": {
		"value": "cdfd9cb8-ae2b-47cb-a43a-b9767ffd5c85",
		"type": "Reference"
	}
}
```