---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

title: Nomisma.org Data
layout: default
permalink:/data
---

# Get Data

Data for Nomisma.org concepts are made open with a [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/) (CC-BY). These data can be reused for any purpose, both commercial and non-commercial. Third party contributions to the Nomisma.org Linked Open Data ecosystem (types, hoards, coins, etc.) come with separate rights or license statements. See the [datasets](/datasets) page for further details and links to download RDF for partner data.

## Bulk Downloads
The Nomisma concepts are regenerated nightly and available as a bulk download in [RDF/XML](/nomisma.org.rdf), [JSON-LD](/nomisma.org.jsonld), and [RDF Turtle](/nomisma.org.ttl) syntax.

These concepts are committed to a [Github repository](https://github.com/nomisma/data) nightly, and versions can be tracked back to 2012.

[Partner datasets](/datasets) are available for download, primarily as RDF/XML. Please refer to each institution's rights and/or license statements regarding reuse.

## Accessing Data Through Web Services
It is possible to access Nomisma linked data through a variety of web services, either about individual concepts or any class of object integrated into Nomisma's SPARQL endpoint.

### Individual Concepts
Nomisma supports delivery of individual concepts in a variety of models and serializations through both REST and content negotiation. Content negotiation (with the accept header) requests should be sent to the URI space [http://nomisma/id/](http://nomisma/id/). Requesting an unsupported content type will result in an HTTP 406: Not Acceptable error.

<table class="table">
	<thead>
		<tr>
			<th>Model</th>
			<th>REST</th>
			<th>Content Type</th>

		</tr>
	</thead>
	<tbody>
		<tr>
			<td>HTML</td>
			<td>http://nomisma.org/id/{$id}</td>
			<td>
				<code>text/html</code>
			</td>
		</tr>
		<tr>
			<td>GeoJSON</td>
			<td>http://nomisma.org/id/{$id}.geojson</td>
			<td>
				<code>application/vnd.geo+json</code>
			</td>
		</tr>
		<tr>
			<td>KML</td>
			<td>http://nomisma.org/id/{$id}.kml</td>
			<td>
				<code>application/vnd.google-earth.kml+xml</code>
			</td>
		</tr>
		<tr>
			<td>RDF/XML</td>
			<td>http://nomisma.org/id/{$id}.rdf</td>
			<td>
				<code>application/rdf+xml</code>
			</td>
		</tr>
		<tr>
			<td>Turtle</td>
			<td>http://nomisma.org/id/{$id}.ttl</td>
			<td>
				<code>text/turtle</code>
			</td>
		</tr>
		<tr>
			<td>JSON-LD</td>
			<td>http://nomisma.org/id/{$id}.jsonld</td>
			<td>
				<code>application/ld+json</code>
			</td>
		</tr>
	</tbody>
</table>

### SPARQL Endpoint
The Nomisma.org [SPARQL endpoint](/sparql) is a deployment of Apache Fuseki, which conforms to the W3C's SPARQL 1.1 specification. See the endpoint page for further details about URL parameters and content negotiation.

