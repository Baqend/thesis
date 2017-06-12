---
layout: single
author_profile: true
comments: true
related: true
title: Declarative Offline-First Application Development under the Backend-as-a-Service
  Paradigm
tags: vergeben
---

**Geeignet für:** Masterarbeit

Backend-as-a-Service (BaaS) ist ein neues Paradigma zur Entwicklung von Apps und Webseiten, bei der ein BaaS-System Datenhaltung und Anwendungslogik als Cloud-Service bereitstellt. "Offline First" ist in der Frontend-Entwicklung ein zunehmend wichtiger Ansatz, um sicherzustellen, dass (Web-)Apps auch ohne bestehende Netzwerkanbindung weiter funktionieren (Beispiel: Gmail). Diese Lösungen sind üblicherweise hochgradig applikationsspezifisch, so dass bei jeder Neuentwicklung erneut der Aufwand zur Offline-Speicherung anfällt. In dieser Arbeit soll ein deklaratives Offline-First (DOF) Storage-Konzept für die JavaScript-API von Orestes konzipiert und implementiert werden.

### Ziele:

-   **Storage**: Transparente Speicherung von geladenen Objekten in geeignetem Storage Provider (LocalStorage, IndexedDB, WebSQL, etc.). Vergleich und Auswahl der Technologien.
-   **Queries**: lokale Anfrageverarbeitung als Fallback. Konkret: performante Implementierung von MongoDB-Queries auf lokalen Daten. Siehe z.B.: [Sift.js](https://github.com/crcn/sift.js/tree/master) und [MiniMongo](https://github.com/mWater/minimongo).
-   **Storage Policy & SLA**: Kontrolle des Offline-Verhaltens durch Policies, die festlegen in welchen Szenarien lokal gespeicherte Daten statt Backend-Daten angefragt werden und wann sie wieder verdrängt werden dürfen und wie sie aktualisiert werden. Idee:
    -   **DOF-Cache**: Speicherung erfolgt lazy wenn Objekt geladen
    -   **DOF-WorkingSet**: Definition von Offline Working Sets über Query, werden beim Seitenaufruf automatisch synchronisiert und optional im Hintergrund über WebSockets aktualisiert. Mögliche Vertiefung: 1) Unterstützung durch Bloomfilter 2) Containment Test: kann Query vollständig lokal ausgewertet werden.
    -   **DOF-Full**: alle (ggf. per-User-)Daten laden.
-   **Offline Updates**: Aktualisierung des lokalen Zustands, setzen von Dirty-Flags. Zu beachtende Fehler-Typen: App-Crashes und Netzwerkabbrüche.
-   **Synchronisation**: Eager (bei jedem Update & bestehender Verbindung), Zeitgesteuert (alle x Sekunden) mit Delay Tolerance und präferiertem Connection Typ (WLAN vs mobile).
-   **Konfliktauflösung**: Handler zur Konfliktauflösung bei nebenläufigen (d.h. konfliktierenden Updates).
-   **Evaluation**: 1) Fall-Studie zu gewähltem Use-Case (z.B. Kalender- oder Todo-Anwendung) 2) Verhaltens-Vergleich mit existierenden BaaS-Offline-APIs (z.B. [Parse](https://parse.com/) oder [Kinvey](http://www.kinvey.com/)), d.h. Untersuchung verschiedener Fehlerszenarien und Vergleich der erzielten Ergebnisse (z.B. Lost Updates).

### Einführungsliteratur:

-   [Backend-as-a-Service Einführung](http://www.heise.de/developer/artikel/Erste-Praxiserfahrungen-mit-Backend-as-a-Service-2440310.html)
-   [IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API/Basic_Concepts_Behind_IndexedDB)
-   [Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API)
-   [Orestes API](http://www.baqend.com/guide/)

### Vertiefungsliteratur:

-   [Reliable, consistent, and efficient data sync for mobile apps (Paper)](https://www.usenix.org/system/files/conference/fast15/fast15-paper-go.pdf)
-   [HTML 5 in Action, Kapitel 5](http://www.amazon.de/s/ref=nb_sb_noss_1?__mk_de_DE=%C5M%C5Z%D5%D1&url=search-alias%3Daps&field-keywords=indexeddb&x=0&y=0)
-   [Conflict-free Replicated Data Types (Datenstrukturen für automatische Konfliktauflösung)](https://hal.inria.fr/inria-00609399/document)
-   [Operational Transformation (Anderer Ansatz zur Konfliktauflösung aus dem Bereich Collaborative Editing)](https://en.wikipedia.org/wiki/Operational_transformation)