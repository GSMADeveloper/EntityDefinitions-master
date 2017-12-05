### AirQualityObserved

This entity contains a harmonised description of the air quality observed at a
particular location and time. This entity is primarily associated with the
vertical segment of the environment and may also be used in smart homes, smart
cities, agriculture, industry and related IoT applications.

&lt;AirQualityObserved&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**AirQualityObserved**".                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. <http://schema.org/version/2.0/>) or a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |

&lt;AirQualityObserved&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name  | Attribute Type       | Description                                                                                                                                                                                                                                                                                                                                                                                                                            | Mandatory/ Optional/ Recommended | May be Null |
|-----------------|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| refPOI          | Reference            | A reference to the unique ids of the Point of Interest (monitoring station) that originated this observation.                                                                                                                                                                                                                                                                                                                          | O                                | Y           |
| refDevice       | List of Reference    | A list of references to the unique ids of the devices that originated this observation.                                                                                                                                                                                                                                                                                                                                                | O                                | Y           |
| location        | geo:json             | The geo:json encoded polygon or point location, of this observation.                                                                                                                                                                                                                                                                                                                                                                   | M                                | N           |
| dateObserved    | DateTime             | The date and time of this observation in ISO8601 UTC format.                                                                                                                                                                                                                                                                                                                                                                           | R                                | Y           |
| PM2.5           | ExtQuantitativeValue | **value --- Measured value timestamp --- date and time when measurement was taken unitCode --- normally GQ unitText --- normally microgram per cubic metre additonalProperty airQualityLevel a choice from an enumerated list (good,moderate,unhealthyForSensitiveGroups,unhealthy,veryUnhealthy,hazardous) valueReference a choice from an enumerated list determined according to the (US EPA standard, EU standard, UK standard.)** | O                                | Y           |
| PM10            | ExtQuantitativeValue | **value --- Measured value timestamp --- date and time when measurement was taken unitCode --- normally GQ unitText --- normally microgram per cubic metre additonalProperty airQualityLevel a choice from an enumerated list (good,moderate,unhealthyForSensitiveGroups,unhealthy,veryUnhealthy,hazardous) valueReference a choice from an enumerated list determined according to the (US EPA standard, EU standard, UK standard.)** | O                                | Y           |
| CO              | ExtQuantitativeValue | **value --- Measured value timestamp --- date and time when measurement was taken unitCode --- normally GQ unitText --- normally microgram per cubic metre additonalProperty airQualityLevel a choice from an enumerated list (good,moderate,unhealthyForSensitiveGroups,unhealthy,veryUnhealthy,hazardous) valueReference a choice from an enumerated list determined according to the (US EPA standard, EU standard, UK standard.)** | O                                | Y           |
| O3              | ExtQuantitativeValue | **value --- Measured value timestamp --- date and time when measurement was taken unitCode --- normally GQ unitText --- normally microgram per cubic metre additonalProperty airQualityLevel a choice from an enumerated list (good,moderate,unhealthyForSensitiveGroups,unhealthy,veryUnhealthy,hazardous) valueReference a choice from an enumerated list determined according to the (US EPA standard, EU standard, UK standard.)** | O                                | Y           |
| SO2             | ExtQuantitativeValue | **value --- Measured value timestamp --- date and time when measurement was taken unitCode --- normally GQ unitText --- normally microgram per cubic metre additonalProperty airQualityLevel a choice from an enumerated list (good,moderate,unhealthyForSensitiveGroups,unhealthy,veryUnhealthy,hazardous) valueReference a choice from an enumerated list determined according to the (US EPA standard, EU standard, UK standard.)** | O                                | Y           |
| NO              | ExtQuantitativeValue | **value --- Measured value timestamp --- date and time when measurement was taken unitCode --- normally GQ unitText --- normally microgram per cubic metre additonalProperty airQualityLevel a choice from an enumerated list (good,moderate,unhealthyForSensitiveGroups,unhealthy,veryUnhealthy,hazardous) valueReference a choice from an enumerated list determined according to the (US EPA standard, EU standard, UK standard.)** | O                                | Y           |
| NO2             | ExtQuantitativeValue | **value --- Measured value timestamp --- date and time when measurement was taken unitCode --- normally GQ unitText --- normally microgram per cubic metre additonalProperty airQualityLevel a choice from an enumerated list (good,moderate,unhealthyForSensitiveGroups,unhealthy,veryUnhealthy,hazardous) valueReference a choice from an enumerated list determined according to the (US EPA standard, EU standard, UK standard.)** | O                                | Y           |
| NOx             | ExtQuantitativeValue | **value --- Measured value timestamp --- date and time when measurement was taken unitCode --- normally GQ unitText --- normally microgram per cubic metre additonalProperty airQualityLevel a choice from an enumerated list (good,moderate,unhealthyForSensitiveGroups,unhealthy,veryUnhealthy,hazardous) valueReference a choice from an enumerated list determined according to the (US EPA standard, EU standard, UK standard.)** | O                                | Y           |
| airQualityIndex | ExtQuantitativeValue | **Value Calculated Air Quality Index value. valueReference a choice from an enumerated list calculated according to the (US EPA standard, EU standard, UK standard.)** [^1]                                                                                                                                                                                                                                                            | O                                | Y           |

[^1]: <https://cfpub.epa.gov/airnow/index.cfm?action=aqibasics.aqi>

#### AirQualityObserved JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/d1e46adc706d986ee9e752a5b425bcca>

```json

{

"id": "c9f32b35-a185-48e2-835f-c521efc294ab",

"type": "AirQualityObserved",

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

"refPOI": {

"value": [

"cdfd9cb8-ae2b-47cb-a43a-b9767ffd5c84"

],

"type": "List"

},

"refDevice": [

"5c9fb9dd-fc13-4fda-8f4c-f99a04f6f858"

],

"location": {

"value": {

"type": "Point",

"coordinates": [

\-104.99404,

39.75621

]

},

"type": "geo:json"

},

"dateObserved": {

"value": "2016-08-08T10:18:16Z",

"type": "DateTime"

},

"PM2.5": {

"type": "ExtQuantitativeValue",

"value": {

"value": 187,

"unitCode": "GQ",

"airQualityLevel": "hazardous"

}

},

"PM10": {

"type": "ExtQuantitativeValue",

"value": {

"value": 50,

"unitCode": "GQ",

"airQualityLevel": "unhealthy"

}

},

"CO": {

"type": "ExtQuantitativeValue",

"value": {

"value": 0.8,

"unitCode": "GQ",

"airQualityLevel": "good"

}

},

"O3": {

"type": "ExtQuantitativeValue",

"value": {

"value": 300,

"unitCode": "GQ",

"airQualityLevel": "very unhealthy"

}

},

"SO2": {

"type": "ExtQuantitativeValue",

"value": {

"value": 7,

"unitCode": "GQ",

"airQualityLevel": "good"

}

},

"NO": {

"type": "ExtQuantitativeValue",

"value": {

"value": 137,

"unitCode": "GQ",

"airQualityLevel": "unhealthy"

}

},

"NO2": {

"type": "ExtQuantitativeValue",

"value": {

"value": 63,

"unitCode": "GQ",

"airQualityLevel": "good"

}

},

"NOx": {

"type": "ExtQuantitativeValue",

"value": {

"value": 273,

"unitCode": "GQ",

"airQualityLevel": "very unhealthy"

}

},

"airQualityIndex": {

"type": "ExtQuantitativeValue",

"value": {

"airQualityLevel": "very unhealthy"

}

}

}
```
