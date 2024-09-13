---
title: How to Contribute Data to Nomisma.org
layout: default
permalink: /documentation/contribute/
id: doc-contribute
---

# How to Contribute Data

In the spring of 2013, we took a new approach in establishing links from RIC types in [OCRE](http://numismatics.org/ocre/) to physical coins and hoards which reference those types. The model has evolved over time to be compliant to the new Nomisma ontology. The following models are required before contributing data into the Nomisma triplestore for use in OCRE and similiar coin type projects based on the Numishare platform that relies on Nomisma.org APIS.

The first basic prerequisite for participation is that each object you wish to contribute be accessible to the web with a distinct URI. This is the core standard for Linked Open Data. After this, there are essentially two required elements for contributing data to a Nomisma-affiliated project, influenced by the requirements for joining the [Pelagios Network](https://pelagios.org/): an RDF data dump (which also much be accessible by URL) and some metadata about this dump, in [Vocabulary of Interlinked Datasets (VoID)](http://www.w3.org/TR/void/) RDF.

## VoID RDF
This snippet of RDF is intended to describe the contents of a dataset with general metadata described with Dublin Core Terms: title, description, rights, license, and a URI that allows the Nomisma.org back-end fetch the RDF dump from a web server.

<pre><code class="language-markup">&lt;rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" 
	xmlns:dcterms="http://purl.org/dc/terms/"
	xmlns:void="http://rdfs.org/ns/void#"&gt;
	&lt;void:Dataset rdf:about="http://coins.lib.virginia.edu/"&gt;
		&lt;dcterms:title&gt;The Fralin | UVa Art Museum Numismatic Collection&lt;/dcterms:title&gt;
		&lt;dcterms:description&gt;The Fralin Museum of Art at the University of Virginia numismatic 
			collection contains about 600 coins of mainly Greco-Roman origin.&lt;/dcterms:description&gt;
		&lt;dcterms:publisher&gt;University of Virginia Library&lt;/dcterms:publisher&gt;
		&lt;dcterms:license rdf:resource="http://opendatacommons.org/licenses/odbl/"/&gt;
		&lt;void:uriSpace&gt;http://coins.lib.virginia.edu/id/&lt;/void:uriSpace&gt;
		&lt;void:dataDump rdf:resource="http://coins.lib.virginia.edu/nomisma.rdf"/&gt;
	&lt;/void:Dataset&gt;
&lt;/rdf:RDF&gt;
</code></pre>

The void:Dataset should include the URI for your project, and this URI should be linked from each individual object (physical coin, coin type, or hoard) within the data dump using the void:inDataset property (see examples, below). The dcterms:title, dcterms:description, dcterms:publisher, and dcterms:license are all required. The title and description must be textual strings, but the publisher and license may be URIs. In fact, the license <i>should</i> be a URI designating the dataset under an open license, such as those published by [Creative Commons](https://creativecommons.org/) or [Open Data Commons](http://opendatacommons.org/). A literal rights statement (dcterms:rights) may be made instead of a dcterms:license link.

## Nomisma-compliant RDF export Models
The data dump model should conform to the standards established by Nomisma.org, including the use of the Nomisma ontology where applicable. Nomisma can harvest and make accessible for query different types of numismatic data: collections of physical objects, coin types, hoards, dies, monograms, etc. Each of these types of materials are represented by minor variations of the Nomisma ontology.

### Physical Coins
<pre><code class="language-markup">&lt;rdf:RDF xmlns:dcterms="http://purl.org/dc/terms/"
	xmlns:void="http://rdfs.org/ns/void#"
	xmlns:nmo="http://nomisma.org/ontology#"
	xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
	xmlns:foaf="http://xmlns.com/foaf/0.1/"
	xmlns:xsd="http://www.w3.org/2001/XMLSchema#"&gt;
	&lt;nmo:NumismaticObject rdf:about="http://coins.lib.virginia.edu/id/1991.17.140"&gt;
		&lt;dcterms:title&gt;Antoninianus of Gallienus, Rome, 254-255. 1991.17.140.&lt;/dcterms:title&gt;
		&lt;dcterms:identifier&gt;1991.17.140&lt;/dcterms:identifier&gt;
		&lt;nmo:hasCollection rdf:resource="http://nomisma.org/id/uva"/&gt;
		&lt;nmo:hasTypeSeriesItem rdf:resource="http://numismatics.org/ocre/id/ric.5.gall(1).143fA"/&gt;
		&lt;dcterms:replaces rdf:resource="http://coins.lib.virginia.edu/display-uva?id=n1991_17_140"/&gt;
		&lt;nmo:hasAxis rdf:datatype="http://www.w3.org/2001/XMLSchema#integer"&gt;6&lt;/nmo:hasAxis&gt;
		&lt;nmo:hasDiameter rdf:datatype="http://www.w3.org/2001/XMLSchema#decimal"&gt;22&lt;/nmo:hasDiameter&gt;
		&lt;nmo:hasWeight rdf:datatype="http://www.w3.org/2001/XMLSchema#decimal"&gt;2.86&lt;/nmo:hasWeight&gt;
		&lt;dcterms:isPartOf rdf:resource="http://nomisma.org/id/olivers_orchard_hoards"/&gt;
		&lt;nmo:hasObverse rdf:resource="http://coins.lib.virginia.edu/id/1991.17.140#obverse"/&gt;
		&lt;nmo:hasReverse rdf:resource="http://coins.lib.virginia.edu/id/1991.17.140#reverse"/&gt;
		&lt;void:inDataset rdf:resource="http://coins.lib.virginia.edu/"/&gt;
	&lt;/nmo:NumismaticObject&gt;
	&lt;rdf:Description rdf:about="http://coins.lib.virginia.edu/id/1991.17.140#obverse"&gt;
		&lt;foaf:depiction rdf:resource="http://coins.lib.virginia.edu/images/coins/screen/n1991_17_140_obv.jpg"/&gt;
		&lt;foaf:thumbnail rdf:resource="http://coins.lib.virginia.edu/images/coins/thumb/n1991_17_140_obv.jpg"/&gt;
	&lt;/rdf:Description&gt;
	&lt;rdf:Description rdf:about="http://coins.lib.virginia.edu/id/1991.17.140#reverse"&gt;
		&lt;foaf:depiction rdf:resource="http://coins.lib.virginia.edu/images/coins/screen/n1991_17_140_rev.jpg"/&gt;
		&lt;foaf:thumbnail rdf:resource="http://coins.lib.virginia.edu/images/coins/thumb/n1991_17_140_rev.jpg"/&gt;
	&lt;/rdf:Description&gt;
&lt;/rdf:RDF&gt;
</code></pre>

The title, publisher, and identifier are required, as is nmo:hasTypeSeriesItem. nmo:hasCollection is recommended for physical specimens. Before submitting your data to nomisma, please contact the administrators to create a URI for your collection. A physical specimen must be carry the nmo:NumismaticObject class. Finally, each object must contain a void:inDataset property linking to the URI of the void:Dataset in the VoID metadata RDF.

There are several fields which are particular to physical objects (and not hoards): nmo:hasAxis, nmo:hasDiameter, nmo:hasWeight, and obverse/reverse thumbnail and references images (to be added as necessary). Thumbnails and reference images that represent sides of coins should be contained in the data objects linked with the nmo:hasObverse and nmo:hasReverse properties. If they are not contained in the nmo:hasObverse or nmo:hasReverse, it is assumed that the images include both the obverse and reverse sides of the coin. None of these fields is required, though the measurements can be used for quantitative analyses. The measurements should be associated with xsd:decimal for weights and diameters, xsd:integer for axis (unless the source data uses fractional numbers for axes). The dcterms:isPartOf property is used to link a coin to a coin hoard that has a published URI.

#### IIIF Integration
The Nomisma RDF model has been extended to follow the Europeana Data Model [specifications](http://pro.europeana.eu/files/Europeana_Professional/Share_your_data/Technical_requirements/EDM_profiles/IIIFtoEDM_profile_042016.pdf) for defining IIIF images and services. Essentially, this requires additional triples about the reference image (foaf:depiction), which should be defined as an edm:WebResource. This edm:WebResource should link to a JSON-LD IIIF manifest or information object (dcterms:isReferencedBy) and the URI for the service (with the svcs:has_service property). The service should include several triples that defines it as a IIIF image service.

**Note:** The JSON-LD IIIF link in the edm:WebResource should be either:

 - If the image represents either the obverse or reverse, the link should point to the info.json for the image
 - If the image depicts both the obverse and reverse simultaneously (as is the standard for British Museum and Harvard Art Museums photographs), the link should be the full IIIF manifest.

<pre><code class="language-markup">
&lt;edm:WebResource rdf:about="https://rucore.libraries.rutgers.edu/api/iiif/image/2.0/rutgers-lib:45878;PTIF-1/full/600,/0/default.jpg"&gt;
    &lt;svcs:has_service rdf:resource="https://rucore.libraries.rutgers.edu/api/iiif/image/2.0/rutgers-lib:45878;PTIF-1"/&gt;
    &lt;dcterms:isReferencedBy rdf:resource="https://rucore.libraries.rutgers.edu/api/iiif/image/2.0/rutgers-lib:45878;PTIF-1/info.json"/&gt;
&lt;/edm:WebResource&gt;
&lt;svcs:Service rdf:about="https://rucore.libraries.rutgers.edu/api/iiif/image/2.0/rutgers-lib:45878;PTIF-1"&gt;
    &lt;dcterms:conformsTo rdf:resource="http://iiif.io/api/image"/&gt;
    &lt;doap:implements rdf:resource="http://iiif.io/api/image/2/level1.json"/&gt;
&lt;/svcs:Service&gt;
</code></pre>

Be sure to include the following XML namespaces/prefixes in your RDF:

 - `PREFIX edm: <http://www.europeana.eu/schemas/edm/>`
 - `PREFIX svcs: <http://rdfs.org/sioc/services#>`
 - `PREFIX doap: <http://usefulinc.com/ns/doap#>`
 
#### Findspot
The findspot model is based upon the ARIADNE archaeological specification, using a combination of existing Nomisma RDF properties and classes in combination with CIDOC-CRM properties. A coin is found by an event which may have occurred on a known date or date range and a place. In an archaeological excavation or a find reported to an portable antiquities service, the very specific coordinates by be presented. Regardless of whether the specific coordinates are known or able to be made public, the findspot occurs within the place defined by a Gazetteer URI. Allowable gazetteers are Wikidata, Geonames, the Getty Thesaurus of Geographic Names, Ordnance Survey, and the Pleiades Gazetteer of Ancient Names. Upon ingestion into Nomisma.org, these URIs will automatically be reconciled to Wikidata Entity URIs, when applicable, and the geographic coordinates, hierarchy, and skos:closeMatch URIs will also be extracted via SPARQL from Wikidata.

When the findspot conforms to one of the aforementioned URI schemes, the crm:E53_Place and its spatial extent do not have to be explicitly included in the RDF export, since these will be programmatically extracted from Wikidata.org to improve consistency across harvested datasets. The crm:E53_Place that defines the gazetteer URI includes two properties (in the WGS84 geo ontology and CIDOC-CRM) pointing to the same node for the spatial expression, which bears two RDF classes. This model is dually compatible with CIDOC-CRM and the more common WGS84 geo ontology.

This data model, which began implementation in Nomisma-associated projects in April 2020, is explained more thoroughly in a Numishare [blog post](https://numishare.blogspot.com/2020/04/updates-to-coin-hoards-of-roman-republic.html).

<pre><code class="language-markup">&lt;nmo:NumismaticObject rdf:about="https://finds.org.uk/database/artefacts/record/id/1018642"&gt;
        &lt;nmo:hasFindspot&gt;
            &lt;nmo:Find&gt;
                &lt;crm:P7_took_place_at&gt;
                    &lt;crm:E53_Place&gt;
                        &lt;rdfs:label xml:lang="en"&gt;Hollingbourne&lt;/rdfs:label&gt;
                        &lt;crm:P89_falls_within rdf:resource="http://www.wikidata.org/entity/Q9199209"/&gt;
                    &lt;/crm:E53_Place&gt;
                &lt;/crm:P7_took_place_at&gt;
            &lt;/nmo:Find&gt;
        &lt;/nmo:hasFindspot&gt;
    &lt;/nmo:NumismaticObject&gt;
    &lt;crm:E53_Place rdf:about="http://www.wikidata.org/entity/Q9199209"&gt;
        &lt;rdfs:label&gt;Hollingbourne&lt;/rdfs:label&gt;
        &lt;crm:P89_falls_within rdf:resource="http://www.wikidata.org/entity/Q737114"/&gt;
        &lt;skos:closeMatch rdf:resource="http://sws.geonames.org/2646748"/&gt;
        &lt;skos:closeMatch rdf:resource="http://data.ordnancesurvey.co.uk/id/4000000074547229"/&gt;
        &lt;skos:closeMatch rdf:resource="http://sws.geonames.org/7295882"/&gt;
        &lt;skos:closeMatch rdf:resource="http://data.ordnancesurvey.co.uk/id/7000000000018330"/&gt;
        &lt;geo:location rdf:resource="http://www.wikidata.org/entity/Q9199209#this"/&gt;
        &lt;crm:P168_place_is_defined_by rdf:resource="http://www.wikidata.org/entity/Q9199209#this"/&gt;
    &lt;/crm:E53_Place&gt;
    &lt;geo:SpatialThing rdf:about="http://www.wikidata.org/entity/Q9199209#this"&gt;
        &lt;rdf:type rdf:resource="http://www.ics.forth.gr/isl/CRMgeo/SP5_Geometric_Place_Expression"/&gt;
        &lt;crmgeo:Q9_is_expressed_in_terms_of rdf:resource="http://www.wikidata.org/entity/Q215848"/&gt;
        &lt;geo:lat rdf:datatype="http://www.w3.org/2001/XMLSchema#decimal"&gt;51.2675&lt;/geo:lat&gt;
        &lt;geo:long rdf:datatype="http://www.w3.org/2001/XMLSchema#decimal"&gt;0.641111111&lt;/geo:long&gt;
        &lt;crmgeo:asWKT rdf:datatype="http://www.opengis.net/ont/geosparql#wktLiteral"&gt;Point(0.641111111 51.2675)&lt;/crmgeo:asWKT&gt;
    &lt;/geo:SpatialThing&gt;
&lt;/nmo:NumismaticObject&gt;
</code></pre>

The above model can be described as follows:

A coin was found (nmo:hasFindspot, repurposing an existing property to stand in for crmsci:O19i_was_object_found_by from ARIADNE), which is represented by the event of an nmo:Find (equivalent to crmsci:S19_Encounter_Event). *From this point, the model conforms to CIDOC-CRM.* The Find took place at (crm:P7_took_place_at) a place (crm:E53_Place). This place is often amorphous. We don't necessarily know the precise place on earth where the coin was found. In the event that we do, we can insert the crm:P168_place_is_defined_by and geo:location properties here to point to precise coordinates. The rdfs:label can be any human-readable label, such as "Farmer Jones' field." Usually the rdfs:label is the gazetteer preferred label. This blank node of an E53_Place exists within the broader geographic concept defined by the gazetteer URI (crm:P89_falls_within). This gazetteer URI can be the lowest-geographic level known, from a Pleiades URI for a temple to the country.


 - The nmo:Find can accommodate any other CIDOC-CRM properties available to a CRM Event class, such as dates.
 - In the event that two coins were found during the same finding event, it may be necessary to give the nmo:Find a reusable URI, instead of using a blank node that will not be able to connect multiple coins found at the same time.


### Hoards

<pre><code class="language-markup">&lt;rdf:RDF xmlns:nmo="http://nomisma.org/ontology#" 
         xmlns:dcterms="http://purl.org/dc/terms/"
         xmlns:void="http://rdfs.org/ns/void#"
         xmlns:geo="http://www.w3.org/2003/01/geo/wgs84_pos#"
         xmlns:skos="http://www.w3.org/2004/02/skos/core#"
         xmlns:dcmitype="http://purl.org/dc/dcmitype/"
         xmlns:relations="http://pelagios.github.io/vocab/relations#"
         xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
         xmlns:foaf="http://xmlns.com/foaf/0.1/"
         xmlns:xsd="http://www.w3.org/2001/XMLSchema#"&gt;
    &lt;nmo:Hoard rdf:about="http://numismatics.org/chrr/id/SCU"&gt;
        &lt;dcterms:title xml:lang="en"&gt;Scurta (Romania; SCU)&lt;/dcterms:title&gt;
        &lt;nmo:hasFindspot&gt;
        	&lt;nmo:Find&gt;
        		&lt;crm:P7_took_place_at&gt;
        			&lt;crm:E53_Place&gt;
        				&lt;rdfs:label xml:lang="en"&gt;Scurta, Romania&lt;/rdfs:label&gt;
        				&lt;crm:P89_falls_within rdf:resource="https://sws.geonames.org/663431/" /&gt;
        			&lt;/crm:E53_Place&gt;
        		&lt;/crm:P7_took_place_at&gt;
        	&lt;/nmo:Find&gt;
        &lt;/nmo:hasFindspot&gt;
        &lt;nmo:hasClosingDate rdf:datatype="http://www.w3.org/2001/XMLSchema#gYear"&gt;0014&lt;/nmo:hasClosingDate&gt;
        &lt;dcterms:tableOfContents rdf:resource="http://numismatics.org/chrr/id/SCU#contents"/&gt;
        &lt;void:inDataset rdf:resource="http://numismatics.org/chrr/"/&gt;
    &lt;/nmo:Hoard&gt;
    &lt;dcmitype:Collection rdf:about="http://numismatics.org/chrr/id/SCU#contents"&gt;
        &lt;nmo:hasTypeSeriesItem rdf:resource="http://numismatics.org/crro/id/rrc-252.1"/&gt;
        &lt;nmo:hasTypeSeriesItem rdf:resource="http://numismatics.org/crro/id/rrc-276.1"/&gt;
        &lt;nmo:hasTypeSeriesItem rdf:resource="http://numismatics.org/crro/id/rrc-278.1"/&gt;
        &lt;nmo:hasTypeSeriesItem rdf:resource="http://numismatics.org/crro/id/rrc-286.1"/&gt;
        &lt;nmo:hasTypeSeriesItem rdf:resource="http://numismatics.org/crro/id/rrc-350A.2"/&gt;
        &lt;nmo:hasTypeSeriesItem rdf:resource="http://numismatics.org/crro/id/rrc-362.1"/&gt;
        &lt;nmo:hasTypeSeriesItem rdf:resource="http://numismatics.org/crro/id/rrc-393.1a"/&gt;
        &lt;nmo:hasTypeSeriesItem rdf:resource="http://numismatics.org/crro/id/rrc-463.3"/&gt;
        &lt;nmo:hasTypeSeriesItem rdf:resource="http://numismatics.org/ocre/id/ric.1(2).aug.541"/&gt;
        &lt;nmo:hasTypeSeriesItem rdf:resource="http://numismatics.org/ocre/id/ric.1(2).aug.340"/&gt;
    &lt;/dcmitype:Collection&gt;
    &lt;crm:E53_Place rdf:about="https://sws.geonames.org/663431/"&gt;
        &lt;rdfs:label&gt;Valea Scurtă (Romania)&lt;/rdfs:label&gt;
        &lt;crm:P2_has_type rdf:resource="http://vocab.getty.edu/aat/300008347"/&gt;
        &lt;geo:location rdf:resource="https://sws.geonames.org/663431/#this"/&gt;
        &lt;crm:P168_place_is_defined_by rdf:resource="https://sws.geonames.org/663431/#this"/&gt;
    &lt;/crm:E53_Place&gt;
    &lt;geo:SpatialThing rdf:about="https://sws.geonames.org/663431/#this"&gt;
        &lt;rdf:type rdf:resource="http://www.ics.forth.gr/isl/CRMgeo/SP5_Geometric_Place_Expression"/&gt;
        &lt;crmgeo:Q9_is_expressed_in_terms_of rdf:resource="http://www.wikidata.org/entity/Q215848"/&gt;
        &lt;geo:lat rdf:datatype="http://www.w3.org/2001/XMLSchema#decimal"&gt;46.10391&lt;/geo:lat&gt;
        &lt;geo:long rdf:datatype="http://www.w3.org/2001/XMLSchema#decimal"&gt;26.19728&lt;/geo:long&gt;
        &lt;crmgeo:asWKT rdf:datatype="http://www.opengis.net/ont/geosparql#wktLiteral"&gt;POINT (26.19728 46.10391)&lt;/crmgeo:asWKT&gt;
    &lt;/geo:SpatialThing&gt;
&lt;/rdf:RDF&gt;
</code></pre>

Like physical coins, the dcterms:title, and dcterms:identifier are required, and the resource must carry the nmo:Hoard class. Similarly, the void:inDataset property is required in the nmo:Hoard object to link to the void:Dataset URI.

Presently, the hoard model is very simple and does not contain all the information stored in the database or NUDS XML record. The nmo:Hoard object should link to a dcmitype:Collection, which merely contains a list of associated TypeSeriesItems (linked with the nmo:hasTypeSeriesItem property). These records are meant to facilitate basic mapping and timelines in OCRE and CRRO. We anticipate enhancing the hoard model over the coming year.

The nmo:hasClosingDate is optional, but if it is a year, it should conform to the rdf:datatype, xsd:gYear (four digit number, padded with zeroes. Negative numbers represent B.C. dates).

The nmo:hasFindspot should be expressed like the example of an individual find, above. Upon ingestion into Nomisma, URIs from various geographic gazetteers (such as Geonames and Ordnance Survey) will be reconciled to Wikidata. As a result, the E53:Place and geo:SpatialThing objects in the above example do not need to be included in the RDF/XML export; they will be removed upon ingestion and replaced with geographic metadata extracted from Wikidata.
