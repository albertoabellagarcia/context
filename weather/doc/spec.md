# Smart Data Models: Weather Forecast specification

## Description

This entity contains a harmonised description of a Weather Forecast. This entity
is primarily associated with the vertical segments of the environment and
agriculture but is applicable to many different applications.

This data model has been developed in cooperation with mobile operators and the
[GSMA](https://www.gsma.com/iot/iot-big-data/).
Description of the properties attached to a Weather Forecast  (in case all of them were used)

## Data Model specification

A JSON Schema corresponding to this data model can be found at
[schema.jsonld](../schema.jsonld)
### Basic properties
-   `id` or `@id` : Unique identifier. It shall be a URN for NGSI-LD (jsonld) example in the form
    `urn:ngsi-ld:{{EntityType}}:<identifier>` where `<identifier>` shall be a
    unique ID string.
-   `type` or `@type`: Entity type. It must be equal to `WeatherForecast`.
-   `modifiedAt` or `dateModified` : Last update timestamp of this entity.
    -   Attribute type: Property. [DateTime](https://schema.org/DateTime)
    -   Read-Only. Automatically generated.
-   `createdAt` or `dateCreated` : Entity's creation timestamp.
    -   Attribute type: Property. [DateTime](https://schema.org/DateTime)
    -   Read-Only. Automatically generated.

### Specific properties of the data model     
-   `dateRetrieved` : The date and time the forecast was retrieved in ISO8601
    UTC format.
    -   Attribute type: Property. [DateTime](https://schema.org/DateTime).
    -   Optional
-   `dateIssued` : The date and time the forecast was issued by the
    meteorological bureau in ISO8601 UTC format.
    -   Attribute type: Property. [DateTime](https://schema.org/DateTime).
    -   Mandatory
-   `validity` : Includes the validity period for this forecast as a ISO8601
    time interval. 
    -   Attribute type: Property. [Text](https://schema.org/Text)
    -   Optional
-   `validFrom` : Validity period start date and time in ISO8601 format.
    -   Attribute type: Property. [DateTime](https://schema.org/DateTime).
    -   Optional
-   `validTo` : Validity period end date and time in ISO8601 format.
    -   Attribute type: Property. [DateTime](https://schema.org/DateTime).
    -   Optional
-   `dayMaximum` : Maximum values for the reported period.
    -   Attribute type: Property. [StructuredValue](https://schema.org/StructuredValue)
    -   Subattributes:
        -   `temperature` : Maximum temperature. Explained below.
        -   `feelLikesTemperature`. Maximum feels like temperature. Explained below.
        -   `relativeHumidity`. Maximum relative humidity. Explained below.
-   `dayMinimum` : Minimum values forecasted for the reported period.
    -   Attribute type: Property. [StructuredValue](https://schema.org/StructuredValue)
    -   Subattributes:
        -   `temperature` : Minimum temperature. Explained below.
        -   `feelLikesTemperature`. Minimum feels like temperature. Explained below.
        -   `relativeHumidity`. Minimum relative humidity. Explained below.
    -   Optional
-   `uVIndexMax` : The maximum UV index for the period, based on the World
    Health Organization's UV Index measure.
    -   Normative references:
        [http://www.who.int/uv/intersunprogramme/activities/uv_index/en/](http://www.who.int/uv/intersunprogramme/activities/uv_index/en/)
    -   Attribute type: Property. [Number](https://schema.org/Number)
    -   Optional
    -   Minimum 0
-   `precipitationProbability` : The probability of precipitation, expressed as parts per one)
    -   Attribute type: Property. [Number](https://schema.org/Number)
    -   Optional,
-   `temperature` : Air's temperature observed.
    -   Attribute type: Property. [Number](https://schema.org/Number)
    -   Default unit: Degrees centigrades.
    -   Attribute metadata (only for NGSIv2):
        -   `timestamp` : optional timestamp for the observed value. It can be
            omitted if the observation time is the same as the one captured by
            the `dateObserved` attribute at entity level.
            -   Type: [DateTime](https://schema.org/DateTime)
    -   Optional
-   `feelsLikeTemperature` : Feels like temperature forecasted.
    -   Attribute type: Property. [Number](https://schema.org/Number)
    -   Default unit: Degrees centigrades.
    -   Optional
-   `relativeHumidity` : Air's relative humidity forecasted (expressed in parts per one).
    -   Optional
-   `weatherType` : The observed weather type. It is represented by a comma
    separated list of weather statuses, for instance `overcast, lightRain`.
    -   Attribute type: Property. [Text](https://schema.org/Text)
    -   Allowed values: A combination of (`clearNight`,`sunnyDay`,
        `slightlyCloudy`, `partlyCloudy`, `mist`, `fog`, `highClouds`, `cloudy`,
        `veryCloudy`, `overcast`, `lightRainShower`, `drizzle`, `lightRain`,
        `heavyRainShower`, `heavyRain`, `sleetShower`, `sleet`, `hailShower`,
        `hail`, `shower`, `lightSnow`, `snow`, `heavySnowShower`, `heavySnow`,
        `thunderShower`, `thunder`) or any other extended value.
    -   Optional
-   `visibility` : Visibility reported.
    -   Attribute type: Property. [Text](https://schema.org/Text)
    -   Allowed values: One of (`veryPoor`, `poor`, `moderate`, `good`,
        `veryGood`, `excellent`)
    -   Optional
-   `windDirection` : The wind direction expressed in decimal degrees compared
    to geographic North (measured clockwise), encoded as a Number.
    -   Attribute type: Property. [Number](https://schema.org/Number)
    -   Default unit: Decimal degrees. Range -180 to 180
    -   Attribute metadata (only for NGSIv2):
        -   `timestamp` : optional timestamp for the observed value. It can be
            omitted if the observation time is the same as the one captured by
            the `dateObserved` attribute at entity level.
            -   Type: [DateTime](https://schema.org/DateTime)
    -   Optional
-   `windSpeed` : The observed wind speed in m/s, encoded as a Number.
    -   Attribute type: Property. [Number](https://schema.org/Number)
    -   Default unit: meters per second
    -   Attribute metadata (only for NGSIv2):
        -   `timestamp` : optional timestamp for the observed value. It can be
            omitted if the observation time is the same as the one captured by
            the `dateObserved` attribute at entity level.
            -   Type: [DateTime](https://schema.org/DateTime)
    -   Optional
-   `refPointOfInterest` : A reference to a point of interest associated to this
    forecast.
    -   Attribute type: Relationship. Reference to an entity of type `PointOfInterest`
    -   Optional

### Location properties
-   `location` : Location of device represented by a GeoJSON geometry.
    -   Attribute type: `GeoProperty` or `geo:json` (only for NGSIv2).
    -   Normative References:
        [https://tools.ietf.org/html/rfc7946](https://tools.ietf.org/html/rfc7946)
    -   Mandatory if `address` is not defined.
-   `address` : Civic address of Device
    -   Attribute type: `Property`
    -   Normative References:
        [https://schema.org/address](https://schema.org/address)
    -   Mandatory if `location` is not present.
    -   It includes these properties
        - `streetAddress`  String containing the description of the address
        - `addressLocality` alternatively, locality, (when using JSON-LD) String containing the name of the locality
        - `addressRegion` alternatively, stateOrProvince, (when using JSON-LD) String containing the name of the Region
        - `addressCountry` alternatively, country, (when using JSON-LD)String containing the name of the Country
        - `postalCode` alternatively, postCode, (when using JSON-LD)String containing the postal code
        - `postOfficeBoxNumber` String containing the Box Office number
        - `AreaServed` String containing the name of the area served by the location
-   `city` String with the city the address is in. 
Equivalent to addressLocality
-   `country` String with the country that the address is in. 
Equivalent to addressCountry
-   `locality` An area of defined or undefined boundaries within a local authority or other 
legislatively defined area, usually rural or semi rural in nature or a suburb a bounded locality within a city, town or shire principally of urban character
-   `postcode` String descriptor for a postal delivery area, used to speed and simplify 
the delivery of mail (also know as zipcode). 
Equivalent to postalCode
-   `stateOrProvince` String with the State or Province that the address is in 
-   `streetName` String with the name of the street or other street type. 
-   `streetNr` String with the number identifying a specific property on a public street. It may be combined with streetNrLast for ranged addresses.
-   `streetNrLast` String with the last number in a range of street numbers allocated to a property
-   `streetNrLastSuffix` String with the last street number suffix for a ranged address
-   `streetNrSuffix` String with the first street number suffix 
-   `streetSuffix` String A modifier denoting a relative direction
-   `streetType` String between an enum between these types 
alley, avenue, boulevard, brae, crescent, drive, highway, lane, terrace, parade, place, tarn, way, wharf
-   `subAddress` String within a property in an urban area, may refer to a building, building cluster, or a floor of a multistory building
-   `Entity` Relation to an entity 
  
**Note**: JSON Schemas are intended to capture the data type and associated
constraints of the different Attributes, regardless their final representation
format in NGSI(v2, LD).