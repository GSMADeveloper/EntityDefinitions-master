### WeatherForecast

This entity contains a harmonised description of a Weather Forecast. This entity
is primarily associated with the vertical segments of the environment and
agriculture but is applicable to many different applications.

&lt;WeatherForecast&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                                                                                                                                                                               | Mandatory/ Optional/ Recommended | May be Null |
|----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| type           | Text           | Must be equal to "**WeatherForecast**".                                                                                                                                                                                                                                                                                                                                                   | M                                | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                                                                                                                                                                                | M                                | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                                                                                                                                                                         | O                                | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                                                                                                                                                                             | R                                | Y           |
| schemaVersion  | Text or URL    | Indicates the version number of the data entity via either a URL referring to an external entity version (e.g. http://schema.org/version/2.0/) or a a sequence of text characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. If omitted implies a schema version of "1.0" | R                                | Y           |
&lt;WeatherForecast&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name           | Attribute Type                 | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Mandatory/ Optional/ Recommended | May be Null |
|--------------------------|--------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|-------------|
| location                 | geo:json                       | The geo:json encoded map location (point or polygon), of this weather forecast.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | M                                | N           |
| dateRetrieved            | DateTime                       | The date and time the forecast was retrieved in ISO8601 UTC format.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | M                                | N           |
| dateIssued               | DateTime                       | The date and time the forecast was issued by the meteorological bureau in ISO8601 UTC format.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                  |             |
| weatherType              | Text                           | The weather type. A choice from an enumerated list. One of: **notAvailable, clearNight, sunnyDay, partlyCloudy, mist, fog, cloudy, overcast, lightRainShower, drizzle, lightRain, heavy RainShower, heavyRain, sleetShower, sleet, hailShower, hail, lightSnow Shower, lightSnow, heavySnowShower,heavySnow, thunderShower, thunder.**                                                                                                                                                                                                                                                                                                                   | R                                | Y           |
| visibility               | Number or QuantitativeValue    | Defines the forecast visibility nominally in metres or in an alternative measurement according to specified unitCode if QuantitativeValue is used                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | R                                | Y           |
| name                     | Text                           | The name of the weather forecast location.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | M                                | Y           |
| validFrom                | DateTime                       | The date and time the forecast is valid from expressed as an ISO8601 UTC format sequence of characters.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | R                                | Y           |
| validThrough             | DateTime                       | The date and time the forecast is valid to expressed as an ISO8601 UTC format sequence of characters.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | R                                | Y           |
| dayMinimum               | StructuredValue                | Defines the minimum forecast values for defined attributes. Supports the inclusion of the nested attribute values, each of which will be a number. The units of the respective values will match the respective main attributes for temperature/ relative humidity. **temperature, feelsLikeTemperature, relativeHumidity temperature** -- The forecasted minimum temperature for the period in degrees Celsius. **feelsLikeTemperature** – The forecasted feels like temperature for the period in degrees Celsius. **relativeHumidity** -- The relative humidity expressed a number between 0 ≤ RelativeHumidity ≤ 1 representing the range 0% to 100% | O                                | Y           |
| dayMaximum               | StructuredValue                | Defines the maximum forecast values for defined attributes. Supports the inclusion of the nested attribute values, each of which will be a number. The units of the respective values will match the respective main attributes for temperature/ relative humidity. **temperature, feelsLikeTemperature, relativeHumidity temperature** -- The forecasted maximum temperature for the period in degrees Celsius. **feelsLikeTemperature –** The forecasted feels like temperature for the period in degrees Celsius. **relativeHumidity --** The relative humidity expressed a number between 0 ≤ RelativeHumidity ≤ 1 representing the range 0% to 100% | O                                | Y           |
| address                  | PostalAddress                  | The weather forecast location encoded as a Schema.org PostalAddress. [https://schema.org/PostalAddress](https://schema.org/Address)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | R                                | Y           |
| temperature              | Number or ExtQuantitativeValue | The temperature expressed in degrees Celsius.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | R                                | Y           |
| windDirection            | Number or ExtQuantitativeValue | The wind direction expressed in degrees compared to geographic North (measured clockwise).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | O                                | Y           |
| windSpeed                | Number or ExtQuantitativeValue | The forecasted wind speed in m/s.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | O                                | Y           |
| uVIndexMax               | Number                         | The maximum UV index for the period, based on the World Health Organization's UV Index measure.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | O                                | Y           |
| relativeHumidity         | Number or ExtQuantitativeValue | The relative humidity expressed a number between 0 ≤ RelativeHumidity ≤ 1 representing the range 0% to 100%                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | O                                | Y           |
| precipitationProbability | Number or ExtQuantitativeValue | The probability of precipitation, expressed as a number between 0 ≤ precipitationProbability ≤ 1 representing the range 0% to 100%                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | O                                | Y           |
| refPointOfInterest       | List of Reference              | A JSON encode sequence of characters referencing the unique ids of the associated group of pointOfInterests.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | O                                | Y           |

#### WeatherForecast JSON

The JSON code can be downloaded from:

https://gist.github.com/GSMADeveloper/fe74d7f9573c53bc46b5199d2ab9c847

```json
{
  "id": "7453c443-290d-44ef-a60f-d4c087010c88",
  "type": "WeatherForecast",
  "dateCreated": {
    "value": "2016-08-08 T10:18:16Z ",
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
  "location": {
    "value": {
      "type": "Point",
      "coordinates": [
        -104.99404,
        39.75621
      ]
    },
    "type": "geo:json"
  },
  "dateRetrieved": {
    "value": "2016-08-16T10:18:16Z",
    "type": "DateTime"
  },
  "dateIssued": {
    "value": "2016-08-10T10:18:16Z",
    "type": "DateTime"
  },
  "weatherType": {
    "value": "sunnyDay",
    "type": "Text"
  },
  "visibility": {
    "value": 1500,
    "type": "Number"
  },
  "name": {
    "value": "London City",
    "type": "Text"
  },
  "validFrom": {
    "value": "2016-08-10T10:18:16Z",
    "type": "DateTime"
  },
  "validThrough": {
    "value": "2016-08-29T10:18:16Z",
    "type": "Text"
  },
  "dayMinimum": {
    "value": {
      "temperature": 30,
      "feelsLikeTemperature": 32,
      "relativeHumidity": 0.22
    },
    "type": "StructuredValue"
  },
  "dayMaximum ": {
    "value": {
      "temperature": 33,
      "feelsLikeTemperature": 38,
      "relativeHumidity": 0.52
    },
    "type": "StructuredValue"
  },
  "address": {
    "type": "PostalAddress",
    "value": {
      "addressLocality": "London",
      "postalCode": "EC4N 8AF",
      "streetAddress": "25 Walbrook"
    }
  },
  "temperature": {
    "value": 30,
    "type": "Number"
  },
  "windDirection": {
    "value": 122,
    "type": "Number"
  },
  "windSpeed": {
    "value": 3,
    "type": "Number"
  },
  "uVIndexMax": {
    "value": 5,
    "type": "Number"
  },
  "relativeHumidity": {
    "value": 0.1,
    "type": "Number"
  },
  "precipitationProbability": {
    "value": 0.05,
    "type": "Number"
  },
  "refPointOfInterest": {
    "value": [
      "d0d88168-780c-11e6-b934-2b9831af3c6f"
    ],
    "type": "List"
  }
}
```
