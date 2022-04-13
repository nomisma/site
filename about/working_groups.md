---
title: Nomisma.org Scientific Committee
layout: default
permalink: /about/working_groups/
---

# Working Groups
Nomisma.org consists of multiple working groups responsible for the creation of concepts in various fields of numismatics.

<div class="row">
	<div class="col-md-4 text-center">
		<h3>Greek</h3>
		<img src="{{site.baseurl}}/images/greek.jpg" alt="Greek coin"/>
	</div>
	<div class="col-md-8">
		<ul style="margin-top:20px">
		{% for person in site.data.wg_greek %}
		<li>{{person.name }}, 
			{% if person.org_url %}
			    <a href="{{ person.org_url}}">{{ person.org }}</a>
			{% else %}
			    {{ person.org }}
			{% endif %}
		 </li>
		 {% endfor %}
		 </ul>
	</div>
</div>
<div class="row">
	<div class="col-md-4 text-center">
		<h3>Roman</h3>		
		<img src="{{site.baseurl}}/images/roman.jpg" alt="Roman coin"/>
	</div>
	<div class="col-md-8">
		<ul style="margin-top:20px">
		{% for person in site.data.wg_roman %}
		<li>{{person.name }}, 
			{% if person.org_url %}
			    <a href="{{ person.org_url}}">{{ person.org }}</a>
			{% else %}
			    {{ person.org }}
			{% endif %}
		 </li>
		 {% endfor %}
		 </ul>
	</div>
</div>

