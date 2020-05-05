# Smart Data Models: Device specification

## Description

Description of the properties attached to a device (in case all of them were used)

## Data Model specification

A JSON Schema corresponding to this data model can be found at
[schema.jsonld](../schema.jsonld)
### Basic properties
-   `id` or `@id` : Unique identifier. It shall be a URN for NGSI-LD (jsonld) example in the form
    `urn:ngsi-ld:{{EntityType}}:<identifier>` where `<identifier>` shall be a
    unique ID string.
-   `type` or `@type`: Entity type. It must be equal to `device`.
-   `modifiedAt` or `dateModified` : Last update timestamp of this
    entity.
    -   Attribute type: Property. [DateTime](https://schema.org/DateTime)
    -   Read-Only. Automatically generated.
-   `createdAt` or `dateCreated` : Entity's creation timestamp.
    -   Attribute type: Property. [DateTime](https://schema.org/DateTime)
    -   Read-Only. Automatically generated.

### Specific properties of the data model     
-    `controlledAsset`: string with the identifier of element controlled 
-    `mnc`: String describing the mnc feature of the device 
-    `ipAddress`: Array of strings with the ip addresses managed by the device
-    `dateInstalled`: Date of the first installation of the device
-    `dateFirstUsed`: Date of the first production use of the device 
-    `dateManufactured`: Date identifying Final date of the device in the factory where it was built 
-    `hardwareVersion`: String identifying the Version of the hardware
-    `softareVersion`: String identifying the Version of the software
-    `firmwareVersion`: String identifying the Version of the firmware
-    `osVersion`: String identifying the operative system version of the device
-    `dateLastCalibration`: Date for the last date the device was calibrated
-    `serialNumber`: String identifying the reference of the manufacturer for the device
-    `provider` : String identifying Provider of the installed device
-    `refDeviceModel`: String of Reference to the static parameters of the device attached to the model
-    `batteryLevel` figure of the battery between 0 and 1. -1 for switch off devices.
-    `rssi`: String describing the mnc feature of the device
-    `deviceState` String describing the state of the device 
-    `dateLastValueReported` Date containing last data the device has been reporting values 
-    `value` Values for the controlled properties in a single string

### Location Commons properties 
-   `location` : Location of device represented by a GeoJSON geometry.
    -   Attribute type: `GeoProperty` or `geo:json` (NGSIv2).
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
        - `addressLocality` String containing the name of the locality
        - `addressRegion` String containing the name of the Region
        - `addressCountry` String containing the name of the Country
        - `postalCode` String containing the postal code
        - `postOfficeBoxNumber` String containing the Box Office number
        - `AreaServed` String containing the name of the area served by the location

### Device commons properties 
-   `category` Device type to be selected between the enum options. This case `sensor`
-   `controlledProperty` Array of strings identifying properties to be controlled to be selected between the enum options
-   `supportedProtocol` Array of strings identifying protocols enabled in the device 
-   `macAddress` Array of strings identifying the mac addresses managed by the device 
  
### TMForum address properties 
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


