---
title: All coins found in Northamptonshire, ordered chronologically by issue
layout: default
stub: geographic-hierarchy
order: 7
permalink: /documentation/sparql/geographic-hierarchy/
---

### {{page.title}} {#{{page.stub}}}

This query uses property paths to look for children of (`crm:P89_falls_within`) of the Wikidata URI for Northamptonshire, England ([http://www.wikidata.org/entity/Q23115](http://www.wikidata.org/entity/Q23115)).

<pre><code class="language-sparql">PREFIX crm: <http://www.cidoc-crm.org/cidoc-crm/>
PREFIX dcmitype: <http://purl.org/dc/dcmitype/>
PREFIX dcterms: <http://purl.org/dc/terms/>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
PREFIX geo: <http://www.w3.org/2003/01/geo/wgs84_pos#>
PREFIX nm: <http://nomisma.org/id/>
PREFIX nmo: <http://nomisma.org/ontology#>
PREFIX org: <http://www.w3.org/ns/org#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

SELECT ?coin ?type ?date ?place WHERE {
?coin nmo:hasFindspot/crm:P7_took_place_at/crm:P89_falls_within ?place ;
      nmo:hasTypeSeriesItem ?type ;
      a nmo:NumismaticObject .
?place crm:P89_falls_within+ <http://www.wikidata.org/entity/Q23115> .
?type nmo:hasEndDate ?date .
} ORDER BY ASC(?date) LIMIT 100
</code></pre>
