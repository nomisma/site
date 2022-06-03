---
title: Nomisma.org SPARQL Examples
layout: default
permalink: /documentation/sparql/
id: doc-sparql
---

# SPARQL Examples

Nomisma.org has implemented a SPARQL endpoint since 2013, and although the ontology and models have evolved considerably since then, it remains the core component of Nomisma's infrastructure for aggregating data that facilitate display of related specimens, geographic visualizations, and metrical analyses in numerous external projects.

The SPARQL endpoint include the Linked Open Data representing numismatic concepts published in the Nomisma.org namespace, but also external [datasets]({{site.baseurl}}/datasets) of coin types, specimens, hoards, monograms, and die links expressed as RDF in the Nomisma [ontology]({{site.baseurl}}/ontology). It is therefore possible to exploit the network of relations between these various types of entities in order to form either simple or complex queries. Some queries underlie human-usable interfaces in other projects, such as [Online Coins of the Roman Empire](http://numismatics.org/ocre), and these interfaces (maps showing the circulation of coins, charts depicting average weights or typological distributions, etc.) typically represent the most common research questions scholars have of the material. However, it is impossible to predict the research needs of all scholars, and the SPARQL endpoint is available to execute complicated queries. The SPARQL endpoint responds with machine-readable data, such as CSV, that can be imported into spreadsheet software, R Studio, or other platforms in order to conduct other forms of visualization.

There are some introductory materials to Nomisma.org's online ontology, model, and SPARQL endpoint which are still largely technically relevant, such as this video below that was presented to the Dublin Core Metadata Initiative in 2015:

<div class="text-center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/3YhG5QQmhvU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

The SPARQL query examples cited above are listed on the Numishare blog [here](https://numishare.blogspot.com/2015/05/sparql-examples-for-dcmiasis-webinar.html), stored on Gist. A wide variety of other SPARQL queries have been uploaded to Ethan Gruber's [Gist account](https://gist.github.com/ewg118/). You can also find templates for created Nomisma RDF exports from normalized data in OpenRefine.

More recently, the Nomisma.org information system and example SPARQL queries were presented in the American Numismatic Society's May 9, 2022 Long Table Series, *Long Table 91. Data Wrangling: How to use Nomisma*, recorded and available below:

<div class="text-center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/0_2FrxfM3d0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

A limitless number of queries can be submitted simply to interrogate Nomisma.org concepts and their relations to each other, independent of links to related coin types, hoards, or specimens aggregated by Nomisma.org. Since the minimum threshold for integrating coins from museum or archaeological collections into Nomisma.org is a link to a coin type and/or hoard URI, it is possible to make a wide variety of statistical queries about coins by means of their relationships to types, and the relationships between those types and Nomisma.org numismatic concepts and URIs that represent the concepts of symbols and monograms.

## Table of Contents

{% for page in site.sparql_examples %}
{% assign sorted = site.sparql_examples | sort:"order" %}
 - [{{page.title}}](#{{page.stub}})
{% endfor %}

## Queries

{% for page in site.sparql_examples %}
{% assign sorted = site.sparql_examples | sort:"order" %}
{{page.content}}
{% endfor %}

