---
title: State Management in Distributed Low-Latency Stream Processors
layout: single
author_profile: true
comments: true
related: true
author: Wolle
tags: Masterarbeit
---

**Geeignet für:** Masterarbeit

[Apache Storm](http://storm.apache.org/) ist ein System zur Verarbeitung kontinuierlicher Datenströme (Distributed Stream Processor, DSP) mit besonders geringer Ende-zu-Ende-Latenz. Es verteilt nicht nur einzelne Prozesse einer verteilten Anwendung auf mehrere Maschinen in einem Clusterverbund, sondern startet abgestürzte Prozesse auch auf anderen Maschinen neu; um dieses Feature auch für zustandsbehaftete Anwendungen nutzbar zu machen, bietet Storm ein Checkpoint-basiertes State Management, welches den Zustand der einzelnen Prozesse periodisch festschreibt. Die Erstellung eines Checkpoint liegt jedoch auf dem kritischen Verarbeitungspfad eines Prozesses und verläuft obendrein synchron, sodass sie unter Umständen starke Auswirkungen auf die Latenz in der Verarbeitungspipeline hat.\
Ziel der Arbeit ist die Implementation und Evaluierung eines komplett asynchronen State Management in Storm.

### Ziele:

-   **Recherche** geeigneter Algorithmen zur Bestimmung des globalen Systemzustands in einem verteilten System (siehe auch Vertiefungsliteratur unten) und insbesondere eine Analyse der Ansätze zum State Management der populärsten DSPs (etwa [Storm](http://storm.apache.org/), [Flink](http://flink.apache.org/), [Apex](http://apex.apache.org/), [Samza](http://samza.apache.org/) oder [Spark Streaming](http://spark.apache.org/streaming/))
-   **Entwurf und Implementierung** einer latenzoptimierten State-Implementation in Storm, die möglichst wenige Einschränkungen bezüglich der Änderungsrate und Größe des Anwendungszustandes bietet und gleichzeitig bestehende Konsistenzgarantien erhält
-   **Evaluation** der Implementation und (quantitativer) Vergleich mit der Standardimplementation in Storm sowie dem State Management in und Flink oder Apex.

### Einführungsliteratur:

-   [Storm: Grundkonzepte](http://storm.apache.org/releases/1.0.1/Concepts.html)
-   [Blog-Beitrag über State Management in Storm (ab Abschnitt „State Management")](https://community.hortonworks.com/articles/14171/windowing-and-state-checkpointing-in-apache-storm.html)

### Vertiefungsliteratur:

-   [Paper zum Chandy-Lamport-Algorithmus](http://research.microsoft.com/en-us/um/people/lamport/pubs/chandy.pdf): beschreibt einen Algorithmus zur Erstellung verteilter Snapshots; beschreibt auch anschaulich die Schwierigkeit dabei, den globalen Zustand in einem verteilten System festzuhalten
-   [Storm auf GitHub](https://github.com/apache/storm), insbesondere:
    -   [StatefulBoltExecutor.java](https://github.com/apache/storm/blob/master/storm-core/src/jvm/org/apache/storm/topology/StatefulBoltExecutor.java)
    -   [RedisKeyValueState.java](https://github.com/apache/storm/blob/master/external/storm-redis/src/main/java/org/apache/storm/redis/state/RedisKeyValueState.java)