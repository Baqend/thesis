---
title: Advanced Search and Aggregations with MongoDB and Orestes
layout: single
author_profile: true
comments: true
related: true
tags: vergeben
---

**Geeignet für: ** Masterarbeit

In dieser Arbeit sollen das [Aggregation Framework](https://docs.mongodb.com/manual/aggregation/) und die [Volltextsuche](https://docs.mongodb.com/manual/reference/operator/query/text/) von MongoDB mit Orestes kombiniert werden.

### Ziele:

-   **Recherche: ** Welche Funktionen untersützt MongoDB zur Volltextsuche (z.B. Stop-word-removal, Stemming, Gewichtigung, Facetting, Konjunktion/Disjunktion; Vergleich mit Funktionen von Search-Plattformen Solr und ElasticSearch. Welche Aggregationstypen lassen sie mit MongoDB umsetzen; Vergleich mit SQL-99.
-   **Entwurf und Implementierung ** einer Orestes-Umsetzung von Such-Indizierung (analog zu Query-Ergebnissen, aber sortiert nach Match-Score) und Aggregationen für den Java-basierten Server.
-   **Evaluation ** der Implementation und (quantitativer) Vergleich mit einem normalen MongoDB-Zugriff.

### Literatur:

-   [Aggregation Framework](https://docs.mongodb.com/manual/aggregation/)
-   [Volltextsuche](https://docs.mongodb.com/manual/reference/operator/query/text/)
-   [MongoDB in Action (Buch)](https://www.amazon.de/MongoDB-Action-Kyle-Banker/dp/1617291609/ref=sr_1_1?ie=UTF8&qid=1477496019&sr=8-1&keywords=mongodb+in+action)
-   [MongoDB vs. Elasticsearch: The Quest of the Holy Performances (Blog post)](http://blog.quarkslab.com/mongodb-vs-elasticsearch-the-quest-of-the-holy-performances.html)