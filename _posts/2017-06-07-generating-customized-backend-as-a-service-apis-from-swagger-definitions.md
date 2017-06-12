---
title: Generating Customized Backend-as-a-Service APIs from Swagger Definitions
layout: single
author_profile: true
comments: true
related: true
tags: Masterarbeit
---

**Geeignet für:** Masterarbeit

Swagger ist eine Interface Definition Language für REST APIs. Ziel dieser Arbeit ist, das Backend-as-a-Service-System Orestes über Schema-spezifische, von Swagger generierte SDKs anzusprechen. Dazu müssen die pro Tenant definierten Datenmodelle in Swagger-Beschreibungen transformiert werden. Dies hat den Vorteil, dass die anschließend generierten SDKs statische Typprüfung bei der Verwendung von Model-Klassen mithilfe des SDKs bietet.

### Ziele:

-   **Recherche: **wie lässt sich die Datenmodellierung in Orestes auf die Beschreibungssprache von Swagger abbilden? Welche Bedingungen müssen in der Swagger Spezifikation erfüllt sein, um voll funktionsfähige SDKs zu generieren?
-   **Entwurf und Implementierung** eines Spezifikationsgenerators, der als Input ein Orestes Datenmodell und die generische REST API erhält und daraus eine datenmodellspezifische Swagger-Spezifikation erzeugt. Die Generierung soll ferner so erweitert werden, dass auch Authenfizierunginformationen (eingeloggter User und seine Rollen) in Form von Tokens korrekt über die REST API übermittelt werden.
-   **Evaluation** der Implementation durch Entwicklung eine Case-Study in zwei generierten SDKs.

### Literatur:

-   Literatur zu Orestes (siehe Einführung)
-   [Interaktive Swagger-Dokumentation der Orestes REST API](https://dashboard.global.ssl.fastly.net/swagger-ui/?url=https%3A%2F%2Ftoodle-bq.global.ssl.fastly.net%2Fv1%2Fspec)
-   [Swagger](http://swagger.io/)
-   [Swagger SDK generation](https://github.com/swagger-api/swagger-codegen)