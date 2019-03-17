---
layout: home
title: Rapport
---

{% assign totalCount = site.data.apis.size %}
{% assign organisations = '' %}
{% for api in site.data.apis %}
  {% assign organisations = organisations | append: api.organisation | append: '_|_' %}
{% endfor %}
{% assign organisations = organisations | split: "_|_" | uniq %}

Deze pagina bevat de rapportage van alle ingediende API Specificaties. Dit rapport is een 'levend document' en wordt automatisch bijgewerkt als er een nieuwe API Specificatie ter analyse wordt aangeboden via de [Analyse API](docs.html). Tot nu toe zijn de onderstaande **{{ totalCount }}** API's geanalyseerd, van de volgende **{{ organisations.size }}** verschillende organisatie's: {{ organisations | sort | join: ", " }}.

## Statistieken per API

<table>
  <thead>
    <tr>
      <th>Titel</th>
      <th>Formaat</th>
      <th>Errors</th>
      <th>Warnings</th>
      <th>Notices</th>
      <th>OASv3</th>
    </tr>
  </thead>
  <tbody>
    {% assign errors = 0 %}
    {% assign notices = 0 %}
    {% assign warnings = 0 %}
    {% assign valid = 0 %}
    {% assign api_blueprint = 0 %}
    {% assign swagger = 0 %}
    {% assign openapi_3 = 0 %}
    {% assign postman = 0 %}
    {% assign raml = 0 %}
    {% assign asyncapi_1 = 0 %}
    {% for api in site.data.apis %}
    {% if api.inputValidation.errors.size > 0 %}
      {% assign errors = errors | plus: 1 %}
    {% endif %}
    {% if api.inputValidation.notices.size > 0 %}
      {% assign notices = notices | plus: 1 %}
    {% endif %}
    {% if api.inputValidation.warnings.size > 0 %}
      {% assign warnings = warnings | plus: 1 %}
    {% endif %}
    {% if api.inputValidation.errors.size == 0 %}
      {% assign valid = valid | plus: 1 %}
    {% endif %}
    {% if api.descriptionFormat == 'api_blueprint' %}
      {% assign api_blueprint = api_blueprint | plus: 1 %}
    {% endif %}
    {% if api.descriptionFormat == 'swagger_1' or api.descriptionFormat == 'swagger_2' %}
      {% assign swagger = swagger | plus: 1 %}
    {% endif %}
    {% if api.descriptionFormat == 'openapi_3' %}
      {% assign openapi_3 = openapi_3 | plus: 1 %}
    {% endif %}
    {% if api.descriptionFormat == 'raml' %}
      {% assign raml = raml | plus: 1 %}
    {% endif %}
    {% if api.descriptionFormat == 'asyncapi_1' %}
      {% assign asyncapi_1 = asyncapi_1 | plus: 1 %}
    {% endif %}
    {% if api.descriptionFormat == 'postman' %}
      {% assign postman = postman | plus: 1 %}
    {% endif %}
    <tr>
      <td>{{ api.title }} <a href="{{ api._links.self.href }}">{% octicon link-external %}</a></td>
      <td>{{ api.descriptionFormat }}</td>
      <td>{{ api.inputValidation.errors.size }}</td>
      <td>{{ api.inputValidation.warnings.size }}</td>
      <td>{{ api.inputValidation.notices.size }}</td>
      <td>{% if api._links.openapiYaml %}<a href="{{ api._links.openapiYaml.href }}">YAML</a> - <a href="{{ api._links.openapiJson.href }}">JSON</a>{% endif %}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

## Algemene validatie statistieken

|Errors|Warnings|Notices|Valid|
|-|-|-|-|-|
|{{ errors }} ({{ errors | times: 1.0 | divided_by: totalCount | times: 100 | round: 0 }}%)|{{ warnings }} ({{ warnings | times: 1.0 | divided_by: totalCount | times: 100 | round: 0 }}%)|{{ notices }} ({{ notices | times: 1.0 | divided_by: totalCount | times: 100 | round: 0 }}%)|{{ valid }} ({{ valid | times: 1.0 | divided_by: totalCount | times: 100 | round: 0 }}%)|

## Gebruikte API specificatie standaard

|API Blueprint|RAML|Swagger|OpenAPI 3|Postman|Async API|
|-|-|-|-|-|-|-|
|{{ api_blueprint }} ({{ api_blueprint | times: 1.0 | divided_by: totalCount | times: 100 | round: 0 }}%)|{{ raml }} ({{ raml | times: 1.0 | divided_by: totalCount | times: 100 | round: 0 }}%)|{{ swagger }} ({{ swagger | times: 1.0 | divided_by: totalCount | times: 100 | round: 0 }}%)|{{ openapi_3 }} ({{ openapi_3 | times: 1.0 | divided_by: totalCount | times: 100 | round: 0 }}%)|{{ postman }} ({{ postman | times: 1.0 | divided_by: totalCount | times: 100 | round: 0 }}%)|{{ asyncapi_1 }} ({{ asyncapi_1 | times: 1.0 | divided_by: totalCount | times: 100 | round: 0 }}%)