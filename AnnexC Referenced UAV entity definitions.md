**Referenced UAV entities (Informative)**

**Table of Contents**

[1.1 Introduction 2](#introduction)

[1.2 Automatic Dependent Surveillance–Broadcast Message entity descriptions:
2](#automatic-dependent-surveillancebroadcast-message-entity-descriptions)

[1.3 State Vector entity descriptions: 3](#state-vector-entity-descriptions)

[1.4 flightMessage descriptions: 4](#flightmessage-descriptions)

[1.4.1 UTM Flight Message description: 5](#utm-flight-message-description)

[1.4.2 flightDeclaration 5](#flightdeclaration)

[1.4.3 flightPart 6](#flightpart)

[1.4.4 altitude 6](#altitude)

[1.4.5 operationMode 7](#operationmode)

1.1 Introduction
------------

To provide additional clarity we provide a snapshot of the referenced UAV entity
definitions below. This information is informative only.

1.2 Automatic Dependent Surveillance–Broadcast Message entity descriptions:
-----------------------------------------------------------------------

Automatic Dependent Surveillance–Broadcast (ADS-B) is a satellite based
surveillance system. Aircraft position, velocity, together with identification
are transmitted automatically through Mode-S Extended (1090 MHz) transponders.

The majority of modern aircrafts are broadcasting ADS-B messages constantly (1
second period). The ADSB Message is a binary message with the following protocol
specification.

An ADS-B message is 112 bits long, and consists of 5 main parts:

| DF | CA | ICAO | TC¦&DATA | PI |
|----|----|------|----------|----|


>   This table defines the key components and bit structure of an ADS-B message:

| nBits | Bits     | Abbreviation | Name                                |
|-------|----------|--------------|-------------------------------------|
| 5     | 1 – 5    | DF           | Downlink Format                     |
| 3     | 6 – 8    | CA           | Capability Additional identifier    |
| 24    | 9 – 32   | ICAO         | ICAO aircraft address               |
| 4     | 33 - 37  | TC           | Data Type Code                      |
| 52    | 38 - 88  | DATA         | Data pertaining to the message type |
| 24    | 89 – 112 | PI           | Parity/Interrogator ID              |

Further information may be found here:

<https://media.readthedocs.org/pdf/adsb-decode-guide/latest/adsb-decode-guide.pdf>

<https://global.ihs.com/doc_detail.cfm?item_s_key=00536618&item_key_date=871131&rid=GS>

<https://www.faa.gov/nextgen/programs/adsb/>

1.3 State Vector entity descriptions:
---------------------------------

The Open Sky State Vector Message is interpreted, reformatted data that may be
extracted from the OpenSky platform using an API defined here:

<https://opensky-network.org/apidoc/index.html#state-vectors>

Each OpenSky State vector has the following properties

| Property | Type    | Description                                                                                                                                                        |
|----------|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| time     | integer | The time which the state vectors in this response are associated with. All vectors represent the state of a vehicle with the interval [time−1,time][time−1,time] . |
| states   | array   | The state vectors.                                                                                                                                                 |

The states property is a two-dimensional array. Each row represents a [state
vector](https://opensky-network.org/apidoc/index.html#state-vectors) and
contains the following fields:

| Index | Property       | Type    | Description                                                                                                                               |
|-------|----------------|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 0     | icao24         | String  | Unique ICAO 24-bit address of the transponder in hex string representation.                                                               |
| 1     | callsign       | String  | Callsign of the vehicle (8 chars). Can be null if no callsign has been received.                                                          |
| 2     | origin_country | String  | Country name inferred from the ICAO 24-bit address.                                                                                       |
| 3     | time_position  | Float   | Unix timestamp (seconds) for the last position update. Can be null if no position report was received by OpenSky within the past 15s.     |
| 4     | time_velocity  | Float   | Unix timestamp (seconds) for the last velocity update. Can be null if no velocity report was received by OpenSky within the past 15s.     |
| 5     | longitude      | Float   | WGS-84 longitude in decimal degrees. Can be null.                                                                                         |
| 6     | latitude       | Float   | WGS-84 latitude in decimal degrees. Can be null.                                                                                          |
| 7     | altitude       | Float   | Barometric or geometric altitude in meters. Can be null.                                                                                  |
| 8     | on_ground      | boolean | Boolean value which indicates if the position was retrieved from a surface position report.                                               |
| 9     | velocity       | Float   | Velocity over ground in m/s. Can be null.                                                                                                 |
| 10    | heading        | Float   | Heading in decimal degrees clockwise from north (i.e. north=0°). Can be null.                                                             |
| 11    | vertical_rate  | Float   | Vertical rate in m/s. A positive value indicates that the airplane is climbing, a negative value indicates that it descends. Can be null. |
| 12    | sensors        | int[]   | IDs of the receivers which contributed to this state vector. Is null if no filtering for sensor was used in the request.                  |

Further information is available here:

<https://opensky-network.org/apidoc/index.html#state-vectors>

1.4 flightMessage descriptions:
---------------------------

The UTM Flight Message is part of an event-based notification system promoted by
the Global UTM association ( <https://gutma.org/> ) where the Originating Party
notifies Interested Parties of a flight or changes to a previously announced
flight.

The flightMessage is the primary entity exchanged between Originating and
Interested Parties. Each UTM Flight Message has the following properties

### 1.4.1 UTM Flight Message description:

| Name              | Description                                                                                                                                                     | Type                       |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|
| flightId          | Identifier provided by the Originating Party that uniquely identifies this declaration from other declarations provided by the same Originating Party.          | string                     |
| sequenceNumber    | A number that represents the version of this message data. When a record is modified, the sequence number must be numerically greater than the previous update. | number (uint64)            |
| flightDeclaration | A flightDeclaration object describing this proposed flight. To delete a flight, this field should be null.                                                      | flightDeclaration          |
| version           | The version of this protocol that the message has been implemented from.                                                                                        | string - currently "0.2.0" |

### 1.4.2 flightDeclaration

| Name                  | Description                                                                                                                                                                                                                                                                                                                         | Type                                                    |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------|
| **parts**             | One or more part that make up this flight                                                                                                                                                                                                                                                                                           | array                                                   |
| **purpose**           | A human readable description of the reason the flight is being conducted. This field can be omitted if the end user chooses not to share the purpose of their flight. (*See notes*)                                                                                                                                                 | string                                                  |
| **expectTelemetry**   | A flag indicting whether it is expected that telemetry will be available during the flight.                                                                                                                                                                                                                                         | boolean                                                 |
| **originatingParty**  | The name of the party that the flight was originally declared with.                                                                                                                                                                                                                                                                 | string                                                  |
| **contactUrl**        | The URL to be use to initiate contact with the user. This can be used to make nuisance report about this flight or for law enforcement to start the process of identifying a drone operator. It is expected that the flightId will be used as part of this Url as the Url must be standalone and not require any other information. | string                                                  |
| **operationMode**     | The mode that the drone is being operated in.                                                                                                                                                                                                                                                                                       | operationMode { "vlos", "evlos", "bvlos", "automated" } |
| **idents**            | Any idents that are associated with this flight                                                                                                                                                                                                                                                                                     | array *[optional]*                                      |
| **actualTakeOffTime** | The time the flight took off. This value can be null or omitted if the take-off time is not known                                                                                                                                                                                                                                   | datetime *[optional]*                                   |
| **actualLandingTime** | The time the flight completed. This value can be null or omitted if the landing time is not known                                                                                                                                                                                                                                   | datetime *[optional]*                                   |

### 1.4.3 flightPart

A flight consists of one or more parts. Each part has a start and end time as
well as a geography and maximum altitude.

| Name            | Description                                                                                          | Type     |
|-----------------|------------------------------------------------------------------------------------------------------|----------|
| **id**          | An identifier that uniquely identifies this part within this flight.                                 | string   |
| **geography**   | A Polygon or LineString describing the planned operating area or route.                              | geometry |
| **startTime**   | The time that the flight is expected to start.                                                       | datetime |
| **endTime**     | The time that the flight is expected to be completed by. This must always be greater than startTime. | datetime |
| **maxAltitude** | The maximum altitude that the drone will achieve during the *flightPart*.                            | altitude |

### 1.4.4 altitude

Altitude is specified in Metres above the specified datum. The altitude type
combines both values.

| Name       | Description                                                                                                                                                                                                              | Type                                            |
|------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|
| **metres** | The height above the specified datum in metres                                                                                                                                                                           | number                                          |
| **datum**  | The datum that describes what the altitude measurement is relative to                                                                                                                                                    | altitudeDatum { "agl", "amsl", "sps", "wgs84" } |
| Datum      | Description                                                                                                                                                                                                              |                                                 |
| agl        | Above Ground Level                                                                                                                                                                                                       |                                                 |
| amsl       | Above Mean Sea Level. This value is included for completeness. As this datum is not valid for any of the messages in this specification, the issue of defining the tidal datum for Mean Sea Level has not been included. |                                                 |
| sps        | Altitude where a barometric altimeter would be set to the Standard Pleasure Setting. This is effectively of the Flight Level multiplied by 100 and converted to metres.                                                  |                                                 |
| wgs84      | Distance above the WGS 84 datum.                                                                                                                                                                                         |                                                 |

### 1.4.5 operationMode

| operationMode | Description                                                                                                               |
|---------------|---------------------------------------------------------------------------------------------------------------------------|
| **vlos**      | The drone is being flown by a human pilot within visual line of sight                                                     |
| **evlos**     | The drone is being flown by a human pilot with extended visual line of sight – typically enabled by the use of observers. |
| **bvlos**     | The drone is being flown by a human pilot beyond visual line of sight                                                     |
| **automated** | The drone does not have a human pilot                                                                                     |

Further information is available here:

<https://bitbucket.org/global_utm/flight-declaration-protocol/>
