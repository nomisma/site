---
title: Nomisma.org Scientific Committee
layout: default
permalink: /about/scientific_committee/
---

# Scientific Committee
The Nomisma.org scientific committee consists of experts in the fields of numismatics, computer science, and Semantic Web principles.

<div class="row">    
    {% for person in site.data.committee %}
        <div class="col-md-4">
            <div class="card">
                {% if person.editor_uri %}
                    <h3><a href="{{ person.editor_uri }}">{{ person.name }}</a></h3>                   
                {% else %}
                    <h3>{{ person.name }}</h3>
                {% endif %}            
            
                {% if person.org_url %}
                    <h4><a href="{{ person.org_url}}">{{ person.org }}</a></h4>
                {% else %}
                    <h4>{{ person.org }}</h4>
                {% endif %}
                
                {% if person.orcid_uri %}
                <p><a href="{{person.orcid_uri}}">
                    <img alt="ORCID logo" src="https://info.orcid.org/wp-content/uploads/2019/11/orcid_16x16.png" width="16" height="16" />{{person.orcid_uri}}</a></p>
                {% endif %}
                
                <div class="truncate">{{ person.bio }}</div>
            </div>        
        </div>   
    {% endfor %}
</div>