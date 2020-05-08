# Data Model Corona Virus Patient

## Description

This data model is a simplified version to treat massively data from corona virus infected persons
and quite useful if adopted. Definitely

## Data Model

A JSON Schema corresponding to this data model can be found at
{{add link to JSON Schema}}

-   `id` : Unique identifier. It shall be a URN in the form
    `urn:ngsi-ld:{{EntityType}}:<identifier>` where `<identifier>` shall be a
    unique ID string.

-   `type` : Entity type. It must be equal to {{coronaPatient}}.

-   `personId` : An anonymous identification for updating data on a patient.

-   `age` : Years of age of the patient

-   `sex` : either `male` or `female`

-   `dateInfection` : Date patient is proved to be infected.

-   `methodDetermineInfection` : Type of test done to patient to confirm the infection. 

{{Location and address are two typical attributes that are added here for convenience}}

-   `locationInfection` : Location of Corona Virus Patient represented by a GeoJSON geometry.

    -   Attribute type: `GeoProperty` or `geo:json` (NGSIv2).
    -   Normative References:
        [https://tools.ietf.org/html/rfc7946](https://tools.ietf.org/html/rfc7946)
    -   Mandatory if `address` is not defined.

-   `address` : Civic address of {{Entity Type}}

    -   Attribute type: `Property`
    -   Normative References:
        [https://schema.org/address](https://schema.org/address)
    -   Mandatory if `location` is not present.

-   `patientResolution` : resolution of the patient either `healing` or `death`.

-   `locationResolution` : Location of Corona Virus Patient resolution represented by a GeoJSON geometry.
 (See `locationInfection` for structure) 
 
-   `treatments` : Array of treatments applied to the patient. Composed of 3 properties:
      - `dateTreatment` : Date started with the treatment
      - `descriptionTreatment` : String describing the treatment
      - `dateEndTreatment` : Date finished with the treatment

-   `coMorbidities` : Array of strings identifying the effect of all other conditions