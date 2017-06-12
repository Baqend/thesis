---
title: 'CacheWorker: Caching Arbitrary Resources without Staleness'
layout: single
author_profile: true
comments: true
related: true
tags: vergeben
---

**Geeignet für:** Masterarbeit oder Bachelorarbeit

Die Performance moderner Webseiten wird [durch die Netzwerklatenz](http://chimera.labs.oreilly.com/books/1230000000545/ch10.html#LATENCY_BOTTLENECK) bestimmt. Orestes ist entstanden, um für dieses Problem ein Lösung anzubieten. Kern der Technik ist die Nutzung von HTTP Web-Caching, das durch den Cache Sketch, einer Bloomfilter-basierten Datenstruktur, um starke Konsistenzgarantien erweitert wird. In dieser Arbeit soll das Konzept, das bisher für Datenbankobjekte besteht, auf beliebige Ressourcen (CSS, JavaScript, Bilder, HTML, ...) erweitert werden. Dieser neuartige Ansatz ist erstmals technisch möglich durch den Standardisierungsprozess neuer Browser-Schnittstellen zur Kontrolle des Ladevorgangs von Ressourcen.

### Ziele:

-   **Literaturrecherche**: Analyse der Unzulänglichkeit von AppCache und verwandten Ansätzen zum Caching beliebiger Ressourcen und Entwicklung von Offline-Web-Apps. Erläuterung von Service Workern und ihrer Verwendung für Caching auf Basis des Cache Sketches.
-   Problembeschreibung: Auswirkungen von [fehlendem Caching](https://docs.google.com/document/d/1N2VXqk9V9aA_-_uOG-ZelNRFFZ5xwsW_Th63ztTTik8/edit?usp=sharing) recherchieren und darstellen, sowie bisherige Lösungansätze (z.B. statische Ressourcen, [Content Hashes](https://github.com/jgallen23/grunt-hash), etc.) und die Probleme/Herausforderungen vergleichen.
-   **Implementierung**: CacheWorker JavaScript Implementation durch Service Worker. Eingabe: Bloomfilter/CacheSketch und Ressource; Ausgabe: Cached Response oder HTTP Revalidation Request für angefragte Ressource.
-   **Evaluation**: Vergleich für ein typische Webseite gemäß [HTTP Archive](http://httparchive.org/interesting.php)(Anzahl Requests, Größe, etc.) zwischen CacheWorker und keinem Caching in Bezug auf Ladezeit und Datenverbrauch für verschiedene Cache-Hit-Raten. Spezielle Vergleiche für HTML gecacht vs ungecacht, Bilder, CSS, JavaScript und die Auswirkungen. Vergleich durch Umschreiben einer typischen Webseite und Laden mit CacheWorker (z.B. [Wikipedia Startseite](https://de.wikipedia.org/wiki/Wikipedia:Hauptseite) oder [langer Artikel](https://de.wikipedia.org/wiki/Deutschland)).

### Einführungsliteratur:

-   [Orestes API](http://www.baqend.com/guide/)
-   [Service Worker (zu benutzende Browser API)](http://www.html5rocks.com/en/tutorials/service-worker/introduction/?redirect_from_locale=de)
-   [Cache Sketch Paper, Kapitel 1 und 2.1](http://www.baqend.com/paper/btw-cache.pdf)
-   [Cache Sketch Präsentation](http://www.btw-2015.de/res/slides/Gessert-The_Cache_Sketch-165_slides.pdf)

### Vertiefungsliteratur:

-   [Application Cache](http://www.html5rocks.com/de/tutorials/appcache/beginner/)
-   [Service Worker Browser Support](https://jakearchibald.github.io/isserviceworkerready/index.html)
-   [RFC 7234 (HTTP Caching)](https://tools.ietf.org/html/rfc7234).
-   [Ilya Grigorik - High Performance Browser Networking](http://chimera.labs.oreilly.com/books/1230000000545/index.html)