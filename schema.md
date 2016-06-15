# health-graph
### Drug-Manufacture-Lobby-Prescription Graph ###
(This file is in development)

#### Nodes ####

##### (drug) #####

* ndc: National Drug Code = labeler code-product code-package code
* brand_name
* generic_name
* start_marketing_date:
* ['marketing_category'](http://www.fda.gov/ForIndustry/DataStandards/StructuredProductLabeling/ucm162528.htm)
* dea_schedule :  drug’s acceptable medical use and the drug’s abuse or dependency potential
* pharm_classes

##### (manufacture) #####

* labeler_code
* firm_name
* address
* operations

##### (provider) #####

* npi: National Provider Identifier
* first_name
* last_name
* credential
* specialty
* gender
* npi_deactivation_date
* npi_reactivation_date

##### (prescription) #####

* bene_count: the total number of unique PartD beneficiaries ( <11 is not counted)
* total_claim_count: Original prescription + refills (<11 is not counted)
* cost: total drug cost
* year: so far this is 2013

##### (hospital) #####

* name
* address
* zipcode
* city
* state
* Country
(lobbyist)


#### Relationships ####

* (provider)-[:writes]->(prescription)  (the prescription contains aggregated properties)
* (provider)-[:works_at]->(hospital)
* (prescription)-[:refers_to]->(drug)
* (manufacture)-[:produces]->(drug)








