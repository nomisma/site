---
title: All findspots for RIC Augustus 1A
layout: default
stub: augustus-1a-findspots
order: 6
permalink: /documentation/sparql/augustus-1a-findspots/
---

### {{page.title}} {#{{page.stub}}}

This will query all coins with individual finds and all coins linked to hoards or hoards with contents containing Augustus 1A. This query makes use of the current Nomisma findspot data model (implemented April 2020). See [documentation]({{site.baseurl}}/documentation/contribute#findspot) for further details

<pre><code class="language-sparql">
PREFIX rdf:      <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dcmitype:	<http://purl.org/dc/dcmitype/>
PREFIX dcterms:  <http://purl.org/dc/terms/>
PREFIX nm:       <http://nomisma.org/id/>
PREFIX nmo:	<http://nomisma.org/ontology#>
PREFIX geo: <http://www.w3.org/2003/01/geo/wgs84_pos#>
PREFIX foaf:	<http://xmlns.com/foaf/0.1/>
PREFIX skos:      <http://www.w3.org/2004/02/skos/core#>
PREFIX rdfs:	<http://www.w3.org/2000/01/rdf-schema#>
PREFIX crm:	<http://www.cidoc-crm.org/cidoc-crm/>

SELECT ?object ?title ?findspot ?placeName ?hoard ?hoardLabel ?lat ?long ?type ?burial WHERE {
{ ?object a nmo:NumismaticObject ;
 nmo:hasTypeSeriesItem <http://numismatics.org/ocre/id/ric.1(2).aug.1A>}
UNION { ?broader skos:broader+ <http://numismatics.org/ocre/id/ric.1(2).aug.1A> .
?object nmo:hasTypeSeriesItem ?broader ;
  a nmo:NumismaticObject }
UNION { ?contents a dcmitype:Collection ; 
  nmo:hasTypeSeriesItem <http://numismatics.org/ocre/id/ric.1(2).aug.1A> .
?object dcterms:tableOfContents ?contents }
?object dcterms:title|skos:prefLabel ?title .
{ ?object nmo:hasFindspot/crm:P7_took_place_at/crm:P89_falls_within ?findspot }
UNION { ?object dcterms:isPartOf ?hoard .
        ?hoard a nmo:Hoard ;
        skos:prefLabel ?hoardLabel ;
        nmo:hasFindspot/crm:P7_took_place_at/crm:P89_falls_within ?findspot .
   		OPTIONAL {?hoard nmo:hasClosingDate ?burial . FILTER isLiteral(?burial)}
        OPTIONAL {?hoard nmo:hasClosingDate ?closing .
                 ?closing nmo:hasEndDate ?burial}}
?findspot rdfs:label ?placeName ;
          geo:location ?loc .
?loc geo:lat ?lat ;
     geo:long ?long .
OPTIONAL { ?object rdf:type ?type FILTER (?type != skos:Concept)} 
OPTIONAL { ?object nmo:hasClosingDate ?burial . FILTER isLiteral(?burial) }}
</code></pre>
