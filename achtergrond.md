---
layout: home
title: Achtergrond
---

De [OpenAPI Specification (3.x)](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.0.md) is een API Specification framework van het [OpenAPI initiative](https://www.openapis.org/) en is in mei 2018 opgenomen op de [pas toe leg uit lijst](https://www.forumstandaardisatie.nl/standaard/openapi-specification) van Bureau Forum Standaardisatie en daarmee het verplichte formaat om API's van de Nederlandse overheid te beschrijven.

## API Specification

Een API Specification beschrijft het 'contract' tussen een RESTful API en een client. Hierin staat hoe welke operaties gedaan kunnen worden, welke beveiligingsprotocollen en gegevensformaten ondersteund worden, etc. Een API Specification is vergelijkbaar met WSDL (Web Service Description Language) voor SOAP. De bekendste manieren (frameworks) om deze informatie uit te drukken waren Swagger, RAML (RESTful API Modeling Language) en API Blueprint. In 2017 hebben de bedrijven achter deze frameworks de handen ineen geslagen om met het OpenAPI intiative het beste van alle werelden te combineren tot één nieuwe variant om RESTful API's te beschrijven: de OpenAPI Specification (OAS).

### Swagger

Swagger 2.0, in 2017 officieel door SmartBear (het bedrijf achter Swagger) gedoneerd aan het OpenAPI Initiative en omgedoopt tot OASv2, vormde als populairste framework de basis voor de nieuwe versie van de OpenAPI Specification (OASv3). Het 'merk' Swagger bestaat onder het bedrijf SmartBear nog steeds, maar wordt tegenwoordig gebruikt voor bepaalde tools die OAS ondersteunen, zoals Swagger UI om op basis van OAS een API reference te genereren of Swagger Editor om OpenAPI specificaties te kunnen schrijven. De term wordt ook nog gebruikt om OASv2 (herkenbaar aan het `swagger: 2.0` attribuut bovenaan het bestand) aan te duiden, maar dit is dus feitelijk onjuist.

## Machine-readable

Het idee achter een (Open)API Specification is dat deze machine-readable is, zodat tools, libraries en SDK's out-of-the-box de (on)mogelijkheden van een API begrijpen en zo grote delen van de implementatie automatiseerbaar maken. Denk hierbij aan API references, tests, validators, gateway configuraties, etc. Door één framework te kiezen als de standaard is het eenvoudiger om zelf maatwerk oplossingen te ontwikkelen en te onderhouden, zoals bijvoorbeeld API documentatie dat voldoet aan de voor Europese overheid verplichte WCAG 2.0 toegankelijkheidsrichtlijnen.

### JSON/YAML

Een OAS kan uitgedrukt worden in zowel JSON (JavaScript Object Notation) als YAML (Yet Another Markup Language). Beiden zijn één op één uitwisselbaar, wat wil zeggen dat je probleemloos JSON naar YAML kunt converteren en vice versa. Het voordeel van JSON is dat dit formaat eenvoudig door machines te parsen is, het voordeel van YAML is dat dit formaat beter leesbaar is voor mensen (bijvoorbeeld tijdens het API design). De OAS die door de Analyse Tool gegenereerd wordt, wordt dan ook in beide formaten aangeboden.

## Open Source

De OpenAPI Specification wordt beheerd door het OpenAPI Initiative, een [consortium van grote bedrijven](https://www.openapis.org/membership/members) (waaronder die achter de voorheen genoemde frameworks) onder de vlag van de [Linux Foundation](https://www.linuxfoundation.org/). Dit garandeert dat het een volledig Open Source en vendor neutrale standaard is die door een grote internationale community ondersteund wordt en daarmee de de facto standaard in de API industrie is.