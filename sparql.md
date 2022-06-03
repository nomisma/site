---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

title: Nomisma.org SPARQL Endpoint
layout: default
id: sparql
permalink: /sparql/
---

# SPARQL Endpoint

For examples, see [SPARQL Examples](http://nomisma.org/documentation/sparql). A basic tutorial on SPARQL is available from [Apache Jena](https://jena.apache.org/tutorials/sparql.html).

<form role="form" id="sparqlForm" action="/query" method="GET" accept-charset="UTF-8">
	<textarea name="query" rows="20" class="form-control" id="code">{% for namespace in site.data.namespaces %}{% if namespace.default == "true" %}
PREFIX {{ namespace.prefix}}:  <{{namespace.uri}}>{% endif %}{% endfor %}

SELECT * WHERE {
  ?s ?p ?o
} LIMIT 100
	</textarea>
	<br/>
	<div class="col-md-6">
		<div class="form-group">
			<h4>Additional prefixes</h4>
			<ul class="list-inline">
				{% for namespace in site.data.namespaces %}
				    {% if namespace.default == "true" %}
                    <li class="hidden">
                      <button class="prefix-button btn btn-default" title="{{ namespace.uri }}" uri="{{ namespace.uri }}">{{ namespace.prefix}}</button>
                    </li>
                    {% else %}
                    <li>
                      <button class="prefix-button btn btn-default" title="{{ namespace.uri }}" uri="{{ namespace.uri }}">{{ namespace.prefix}}</button>
                    </li>
                    {% endif %}
                {% endfor %}
			</ul>
		</div>

		<div class="form-group">
			<label for="output">Output</label>
			<select name="output" class="form-control">
				<option value="html">HTML</option>
				<option value="xml">XML</option>
				<option value="json">JSON</option>
				<option value="text">Text</option>
				<option value="csv">CSV</option>
			</select>
		</div>
		<button type="submit" class="btn btn-default">Submit</button>
	</div>
	<div class="col-md-6">
		<p class="text-info">This endpoint ({{ site.url }}/query) supports content negotiation for the following content types
			with SELECT queries: <code>text/html</code>, <code>text/csv</code>, <code>text/plain</code>, <code>application/sparql-results+json</code>, and
				<code>application/sparql-results+xml</code></p>

		<p class="text-info">When querying for geo:lat and geo:long properties, a map will be generated, and geographic data may be downloaded as GeoJSON and
			KML.</p>
	</div>
</form>