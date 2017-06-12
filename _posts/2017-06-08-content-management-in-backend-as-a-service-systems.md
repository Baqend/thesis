---
title: Content Management for Serverless Architectures
layout: single
author_profile: true
comments: true
related: true
author: Felix
tags: Masterarbeit Bachelorarbeit
---

**Geeignet für: ** Bachelorarbeit oder Masterarbeit

In dieser Arbeit soll untersucht werden, wie Content-Management Funktionen in Backend-as-a-Service (BaaS) Systemen implementiert werden können. Bisher treten beide Paradigmen getrennt auf: BaaS als wichtiger Ansatz für *Serverless Architectures* verspricht durch potente Standard-APIs für Daten und Anwendungslogik die Entwicklung von Webseiten und Apps zu vereinfachen, während Content Management Systeme (CMS) integraler Bestandteil vieler Webplattformen sind, um Autoren und Redakteruren eine möglichste einfache Gestaltung von Inhalten zu ermöglichen. Diese Arbeit soll untersuchen, wie sich Content Mangement in der BaaS-Plattform  Orestes umsetzen lässt, um die Vorteile beider Ansätze zu vereinen.

## Ziele:

-   **Recherche: ** Welche Funktionen benötigt ein modernes CMS: Autoren-UI, Audit-Trail mit Versionshistorie, verschiedene Zustände von Artikeln (Draft, Public)? Wie funktioniert die Datenmodellierung in Orestes/Baqend? Kann ein bestehendes Headless CMS (z.B. Netlify CMS) oder ein Static Site Generator (Jekyll) sinnvoll adaptiert werden?
-   **Entwurf und Implementierung ** von Content Management in Orestes: neue Autoren-Dashboard-Oberfläche zum Editieren und Prüfen von Content. Erweiterung der Datenmodellierung um Abstraktionen für Content-Management (welche Felder können geändert werden, wie werden sie dargestellt, Constraints, etc.).
-   **Evaluation ** der Implementation durch die Realisierung eines Blogs oder einer News-Webseite als Case Study. Vergleich der Funktionalität mit verbreiteten CMS. Performance-Analyse z.B. gegenüber Wordpress oder Drupal.

## Literatur:
-  Übersicht [Headless CMS Systeme](https://headlesscms.org/)
-  Übersicht [ Static Site Generators](https://www.staticgen.com/)
-  [Serverless Paradigma ](https://martinfowler.com/articles/serverless.html)
-   [Baqend als Backend-as-a-Service System (Orestes-basiert) ](http://www.baqend.com/)
-   [Contenful als Beispiel für ein modernes CMS](https://www.contentful.com/)
-   Literatur zu Orestes (siehe Einführung)