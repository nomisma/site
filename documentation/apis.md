---
title: Nomisma.org APIs
layout: default
---

# API Documentation
This page contains documentation for using web services provided by Nomisma and how to access machine readable serializations through REST and content negotiation.

- [APIs](#apis)
- [OpenRefine Reconciliation Service](#reconciliation)

## APIs {#apis}

 {% include api-section.html %}

## OpenRefine Reconciliation Service {#reconciliation}

**Service URI:** [http://nomisma.org/apis/reconcile](http://nomisma.org/apis/reconcile)

Nomisma supports the following reconciliation services for OpenRefine:

- Main Reconciliation Service
- Preview API
- Entity Suggestion API (for autosuggest on matching terms)

All API responses are in JSON. Please see the [API documentation](https://github.com/OpenRefine/OpenRefine/wiki/Reconciliation-Service-Api) and [usage documentation](https://github.com/OpenRefine/OpenRefine/wiki/Reconciliation) for more details. The blog post, *[Nomisma launches OpenRefine reconciliation service](http://numishare.blogspot.com/2017/10/nomisma-launches-openrefine.html)*, contains further information about this particular implementation in Nomisma.
