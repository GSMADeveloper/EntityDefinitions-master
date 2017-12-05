### <br>Product

This entity contains a harmonised description of a generic product. This entity
is primarily associated with products and supply chains. It is the harmonised
description of the <http://gs1.org/voc/Product>:

&lt;Product&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**Product**".                                                                                                                                                                                                                                                                                                                                                           | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;Product&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name   | Attribute Type    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Mandatory/ Optional/ Recommended | May be Null |
|------------------|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| productType      | Reference         | Unique id of this product type. Refers to the relevant ProductType record.                                                                                                                                                                                                                                                                                                                                                                                               | R                                | Y           |
| supplierName     | Text              | The details of the local retailer of this product.                                                                                                                                                                                                                                                                                                                                                                                                                       | R                                | Y           |
| category         | List              | A choice from an enumerated list. including: **fertiliser, herbicide, pesticide, other**                                                                                                                                                                                                                                                                                                                                                                                 | R                                | Y           |
| gtin             | Text              | GS1 product code A Global Trade Item Number (GTIN) is the 14 digit GS1 Identification Key used to identify products. The key comprises a GS1 Company Prefix followed by an Item Reference Number and a Check Digit. See http://www.gs1.org/gtin for more details. There are four GTIN formats. A uniform 14-digit format is required for this harmonised model, add leading zeros as required: 000000nnnnnnnn (GTIN-8) 00nnnnnnnnnnnn (GTIN-12) 0nnnnnnnnnnnnn (GTIN-13) | O                                | Y           |
| productName      | Text              | The name of this product.                                                                                                                                                                                                                                                                                                                                                                                                                                                | R                                | Y           |
| description      | Text              | A description of this product.                                                                                                                                                                                                                                                                                                                                                                                                                                           | R                                | Y           |
| manufacturerName | Text              | The name of manufacturer of this product.                                                                                                                                                                                                                                                                                                                                                                                                                                | R                                | Y           |
| brand            | Text              | A description of this brand name.                                                                                                                                                                                                                                                                                                                                                                                                                                        | R                                | Y           |
| inPackageWidth   | QuantitativeValue | The width of the product in the package, as measured according to the GS1 Package Measurement Rules. See http://www.gs1.org/package-measurement-rules-implementation-guide for more details.                                                                                                                                                                                                                                                                             | O                                | Y           |
| inPackageDepth   | QuantitativeValue | The depth of the product in its packaging, as measured according to the GS1 Package Measurement Rules. See http://www.gs1.org/package-measurement-rules-implementation-guide for more details.                                                                                                                                                                                                                                                                           | O                                | Y           |
| inPackageHeight  | QuantitativeValue | The height of the product in the package, as measured according to the GS1 Package Measurement Rules. See http://www.gs1.org/package-measurement-rules-implementation-guide for more details.                                                                                                                                                                                                                                                                            | O                                | Y           |
| netWeight        | QuantitativeValue | Used to identify the net weight of the product. Net Weight excludes all packaging material, including the packaging material of all lower-level GTINs. Example:11.5 kgm.                                                                                                                                                                                                                                                                                                 | O                                | Y           |
| grossWeight      | QuantitativeValue | Used to identify the gross weight of the product. The gross weight includes all packaging materials of the product. At pallet level the productGrossWeight includes the weight of the pallet itself. For example, 200 GRM, value - total pounds, total grams, etc.                                                                                                                                                                                                       | O                                | Y           |
| countryOfOrigin  | Text              | Country where the product was manufactured, harvested, mined etc. Code indicating the country of origin of the product.                                                                                                                                                                                                                                                                                                                                                  | O                                | Y           |
| gpcCategoryCode  | Text              | Product category code 8-digit code (GPC "Brick Value") specifying a product category according to the GS1 Global Product Classification (GPC) standard. For more information see http://www.gs1.org/gpc                                                                                                                                                                                                                                                                  | O                                | Y           |
| image            | List of URLs      | List of URLs of images of the product. Each URL links to a file containing a visual representation of the product either as catalogue images or as actual images of the specific product.                                                                                                                                                                                                                                                                                | O                                | Y           |
| growerURL        | URL               | URL of a grower of a product (particularly agricultural)                                                                                                                                                                                                                                                                                                                                                                                                                 | O                                | Y           |
| manufacturer     | Organization      | Name of the product manufacturer The organization that produces the item.                                                                                                                                                                                                                                                                                                                                                                                                | O                                | Y           |

#### Product JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/0817901a9f8ae3440ab751513acdf88e
```json
{
  "id": "6223903a-d8c5-4e7e-af24-cc90967feb61",
  "type": "Product",
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
  "productType": {
    "type": "Reference",
    "value": "27242396-032d-11e7-83f3-83fdf070a882"
  },
  "supplierName": {
    "type": "Text",
    "value": "Acme Products, Inc."
  },
  "category": {
    "value": [
      "Vegetables"
    ],
    "type": "List"
  },
  "gtin": {
    "type": "Text",
    "value": "01234567890"
  },
  "productName": {
    "type": "Text",
    "value": "Paprika, dried, powdered"
  },
  "description": {
    "type": "Text",
    "value": "Natural paprika grown in Suffolk"
  },
  "manufacturerName": {
    "type": "Text",
    "value": "Paprika Company"
  },
  "brand": {
    "type": "Text",
    "value": "All natural Suffolk spice"
  },
  "inPackageWidth": {
    "type": "QuantitativeValue",
    "value": {
      "unitText": "inch",
      "unitCode": "INH",
      "value": 25
    }
  },
  "inPackageDepth": {
    "type": "QuantitativeValue",
    "value": {
      "unitText": "inch",
      "unitCode": "INH",
      "value": 5
    }
  },
  "inPackageHeight": {
    "type": "QuantitativeValue",
    "value": {
      "unitText": "inch",
      "unitCode": "INH",
      "value": 15
    }
  },
  "netWeight": {
    "type": "QuantitativeValue",
    "value": {
      "unitText": "grammes",
      "unitCode": "GRM",
      "value": 2500
    }
  },
  "grossWeight": {
    "type": "QuantitativeValue",
    "value": {
      "unitText": "grammes",
      "unitCode": "GRM",
      "value": 3000
    }
  },
  "countryOfOrigin": {
    "type": "Text",
    "value": "GB"
  },
  "gpcCategoryCode": {
    "type": "Text",
    "value": "00786613"
  },
  "Image": {
    "type": "List",
    "value": [
      "http://example.com/productImg1.jpg",
      "http://example.com/productImg2.jpg"
    ]
  },
  "growerURL": {
    "type": "URL",
    "value": "http://www.example.com"
  },
  "manufactuer": {
    "type": "Organization",
    "value": {
      "name": "Paprika Company"
    }
  }
}
```
