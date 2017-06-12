---
title: 'Polyglot Persistence Mediator: Annotation-based Scoring'
layout: single
author_profile: true
comments: true
related: true
tags: Masterarbeit
---

**Geeignet für:** Masterarbeit

Der Polyglot Persistence Mediator (PPM) ist die Vision einer automatisierten Verwendung verschiedener Datenbanksysteme (Polyglot Persistence) durch die deklarative Angabe von Anforderungen. Diese werden in Form von Service Level Agreements (z.B. Latenz < 30ms, Top-K-Queries) am Schema annotiert. Ein Scoring ermittelt anhand dieser Annotationen die ideale Datenbank für jedes Element des Schemas (Routing Model). Der PPM routet zur Laufzeit gemäß des Routing-Models die Anfragen und CRUD Operationen zur passenden Datenbank. Ziel dieser Arbeit ist das Anlegen eines Katalogs einiger umsetzbarer Annotationen/SLAs, die Implementierung des Scoring Algorithmus für diese SLAs (siehe [Paper](http://www.baqend.com/paper/btw-polyglot.pdf)), sowie die Umsetzung des Routings für die Kombination aus Redis und MongoDB.

### Ziele:

-   **Katalog von SLAs anlegen**: kategorisieren nach functional, non-functional und continuous non-functional, Annotationslevel (DB, Table, Feld). Jeweils "Patterns" zu einer möglichen naiven Implementierung ohne PPM sammeln, zu messende Metriken und Arten der Erfassung pro SLA diskutieren, bei binären Eigenschaften: Literatur-Recherche, wie/ob sie in Redis und MongoDB sicherzustellen sind.
-   **Routing-Strategien**: Katalog für die notwendigen Aktionen des PPMs zur Sicherstellung der jeweiligen SLAs diskutieren, sowie Metrik-Erfassung. Vier Modelle erötern:
    -   **PPM-mixed**: unterschiedliche Zieldatenbanken für jedes Schemaelement (Feld, Table, DB) zulassen -> maximale Heterogenität, maximaler Koordinationsaufwand, potentiell ideale Performance
    -   **PPM-microbatched**: wie PPM-mixed, aber ein System wird als "primary database" designiert und erhält in Microbatches (z.B. alle 5 Sekunden), alle (verdichteten) Updates -> beliebige Queries auf allen Daten mit Staleness-Bound des Microbatch-Intervalls
    -   **PPM-entity**: Es wird garantiert, dass Objekte jeweils vollständig (ohne Zerlegung) in einer Datenbank angespeichert werden -> einfaches Routing, ponteziell konfliktierende Anforderungen zwischen Feldern
    -   **PPM-advisory**: Es wird lediglich ermittelt, welche Datenbank für das Gesamtschema den besten Score erzielen kann -> effektiv kein Routing und keine polyglotte Persistenz, sondern nur ein Hint welches System insgesamt den besten Trade-off liefert.
-   **Implementierung:** SLAs modellieren und Schema erweitern um Annotationen zu tragen. Scoring Algorithmus aus Paper implementieren und Routing Modell generieren. Laufzeit-Routing für ausgewählte SLAs in Orestes implementieren, d.h. korrekte Weiterleitungen an die Redis und MongoDB Schnittstellen und Ergänzungen von Metadaten, um spätere Auflösung bei Reads und Queries vorzunehmen.
-   **Evaluation:** Performance verschiedener SLA-Kombinationen messen und mit nicht-polyglotter Umsetzung auf jeweils MongoDb und Redis vergleichen (mit und ohne Orestes).

### Einführungsliteratur:

-   [BTW Polyglot Persistence Paper: Idee des Polyglot Persistence Mediators](http://www.baqend.com/paper/btw-polyglot.pdf)
-   [Zugehörige Präsentation](http://www.btw-2015.de/res/slides/Schaarschmidt-Towards_Automated_Pol_slides.pdf)
-   [Orestes Schnittstellendokumentation](http://www.baqend.com/guide/)

### Vertiefungsliteratur:

-   [PPM Masterarbeit (Use-Case mit News-Artikeln)](https://www.dropbox.com/s/q2gwtl4p0063qxq/Bachelorarbeit.pdf?dl=0)
-   [MongoDB](http://docs.mongodb.org/manual/)
-   [Redis](http://redis.io/)
-   [Martin Kleppmann - Designing Data-Intensive Applications](http://shop.oreilly.com/product/0636920032175.do)
-   [Erhard Rahm, Gunter Saake, Kai-Uwe Sattler - Verteiltes und Paralleles Datenmanagement](http://orestes.info/assets/files/Masterarbeit.pdf)