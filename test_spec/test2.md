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
{'id': {'anyOf': [{'type': 'string', 'minLength': 1, 'maxLength': 256, 'pattern': '^[\\w\\-\\.\\{\\}\\$\\+\\*\\[\\]`|~^@!,:\\\\]+$', 'description': 'Property. Identifier format of any NGSI entity'}, {'type': 'string', 'format': 'uri', 'description': 'Property. Identifier format of any NGSI entity'}]}, 'dateCreated': {'type': 'string', 'format': 'date-time', 'x-ngsi': {'type': 'Property'}, 'description': 'Entity creation timestamp. This will usually be allocated by the storage platform.'}, 'dateModified': {'type': 'string', 'format': 'date-time', 'x-ngsi': {'type': 'Property'}, 'description': 'Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.'}, 'source': {'type': 'string', 'x-ngsi': {'type': 'Property'}, 'description': 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'}, 'name': {'type': 'string', 'x-ngsi': {'type': 'Property'}, 'description': 'The name of this item.'}, 'alternateName': {'type': 'string', 'x-ngsi': {'type': 'Property'}, 'description': 'An alternative name for this item'}, 'description': {'type': 'string', 'x-ngsi': {'type': 'Property'}, 'description': 'A description of this item'}, 'dataProvider': {'type': 'string', 'x-ngsi': {'type': 'Property'}, 'description': 'A sequence of characters identifying the provider of the harmonised data entity.'}, 'owner': {'type': 'array', 'x-ngsi': {'type': 'Property'}, 'description': 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)', 'items': {'anyOf': [{'type': 'string', 'minLength': 1, 'maxLength': 256, 'pattern': '^[\\w\\-\\.\\{\\}\\$\\+\\*\\[\\]`|~^@!,:\\\\]+$', 'description': 'Property. Identifier format of any NGSI entity'}, {'type': 'string', 'format': 'uri', 'description': 'Property. Identifier format of any NGSI entity'}]}}, 'seeAlso': {'oneOf': [{'type': 'array', 'minItems': 1, 'items': [{'type': 'string', 'format': 'uri'}]}, {'type': 'string', 'format': 'uri'}]}, 'location': {'$schema': 'http://json-schema.org/draft-07/schema#', '$id': 'https://geojson.org/schema/Geometry.json', 'title': 'GeoJSON Geometry', 'oneOf': [{'title': 'GeoJSON Point', 'type': 'object', 'required': ['type', 'coordinates'], 'properties': {'type': {'type': 'string', 'enum': ['Point']}, 'coordinates': {'type': 'array', 'minItems': 2, 'items': {'type': 'number'}}, 'bbox': {'type': 'array', 'minItems': 4, 'items': {'type': 'number'}}}}, {'title': 'GeoJSON LineString', 'type': 'object', 'required': ['type', 'coordinates'], 'properties': {'type': {'type': 'string', 'enum': ['LineString']}, 'coordinates': {'type': 'array', 'minItems': 2, 'items': {'type': 'array', 'minItems': 2, 'items': {'type': 'number'}}}, 'bbox': {'type': 'array', 'minItems': 4, 'items': {'type': 'number'}}}}, {'title': 'GeoJSON Polygon', 'type': 'object', 'required': ['type', 'coordinates'], 'properties': {'type': {'type': 'string', 'enum': ['Polygon']}, 'coordinates': {'type': 'array', 'items': {'type': 'array', 'minItems': 4, 'items': {'type': 'array', 'minItems': 2, 'items': {'type': 'number'}}}}, 'bbox': {'type': 'array', 'minItems': 4, 'items': {'type': 'number'}}}}, {'title': 'GeoJSON MultiPoint', 'type': 'object', 'required': ['type', 'coordinates'], 'properties': {'type': {'type': 'string', 'enum': ['MultiPoint']}, 'coordinates': {'type': 'array', 'items': {'type': 'array', 'minItems': 2, 'items': {'type': 'number'}}}, 'bbox': {'type': 'array', 'minItems': 4, 'items': {'type': 'number'}}}}, {'title': 'GeoJSON MultiLineString', 'type': 'object', 'required': ['type', 'coordinates'], 'properties': {'type': {'type': 'string', 'enum': ['MultiLineString']}, 'coordinates': {'type': 'array', 'items': {'type': 'array', 'minItems': 2, 'items': {'type': 'array', 'minItems': 2, 'items': {'type': 'number'}}}}, 'bbox': {'type': 'array', 'minItems': 4, 'items': {'type': 'number'}}}}, {'title': 'GeoJSON MultiPolygon', 'type': 'object', 'required': ['type', 'coordinates'], 'properties': {'type': {'type': 'string', 'enum': ['MultiPolygon']}, 'coordinates': {'type': 'array', 'items': {'type': 'array', 'items': {'type': 'array', 'minItems': 4, 'items': {'type': 'array', 'minItems': 2, 'items': {'type': 'number'}}}}}, 'bbox': {'type': 'array', 'minItems': 4, 'items': {'type': 'number'}}}}]}, 'address': {'type': 'object', 'x-ngsi': {'type': 'Property'}, 'description': 'The mailing address.', 'properties': {'streetAddress': {'type': 'string'}, 'addressLocality': {'type': 'string'}, 'addressRegion': {'type': 'string'}, 'addressCountry': {'type': 'string'}, 'postalCode': {'type': 'string'}, 'postOfficeBoxNumber': {'type': 'string'}, 'areaServed': {'type': 'string'}}}, 'areaServed': {'type': 'string', 'x-ngsi': {'type': 'Property'}, 'description': 'The geographic area where a service or offered item is provided.'}, 'type': {'type': 'string', 'enum': ['Airport'], 'description': 'NGSI Entity type'}, 'codeIATA': {'type': 'string'}, 'codeICAO': {'type': 'string'}}
```
</details>  

## Example payloads  
