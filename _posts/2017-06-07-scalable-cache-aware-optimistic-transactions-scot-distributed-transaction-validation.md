---
layout: single
author_profile: true
comments: true
related: true
title: 'Scalable Cache-Aware Optimistic Transactions (SCOT): Distributed Transaction
  Validation'
tags: vergeben
---

**Geeignet für:** Masterarbeit; hoher Anspruch; Publikation wahrscheinlich

Das SCOT Konzept (siehe Orestes Paper) ist ein Algorithmus, um ACID Transaktionen über beliebige Datenbanken auszuführen und gleichzeitig Leseoperationen aus (potentiell veralteten) Caches zuzulassen. Die neue Kombination aus Caching und optimistischen Transaktionen mit BOCC+ eröffnet die Möglichkeit eines der ältesten Probleme von transaktionalen Systemen zu lösen: hohe Abbruchraten von optimistischen Transaktionen. Der Grund dafür sind schnellere Leseoperationen aus Caches, die die Gesamtausführungszeit von Transaktionen minimieren. Da die Abbruchraten polynomiell von der Transaktionsdauer abhängen, können sie auf diesem Wege drastisch reduziert werden. In der Arbeit soll ein verteilter Transaktions-Validator für SCOT implementiert werden. Dieser erhält als Eingabe die Read- und Write-Sets von committenden Transaktionen, um sie korrekt, performant und ausfallsicher zu validieren.

### Ziele:

-   Formale Beschreibung von SCOT durch seine Algorithmen *Read, Write und Commit*. Vergleich mit BOCC+ (zwei Unterschiede: Caching und nebenläufige Validierung nicht-konfliktierender Transaktionen).
-   **Übersicht über Realisierungsalternativen geben**: auf Koordinationsdienst wie Redis, ZooKeeper oder etcd aufsetzen, oder Java In-Memory-Implementierung (siehe Omid).
-   **Implementierung**: SCOT-Validator-Service in Orestes und transactional read + transactional write CRUD Operationen. Architektur: Validator-Interface & Klasse für wechselseitigen Ausschluss überlappender Write-Sets *acquireLock(tid, writeset)*, Validierung des Read-Sets *validate(tid, readset, currentDbStateReadSet) -> {commit, abort}*. Orestes Coordinator Projekt (basiert auf Redis) erweitern um acquireLock zu implementieren. Resultat: Validierung über lokalen Koordinator möglich (SCOT-embedded) und über verteilten Koordinator (SCOT-distributed).
-   **Diskussion**: Fehlerszenarien (Netzwerkpartitionen und Crashes) und daraus resultierende Garantien des Validators --> Wann muss geloggt werden? Wann können Validierungslocks freigegeben werden? Wie sieht die Restart-Prozedur pro Server aus?
-   **Vertiefung**: Behandlung nicht-transaktionaler Operationen in Kombination mit SCOT-Transaktionen.
-   **SCOT Analyse**: Monte-Carlo Simulation zur empirischen Ermittlung der Abbruchrate von SCOT vs BOCC. Vorbild: [PBS Rechner](http://pbs.cs.berkeley.edu/#demo).
    -   **Gegeben**: Workload mit object count (n), popularity distribution, workload mix (read/write) (siehe YCSB) + cache-TTL (ttl), Bloom filter false positive rate (f), Transaction Parallelism (p).
    -   **Annahme**: ein shared cache (einfachster Fall) und Abruf des Bloom filter zu Beginn einer Transaktion.
    -   **Latenzen**: Client-Cache, Cache-Server, Server-DB einstellbar. Standard-Werte: siehe Cache Sketch Paper.
    -   **Finde**: Abbruchrate mit Caching + BF vs Abbruchrate ohne Caching + BF durch Monte-Carlo-Simulation (siehe PBS), d.h. ziehen von Latenzen, virtuelles Ausführen der parallelen Transaktionen, Validierung (Commit vs Abort?), Sammeln der Metriken Commits, Aborts, Hits, Misses.
-   **Praktische Evaluation**: verteilte Validierung in Orestes mit MongoDB auf Performance und Korrektheit testen. Vergleich: Kein Caching vs Caching -> Abbruchraten.

### Einführungsliteratur:

-   [Probabilistically Bounded Staleness (Simulationsidee)](http://pbs.cs.berkeley.edu/)
-   [Orestes Paper, Kapitel IV](http://www.baqend.com/paper/clouddb.pdf)
-   [Cache Sketch Paper, Kapitel 1 und 2.1](http://www.baqend.com/paper/btw-cache.pdf)
-   [Cache Sketch Präsentation](http://www.btw-2015.de/res/slides/Gessert-The_Cache_Sketch-165_slides.pdf)
-   [Verteiltes und Paralleles Datenmanagement, Kapitel 12.4, Optimistische Transaktionen](http://link.springer.com/book/10.1007/978-3-642-45242-0)

### Vertiefungsliteratur:

-   [Performance Evaluation: Origins and Directions, Kapitel 5.2](http://books.google.de/books?id=aHrXH_aYm8YC&pg=PA345&lpg=PA345&dq=optimistic+transactions+conflict+probability&source=bl&ots=j_JW5NPlxO&sig=YrtIoFHuucUaGBSGzIq3n3l_rXY&hl=de&sa=X&ei=9BonU6bSG8bRtQb1moC4Ag&ved=0CDsQ6AEwAQ#v=onepage&q=optimistic%20transactions%20conflict%20probability&f=false)
-   [Benchmarking cloud serving systems with YCSB](http://ipij.aei.polsl.pl/django-media/lecture_file/ycsb.pdf)
-   [Omid: Lock-free transactional support for distributed data stores](http://nosqlmark.informatik.uni-hamburg.de/sdb2014/res/paper/Omid.pdf)
-   [Scalable distributed transactions across heterogeneous stores](http://ieeexplore.ieee.org/xpl/articleDetails.jsp?arnumber=7113278)
-   [Orestes Paper Entwurf, Kapitel III c](https://www.dropbox.com/s/x3knzlk0kehalr3/Paper.pdf?dl=0)
-   [Redis Optimistic Transactions (Basis des Orestes Coordinators)](http://redis.io/topics/transactions)