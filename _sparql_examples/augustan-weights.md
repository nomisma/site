---
title: All weights of Augustan denarii
layout: default
stub: augustan-weights
order: 2
permalink: /documentation/sparql/augustan-weights/
---

### {{page.title}} {#{{page.stub}}}

This query yields all coins that have a coin type with the authority (`nmo:hasAuthority`) of Augustus and denomination (`nmo:hasDenomination`) of denarius from *Roman Imperial Coinage* (thus excluding provincial coinage, if applicable), and includes their weight (`nmo:hasWeight`). Note that the weight is *required*, not optional in this query.

<pre><code class="language-sparql">PREFIX rdf:		<http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dcterms:		<http://purl.org/dc/terms/>
PREFIX nm:		<http://nomisma.org/id/>
PREFIX nmo:		<http://nomisma.org/ontology#>

SELECT ?type ?weight WHERE {
?type nmo:hasAuthority nm:augustus ;
  nmo:hasDenomination nm:denarius ;
  dcterms:source nm:ric.
?coin nmo:hasTypeSeriesItem ?type .
?coin nmo:hasWeight ?weight
}
</code></pre>
