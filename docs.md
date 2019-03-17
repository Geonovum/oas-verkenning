---
layout: home
title: Documentatie
---

API Specificaties toevoegen, valideren en transformeren naar OASv3 kan via de Analyse API. Via deze API is alle informatie die op deze site gevisualiseerd is ook op te vragen. Zie de [API Reference](https://rebilly.github.io/ReDoc/?url=https://geonovum.github.io/oas-verkenning/assets/openapi.yaml&nocors) voor meer informatie over het gebruik van de Analyse API, hieronder een samenvatting van de functionaliteiten:

|Operatie|Omschrijving|
|-|-|
|`POST /apis`|API aanbieden ter analyse (zie voor meer info ook het [proces](proces.html))|
|`GET /apis`|Overzicht van alle API's en bijbehorende resultaten|
|`GET /apis/{id}`|Gegenereerde OASv3 (indien mogelijk) in YAML formaat voor mensen|
|`GET /apis/{id}/openapi.yaml`|Gegenereerde OASv3 (indien mogelijk) in YAML formaat voor mensen|
|`GET /apis/{id}/openapi.json`|Gegenereerde OASv3 (indien mogelijk) in JSON formaat voor machines|