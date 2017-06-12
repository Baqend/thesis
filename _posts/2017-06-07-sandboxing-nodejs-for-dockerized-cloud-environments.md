---
layout: single
author_profile: true
comments: true
related: true
title: Sandboxing Node.js for Dockerized Cloud Environments
tags: vergeben
---

**Geeignet für:** Masterarbeit

In dieser Arbeit soll untersucht werden, wie ein Node.js Server, auf dem "untrusted" Application Code von Usern ausführt wird, effektiv einem Sandboxing unterzogen werden kann. Dabei wird davon ausgegangen, dass der Node.js Server in einer Cloud Umgebung beliebigen Code von Usern ausführt und einem Docker-Container isoliert ist. Das Saandboxing soll - soweit technisch umsetzbar - folgendes gewährleisten:

-   Limitierung der CPU-Ressourcen, kein Filesystem-Zugriff (durch Docker weitestgehend gegeben)
-   Limitierung von Netzwerk I/O (z.B. Aufrufe von REST-APIs)
-   Messung des erzeugten I/O Traffics (z.B. für Statistiken)
-   Limitierung der Ausführungzeit aufgerufener Funktionen, inklusive der dadurch aufgerfuenen Funktionen, auch asnychron (z.B. Durch Netzwerkommunikation, oder setTimeout)

### Ziele:

-   **Recherche** zu existrierenden Sanboxing Ansätzen für [Node](https://nodejs.org/en/)( [Node VM](https://nodejs.org/api/vm.html)) und den Sandboxing Möglichkeiten von [Docker](https://www.docker.com/)
-   **Entwurf und Implementierung** einer Sandboxing-Lösung für obige Anforderungen
-   **Evaluation** der Implementation und (quantitativer) Vergleich mit der Ausführung ohne Sandboxing/Node.js.

### Einführungsliteratur:

-   [Docker for Beginners](http://prakhar.me/docker-curriculum/)
-   [Node.js: Tutorial](https://www.airpair.com/javascript/node-js-tutorial)

### Vertiefungsliteratur:

-   [Docker Doku](https://docs.docker.com/)
[](https://docs.docker.com/)
-   [](https://docs.docker.com/)[Node.js Doku](https://nodejs.org/api/)
-   [Docker in Action](http://www.amazon.com/Docker-Action-Jeff-Nickoloff/dp/1633430235/ref=sr_1_1?s=books&ie=UTF8&qid=1464959732&sr=1-1&keywords=Docker)
-   [Practical Node.js](http://link.springer.com/book/10.1007/978-1-4302-6596-2)
-   [Course on Node.js](https://www.coursera.org/learn/server-side-development)