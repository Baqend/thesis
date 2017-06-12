---
title: Providing Low Latency for DynamoDB, Cassandra, PostgreSQL, Azure DocumentsDB,
  RethinkDB, Cassandra through the Orestes Caching Middleware (4 Themen)
layout: single
author_profile: true
comments: true
related: true
author: Felix
tags: Masterarbeit Bachelorarbeit
---

**Geeignet für:** Masterarbeit oder Bachelorarbeit

**Offen:** Azure DocumentsDB, RethinkDB, PostgreSQL

Orestes ist eine datenbankunabhängige Cloud-Middleware für (NoSQL) Datenbanken, die durch Caching extrem geringe Latenz erzielt. Orestes ist so konzipiert, dass durch die Implementierung bestimmter Schnittstellen (z.B. CRUD, Queries, Schemaänderungen) beliebige Datenbanken angebunden und durch eine *Unified REST API*einheitlich angesprochen werden können. Die Datenbank wird dabei automatisch angereichert um Fähigkeiten, die ihr sonst fehlen, u.a. gloabl verteiltes Web-Caching, semi-strukturierte Schemata, Zugriffskontrolle durch ACLs, etc. Ziel der Arbeit ist die Anbindung eines der Systeme DynamoDB, Cassandra, HBase oder PostgreSQL mit einer Studie darüber, welche Eigenschaften sich erzielen lassen und welche aufgrund der Datenbankarchitektur und seiner Schnittstellen nicht erreichbar sind.

### Ziele:

-   Analyse der Datenbankeigenschaften aus Sicht der verschiedenen Orestes-Schnittstellen für CRUD, Queries, Partial Updates etc.
-   Problembeschreibung: Identifikation der fehlenden Fähigkeiten der Datenbank und Studie, welche sich durch Orestes automatisch erzielen lassen.
-   **Konsistenzmodell**: Welche Auswirkung haben die Konistenzgarantien der Datenbank für Clients und wie spielen sie mit Caching zusammen?
-   **Optionale Vertiefung**: welche Skalierbarkeitseigenschaften weist die Datenbank auf und wie können diese durch Orestes in Form von Auto-Scaling genutzt werden?
-   **Implementierung**: Anbindung der Datenbank an Orestes für die umsetzbaren Schnittstellen.
-   **Evaluation**:

### Einführungsliteratur:

-   [Orestes API](http://www.baqend.com/guide/)
-   [CloudDB Paper (Orestes Architektur)](http://www.baqend.com/paper/clouddb.pdf)
-   [Kapitel 5 u. 5.1.: Beispiel für Redis-Anbindung in Orestes](http://orestes.info/assets/files/Masterarbeit.pdf)

### Vertiefungsliteratur:

-   [Übrige Orestes Paper](/paper/)
-   [Cassandra](http://cassandra.apache.org/)
-   [HBase](http://hbase.apache.org/)
-   [Mastering DynamoDB](http://www.amazon.de/Mastering-DynamoDB-Tanmay-Deshpande-ebook/dp/B00N1X691W/ref=sr_1_3?ie=UTF8&qid=1436351157&sr=8-3&keywords=dynamodb)
-   [PostgreSQL](http://www.postgresql.org/)