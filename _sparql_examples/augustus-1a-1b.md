---
title: Coins of RIC Augustus 1A and 1B
layout: default
stub: augustus-1a-ab
order: 4
permalink: /documentation/sparql/augustus-1a-ab/
---

### {{page.title}} {#{{page.stub}}}

This query is similar to the query that underlies the **Examples of this Type** section in Numishare-based digital type corpora (see Online Coins of the Roman Empire [RIC Augustus 1A](http://numismatics.org/ocre/id/ric.1(2).aug.1A), for example). The exception is that we use UNION to query for both Augustus 1A and 1B simultaneously. The query includes optional measurements and image links, as well as the numismatic collection, with a preferred language in English for that collection as provided by Nomisma.org.

<pre><code class="language-sparql">PREFIX rdf:		<http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dcterms:		<http://purl.org/dc/terms/>
PREFIX nm:		<http://nomisma.org/id/>
PREFIX nmo:		<http://nomisma.org/ontology#>
PREFIX foaf:		<http://xmlns.com/foaf/0.1/>
PREFIX skos:	<http://www.w3.org/2004/02/skos/core#>

SELECT ?object ?type ?diameter ?weight ?axis ?type ?collection ?obvThumb ?revThumb ?obvRef ?revRef ?comThumb ?comRef WHERE {
	{?object nmo:hasTypeSeriesItem <http://numismatics.org/ocre/id/ric.1(2).aug.1A> }
	UNION { ?object nmo:hasTypeSeriesItem <http://numismatics.org/ocre/id/ric.1(2).aug.1B> }
	?object rdf:type nmo:NumismaticObject .
	OPTIONAL { ?object nmo:hasWeight ?weight }
	OPTIONAL { ?object nmo:hasDiameter ?diameter }
	OPTIONAL { ?object nmo:hasAxis ?axis }
	OPTIONAL { ?object dcterms:identifier ?identifier }
	OPTIONAL { ?object nmo:hasCollection ?colUri .
		?colUri skos:prefLabel ?collection FILTER(langMatches(lang(?collection), "EN"))}
	OPTIONAL { ?object foaf:thumbnail ?comThumb }
	OPTIONAL { ?object foaf:depiction ?comRef }
	OPTIONAL { ?object nmo:hasObverse ?obverse .
		?obverse foaf:thumbnail ?obvThumb }
	OPTIONAL { ?object nmo:hasObverse ?obverse .
		?obverse foaf:depiction ?obvRef }
	OPTIONAL { ?object nmo:hasReverse ?reverse .
		?reverse foaf:thumbnail ?revThumb }
	OPTIONAL { ?object nmo:hasReverse ?reverse .
		?reverse foaf:depiction ?revRef }
}
</code></pre>
