---
title: List of all Roman Emperors
layout: default
stub: list-roman-emperors
order: 1
permalink: /documentation/sparql/list-roman-emperors/
---

### {{page.title}} {#{{page.stub}}}

Get all people with a role of `nm:roman_emperor` and display their English preferred label.

<pre><code class="language-sparql">PREFIX rdf:		<http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dcterms:		<http://purl.org/dc/terms/>
PREFIX foaf:		<http://xmlns.com/foaf/0.1/>
PREFIX nm:		<http://nomisma.org/id/>
PREFIX nmo:		<http://nomisma.org/ontology#>
PREFIX org:		<http://www.w3.org/ns/org#>
PREFIX skos:		<http://www.w3.org/2004/02/skos/core#>

SELECT ?uri ?label WHERE {
?uri a foaf:Person ;
  skos:prefLabel ?label ;
  org:hasMembership ?membership .
?membership org:role nm:roman_emperor .
FILTER(langMatches(lang(?label), "EN"))
}
</code></pre>
