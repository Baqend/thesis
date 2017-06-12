---
title: Constraint-Checking in Distributed Database-as-a-Service Systems
layout: single
author_profile: true
comments: true
related: true
tags: Masterarbeit
---

**Geeignet für: ** Masterarbeit

In dieser Arbeit soll untersucht werden, welche Constraints auf Datenmodell-Ebene wichtig für ein Database/Backend-as-a-Service System sind und wie sie deklarativ umgesetzt werden können. Beispiele für derartige Constraints sind Wertebereiche (z.B. Datum zwischen x und y) oder Not-Null-Constraints. Diese Form der Datenmodell-gebundenen Verifizierung von Constraints hat den großen Vorteil, dass sie keiner zusätzlich zu wartenden Code-Basis bedarf und direkt im Frontend, z.B. bei der Formularvalidierung, genutzt werden kann.

## Ziele:

-   **Recherche: ** Aufstellen einer Matrix, die Datentypen zu sinnvollen Constraints in Relation setzt, d.h. für welchen Datentyp sind welche Validierungen sinnvoll? Als Grundlage können hier Content-Management-Systeme und SQL dienen. Systematische Unterteilung von Constraints nach ihren Anforderungen: benötigt nur neues Objekt (z.B. Range Constraints), benötigt Informationen über andere Objekte (z.B. Unique Constraint), benötigt vorherige Version des Objekts (z.B. monoton steigende Versionsnummern).
-   **Entwurf und Implementierung ** eines Constraint-Checkings in Orestes. Hier soll das bestehende Schema-System so angepasst werden, dass Constraints automatisch und skalierbar geprüft werden. Dazu soll die vorhandene Schema-Web-UI (siehe Baqend-Webseite) so angepasst werden, dass Constraints elegant deklariert werden können.
-   **Evaluation ** der Implementation durch Tests auf Erfüllung der Constraints und einer kleinen Case-Study (z.B. komplexes Formular mit Randbedingungen).

## Literatur:

-   [SQL Constraints](https://mariadb.com/kb/en/sql-99/20-sql-constraints-and-assertions/)
-   [Beispiel für Constraints in einem Content-Management-System](https://www.contentful.com/r/knowledgebase/validations/)
-   [Orestes/Baqend Schema Oberfläche](https://dashboard.baqend.com/register)
-   Literatur zu Orestes (siehe Einführung)