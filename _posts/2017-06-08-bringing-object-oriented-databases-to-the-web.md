---
title: Bringing Object-Oriented Databases to the Web
layout: single
author_profile: true
comments: true
related: true
author: Felix
tags: Bachelorarbeit
---

**Geeignet für:** Bachelorarbeit

In dieser Arbeit soll eine der führenden objektorientierten Datenbanken Actian NoSQL (ehemals Versant) über Orestes für Uses-Cases im Web erweitert werden. Orestes bietet Interfaces für verschiedene Datenbankoperationen, die implementiert werden können (siehe Graphik). Orestes reichert das System auf diese Weise automatisch mit Caching, Transaktionen, Schema-Management, server-seitigem Business Code, User-Management etc. an. Actian NoSQL wird hiermit durch die Baqend REST/HTTP Schnittstelle und das JavaScript API aus beliebigen Umgebungen, u.a. Webseiten und Apps ansprechbar. Eine Implementation von 2012 auf einer früheren Version von Orestes kann für die Arbeit weitergenutzt werden. 

![](/assets/images/versant1.png)

Eigenschaften der ursprünglichen Implementierung (2012):
* Uses the Versant's Java JDO client API
* Based on the StorageManager interface in the VDS layer
* All CRUD and query operations available via the REST API
* Schemas/metadata are transferred in binary, updates were not supported through the API
* Optimistic transactions based on VOD transactions
	* Replaced by a more scalable implementation later on
	* Could also be used for VOD

Ziele:
* Universal REST API for Actian NoSQL users
* Versant queries can easily be plugged into Orestes
* New optimistic transaction API, which should work very well with the Versant API (Bulk updates at commit time), not public yet
* All CRUD operations can be executed within a transaction or executed alone
* Baqend schema API now supports many update operations (rename, indexes, add/drop schema and fields, type up/downcast, inheritance) -> schema migrations can be mapped

Für die Bearbeitung werden alle benötigten Lizenzen, Umgebungen und Tools zur Verfügung gestellt.

### Literatur:
* [Bachelorarbeit](https://vsis-www.informatik.uni-hamburg.de/getDoc.php/thesis/605/bachelor.pdf) und [Masterarbeit](https://vsis-www.informatik.uni-hamburg.de/getDoc.php/thesis/695/MasterarbeitOpt.pdf) zu der ursprünglichen Integration von Versant in Orestes
* [Paper & Literatur](/paper/)
* [Actian Versant NoSQL](https://www.actian.com/data-management/versant-nosql-object-database/)