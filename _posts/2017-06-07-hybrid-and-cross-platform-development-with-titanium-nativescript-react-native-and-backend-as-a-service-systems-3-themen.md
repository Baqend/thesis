---
title: Hybrid and Cross-Platform Development with Titanium/NativeScript/React Native
  and Backend-as-a-Service Systems (3 Themen)
layout: single
author_profile: true
comments: true
related: true
tags: Masterarbeit Bachelorarbeit
---

**Geeignet für: ** Bachelorarbeit oder Masterarbeit

**Offen**: Titanium, NativeScript

Cross-Platform Appentwicklungs-Frameworks haben das Ziel, die Entwicklung nativer mobiler Apps durch Betriebssystem-übergreifende Schnittstellen zu vereinfachen. In dieser Arbeit soll untersucht werden, wie durch das Backend-as-a-Service Paradigma (am Beispiel Orestes) in Kombination mit Cross-Platform-Frameworks darüber hinaus die Backend-Entwicklung standardisiert und vereinfacht werden kann. Dazu soll eine Integration der Orestes REST bzw. JavaScript API in das jeweilige Framework erfolgen, um eine direkte Ansteuerung von Datenspeicherung, File-Management, User-Authentifizierung etc. zu ermöglichen.

### Ziele:

-   **Recherche** der Funktionsweise des jeweiligen Cross-Plattform-Frameworks: kann dort nativ JavaScript ausgeführt werden und ggf. mit welchen Einschränkungen? Wie lässt sich die HTTP/REST Kommunikation realisieren? Welche Abstraktionen zur lokalen Speicherung stehen zur Verfügung?
-   **Entwurf und Implementierung** eines Orestes-SDKs für die jeweilige Plattform. Minimalumfang: CRUD-Operationen & Queries, Login und Registrierung, Ausführen von Backend-Code. Sammeln der Ergebnisse in einem SDK-Shim-Layer für die Zielplattform, mit dem das JavaScript-SDK von Orestes auf der Plattform läuffähig wird.
-   **Evaluation** der Implementation durch eine prototypische App, die das SDK verwendet.

### Literatur:

-   [NativeScript](https://www.nativescript.org/)
-   [Appcelerator Titanium](http://docs.appcelerator.com/platform/latest/#!/guide/Appcelerator_Platform)
-   [React Native](https://facebook.github.io/react-native/)
-   [Orestes JS Guide](http://www.baqend.com/js-sdk/latest/baqend.html)
-   [Orestes JS API](http://www.baqend.com/guide/)