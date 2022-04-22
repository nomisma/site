---
title: Average weight of Augustan denarii
layout: default
stub: augustan-avg-weight
order: 3
permalink: /documentation/sparql/augustan-avg-weight/
---

### {{page.title}} {#{{page.stub}}}

Like the query above, now we are calculating the average of all of the weights of Augustan denarii.

<pre><code class="language-sparql">PREFIX rdf:		<http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dcterms:		<http://purl.org/dc/terms/>
PREFIX nm:		<http://nomisma.org/id/>
PREFIX nmo:		<http://nomisma.org/ontology#>
PREFIX xsd:		<http://www.w3.org/2001/XMLSchema#>

SELECT (AVG(xsd:decimal(?weight)) AS ?average) WHERE {
?type nmo:hasAuthority nm:augustus ;
  nmo:hasDenomination nm:denarius ;
  dcterms:source nm:ric.
?coin nmo:hasTypeSeriesItem ?type .
?coin nmo:hasWeight ?weight
}
</code></pre>
