Entity: Airport
===============


Global description: **A description of a generic Airport**


## List of properties


- `id`:   
- `dateCreated`: Entity creation timestamp. This will usually be allocated by the storage platform.  
- `dateModified`: Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.  
- `source`: A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.  
- `name`: The name of this item.  
- `alternateName`: An alternative name for this item  
- `description`: A description of this item  
- `dataProvider`: A sequence of characters identifying the provider of the harmonised data entity.  
- `owner`: A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)  
- `seeAlso`:   
- `location`:   
- `address`: The mailing address.  
- `areaServed`: The geographic area where a service or offered item is provided.  
- `type`: NGSI Entity type  
- `codeIATA`:   
- `codeICAO`:   

Required properties
## Data Model description of properties

Sorted alphabetically (click for details)
<details><summary><strong>full yaml details</strong></summary>  

```yaml
address:
  description: The mailing address.
  properties:
    addressCountry: {type: string}
    addressLocality: {type: string}
    addressRegion: {type: string}
    areaServed: {type: string}
    postOfficeBoxNumber: {type: string}
    postalCode: {type: string}
    streetAddress: {type: string}
  type: object
  x-ngsi: {type: Property}
alternateName:
  description: An alternative name for this item
  type: string
  x-ngsi: {type: Property}
areaServed:
  description: The geographic area where a service or offered item is provided.
  type: string
  x-ngsi: {type: Property}
codeIATA: {type: string}
codeICAO: {type: string}
dataProvider:
  description: A sequence of characters identifying the provider of the harmonised
    data entity.
  type: string
  x-ngsi: {type: Property}
dateCreated:
  description: Entity creation timestamp. This will usually be allocated by the storage
    platform.
  format: date-time
  type: string
  x-ngsi: {type: Property}
dateModified:
  description: Timestamp of the last modification of the entity. This will usually
    be allocated by the storage platform.
  format: date-time
  type: string
  x-ngsi: {type: Property}
description:
  description: A description of this item
  type: string
  x-ngsi: {type: Property}
id:
  anyOf: &id001
  - {description: Property. Identifier format of any NGSI entity, maxLength: 256,
    minLength: 1, pattern: '^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$', type: string}
  - {description: Property. Identifier format of any NGSI entity, format: uri, type: string}
location:
  $id: https://geojson.org/schema/Geometry.json
  $schema: http://json-schema.org/draft-07/schema#
  oneOf:
  - properties:
      bbox:
        items: {type: number}
        minItems: 4
        type: array
      coordinates:
        items: {type: number}
        minItems: 2
        type: array
      type:
        enum: [Point]
        type: string
    required: [type, coordinates]
    title: GeoJSON Point
    type: object
  - properties:
      bbox:
        items: {type: number}
        minItems: 4
        type: array
      coordinates:
        items:
          items: {type: number}
          minItems: 2
          type: array
        minItems: 2
        type: array
      type:
        enum: [LineString]
        type: string
    required: [type, coordinates]
    title: GeoJSON LineString
    type: object
  - properties:
      bbox:
        items: {type: number}
        minItems: 4
        type: array
      coordinates:
        items:
          items:
            items: {type: number}
            minItems: 2
            type: array
          minItems: 4
          type: array
        type: array
      type:
        enum: [Polygon]
        type: string
    required: [type, coordinates]
    title: GeoJSON Polygon
    type: object
  - properties:
      bbox:
        items: {type: number}
        minItems: 4
        type: array
      coordinates:
        items:
          items: {type: number}
          minItems: 2
          type: array
        type: array
      type:
        enum: [MultiPoint]
        type: string
    required: [type, coordinates]
    title: GeoJSON MultiPoint
    type: object
  - properties:
      bbox:
        items: {type: number}
        minItems: 4
        type: array
      coordinates:
        items:
          items:
            items: {type: number}
            minItems: 2
            type: array
          minItems: 2
          type: array
        type: array
      type:
        enum: [MultiLineString]
        type: string
    required: [type, coordinates]
    title: GeoJSON MultiLineString
    type: object
  - properties:
      bbox:
        items: {type: number}
        minItems: 4
        type: array
      coordinates:
        items:
          items:
            items:
              items: {type: number}
              minItems: 2
              type: array
            minItems: 4
            type: array
          type: array
        type: array
      type:
        enum: [MultiPolygon]
        type: string
    required: [type, coordinates]
    title: GeoJSON MultiPolygon
    type: object
  title: GeoJSON Geometry
name:
  description: The name of this item.
  type: string
  x-ngsi: {type: Property}
owner:
  description: A List containing a JSON encoded sequence of characters referencing
    the unique Ids of the owner(s)
  items: !!python/object/new:builtins.dict
    dictitems:
      anyOf: *id001
  type: array
  x-ngsi: {type: Property}
seeAlso:
  oneOf:
  - items:
    - {format: uri, type: string}
    minItems: 1
    type: array
  - {format: uri, type: string}
source:
  description: A sequence of characters giving the original source of the entity data
    as a URL. Recommended to be the fully qualified domain name of the source provider,
    or the URL to the source object.
  type: string
  x-ngsi: {type: Property}
type:
  description: NGSI Entity type
  enum: [Airport]
  type: string
```
</details>  

## Example payloads  

#### Airport NGSI V2 key-values Example  

Here is an example of a Airport in JSON format as key-values. This is compatible with NGSI V2 when  using `options=keyValues` and returns the context data of an individual entity.

```json
{
    "id": "airport-BMA",
    "type": "Airport",
    "codeIATA": "BMA",
    "codeICAO": "ESSB",
    "name": "Bromma Stockholm Airport",
    "alternateName": "Stockholm Airport",
    "address": {
        "addressCountry": "SE",
        "addressLocality": "Stockholm"
    },
    "location": {
        "type": "Point",
        "coordinates": [59.354444, 17.939722, 14]
    }
}
```

#### Airport NGSI V2 normalized Example  

Here is an example of a Airport in JSON format as normalized. This is compatible with NGSI V2 when not using options and returns the context data of an individual entity.

```json
{
    "id": "airport-BMA",
    "type": "Airport",
    "codeIATA": {
        "value": "BMA"
    },
    "codeICAO": {
        "value": "ESSB"
    },
    "name": {
        "value": "Bromma Stockholm Airport"
    },
    "alternateName": {
        "value": "Stockholm Airport"
    },
    "address": {
        "type": "PostalAddress",
        "value": {
            "addressCountry": "SE",
            "addressLocality": "Stockholm"
        }
    },
    "location": {
        "type": "geo:json",
        "value": {
            "type": "Point",
            "coordinates": [59.354444, 17.939722, 14]
        }
    }
}
```

#### Airport NGSI-LD key-values Example  

Here is an example of a Airport in JSON-LD format as key-values. This is compatible with NGSI-LD when  using `options=keyValues` and returns the context data of an individual entity.

```json
{
    "id": "urn:ngsi-ld:Airline:airport-BMA",
    "type": "Airport",
    "codeIATA": "BMA",
    "codeICAO": "ESSB",
    "name": "Bromma Stockholm Airport",
    "alternateName": "Stockholm Airport",
    "address": {
        "addressCountry": "SE",
        "addressLocality": "Stockholm" 
    },
    "location": {
        "type": "Point",
        "coordinates": [59.354444, 17.939722, 14]
    },
    "@context": [
        "https://schema.lab.fiware.org/ld/context",
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"
    ]
}
```

#### Airport NGSI-LD normalized Example  

Here is an example of a Airport in JSON-LD format as normalized. This is compatible with NGSI-LD when not using options and returns the context data of an individual entity.

```json
{
    "id": "urn:ngsi-ld:Airline:airport-BMA",
    "type": "Airport",
    "codeIATA": {
        "type": "Property",
        "value": "BMA"
    },
    "codeICAO": {
        "type": "Property",
        "value": "ESSB"
    },
    "name": {
        "type": "Property",
        "value": "Bromma Stockholm Airport"
    },
    "alternateName": {
        "type": "Property",
        "value": "Stockholm Airport"
    },
    "address": {
        "type": "Property",
        "value": {
            "addressCountry": "SE",
            "addressLocality": "Stockholm"
        }
    },
    "location": {
        "type": "GeoProperty",
        "value": {
            "type": "Point",
            "coordinates": [59.354444, 17.939722, 14]
        }
    },
    "@context": [
        "https://schema.lab.fiware.org/ld/context",
        "https://uri.etsi.org/ngsi-ld/v1/ngsi-ld-core-context.jsonld"
    ]
}
```
