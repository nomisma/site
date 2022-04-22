---
title: Average Diameter of RIC Augustus 1A
layout: default
stub: augustus-1a-diameter
order: 5
permalink: /documentation/sparql/augustus-1a-diameter/
---

### {{page.title}} {#{{page.stub}}}

This query finds all coins connected to the OCRE URI for Augustus 1A and averages their diameters.

<pre><code class="language-sparql">PREFIX rdf:		<http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dcterms:		<http://purl.org/dc/terms/>
PREFIX nm:		<http://nomisma.org/id/>
PREFIX nmo:		<http://nomisma.org/ontology#>
PREFIX xsd:		<http://www.w3.org/2001/XMLSchema#>

SELECT (AVG(xsd:decimal(?diameter)) AS ?average) WHERE {
?object nmo:hasTypeSeriesItem <http://numismatics.org/ocre/id/ric.1(2).aug.1A> ;
  nmo:hasDiameter ?diameter
}
</code></pre>

