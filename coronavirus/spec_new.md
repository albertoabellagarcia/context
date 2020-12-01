properties:
 id/@id: `depending if you are using NGSIv2 or NGSI-LD`
  x-attr-type: "Property" 
    type: "string"  `Mandatory`
    format: "URI" `optional. Optional to be included for every property`
    description: Entity Identifier
  type/@type: `depending if you are using NGSIv2 or NGSI-LD`
    x-attr-type: "Property" 
    type: "string"  `Mandatory`
    description: Type of Entity
  propertyName1: `reference to other external models. i.e. location`
    $ref = `link to other spec`
  propertyName2: `Example of relatiohsip`
    x-attr-type: "Relationship" 
    type: "string"
    format: "URI" `This case, relationship is mandatory. Preferably full URI and not relative`
    description: `Mandatory. Description of the property`
