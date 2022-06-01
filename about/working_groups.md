---
title: Nomisma.org Scientific Committee
layout: default
permalink: /about/working_groups/
---

# Working Groups
Nomisma.org consists of multiple working groups responsible for the creation of concepts in various fields of numismatics.

<div class="row section">
	<div class="col-md-4 text-center">
		<h3>Bibliography</h3>	

	</div>
	<div class="col-md-8">
		<ul style="margin-top:20px">
		{% for person in site.data.wg_bibliography %}
		<li>{{person.name }}, 
			{% if person.org_url %}
			    <a href="{{ person.org_url}}">{{ person.org }}</a>
			{% else %}
			    {{ person.org }}
			{% endif %}
			{% if person.email and person.role == 'chair' %}
				<a href="mailto:{{person.email}}"><span class="glyphicon glyphicon-envelope"/></a>
			{% endif %}
		 </li>
		 {% endfor %}
		 </ul>
	</div>
</div>
<div class="row section">
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
			{% if person.email and person.role == 'chair' %}
				<a href="mailto:{{person.email}}"><span class="glyphicon glyphicon-envelope"/></a>
			{% endif %}
		 </li>
		 {% endfor %}
		 </ul>
	</div>
</div>
<div class="row section">
	<div class="col-md-4 text-center">
		<h3>Hoards</h3>
	</div>
	<div class="col-md-8">
		<ul style="margin-top:20px">
		{% for person in site.data.wg_hoards %}
		<li>{{person.name }}, 
			{% if person.org_url %}
			    <a href="{{ person.org_url}}">{{ person.org }}</a>
			{% else %}
			    {{ person.org }}
			{% endif %}
			{% if person.email and person.role == 'chair' %}
				<a href="mailto:{{person.email}}"><span class="glyphicon glyphicon-envelope"/></a>
			{% endif %}
		 </li>
		 {% endfor %}
		 </ul>
	</div>
</div>
<div class="row section">
	<div class="col-md-4 text-center">
		<h3>Iconography</h3>	
	</div>
	<div class="col-md-8">
		<ul style="margin-top:20px">
		{% for person in site.data.wg_iconography %}
		<li>{{person.name }}, 
			{% if person.org_url %}
			    <a href="{{ person.org_url}}">{{ person.org }}</a>
			{% else %}
			    {{ person.org }}
			{% endif %}
			{% if person.email and person.role == 'chair' %}
				<a href="mailto:{{person.email}}"><span class="glyphicon glyphicon-envelope"/></a>
			{% endif %}
		 </li>
		 {% endfor %}
		 </ul>
	</div>
</div>
<div class="row section">
	<div class="col-md-4 text-center">
		<h3>Iron Age</h3>		
		<img src="{{site.baseurl}}/images/iron_age.jpg" alt="Iron Age coin"/>
	</div>
	<div class="col-md-8">
		<ul style="margin-top:20px">
		{% for person in site.data.wg_iron_age %}
		<li>{{person.name }}, 
			{% if person.org_url %}
			    <a href="{{ person.org_url}}">{{ person.org }}</a>
			{% else %}
			    {{ person.org }}
			{% endif %}
			{% if person.email and person.role == 'chair' %}
				<a href="mailto:{{person.email}}"><span class="glyphicon glyphicon-envelope"/></a>
			{% endif %}
		 </li>
		 {% endfor %}
		 </ul>
	</div>
</div>
<div class="row section">
	<div class="col-md-4 text-center">
		<h3>Medieval/Modern European</h3>		
		<img src="{{site.baseurl}}/images/medieval.jpg" alt="Medieval coin"/>
	</div>
	<div class="col-md-8">
		<ul style="margin-top:20px">
		{% for person in site.data.wg_medieval-modern %}
		<li>{{person.name }}, 
			{% if person.org_url %}
			    <a href="{{ person.org_url}}">{{ person.org }}</a>
			{% else %}
			    {{ person.org }}
			{% endif %}
			{% if person.email and person.role == 'chair' %}
				<a href="mailto:{{person.email}}"><span class="glyphicon glyphicon-envelope"/></a>
			{% endif %}
		 </li>
		 {% endfor %}
		 </ul>
	</div>
</div>
<div class="row section">
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
			{% if person.email and person.role == 'chair' %}
				<a href="mailto:{{person.email}}"><span class="glyphicon glyphicon-envelope"/></a>
			{% endif %}
		 </li>
		 {% endfor %}
		 </ul>
	</div>
</div>
<div class="row section">
	<div class="col-md-4 text-center">
		<h3>Roman Provincial</h3>
		<img src="{{site.baseurl}}/images/roman_provincial.jpg" alt="Roman Provincial coin"/>
	</div>
	<div class="col-md-8">
		<ul style="margin-top:20px">
		{% for person in site.data.wg_roman_provincial %}
		<li>{{person.name }}, 
			{% if person.org_url %}
			    <a href="{{ person.org_url}}">{{ person.org }}</a>
			{% else %}
			    {{ person.org }}
			{% endif %}
			{% if person.email and person.role == 'chair' %}
				<a href="mailto:{{person.email}}"><span class="glyphicon glyphicon-envelope"/></a>
			{% endif %}
		 </li>
		 {% endfor %}
		 </ul>
	</div>
</div>
