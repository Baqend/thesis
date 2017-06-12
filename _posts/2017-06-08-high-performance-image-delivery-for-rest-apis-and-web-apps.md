---
title: High-Performance Image Delivery for REST APIs and Web Apps
layout: single
author_profile: true
comments: true
related: true
author: Felix
tags: Bachelorarbeit Masterarbeit
---

**Geeignet für**: Masterarbeit oder Bachelorarbeit

Orestes ist eine Backend-as-a-Service Plattform, das konsistentes Web Caching von REST APIs und Datenbankzugriffen ermöglicht, um Webseiten zu beschleunigen. In dieser Arbeit soll der Caching-Ansatz für die intelligente Auslieferung von Bilder erweitert werden. Ziel ist, daher CDN- und Browser-Caching von abgeleiteten Bildern zu ermöglichen, insbesondere:
- Verschiedene Größen eines Basisbilds
- Cropping, z.B. Ausschnitte eines Bildes um Gesichter herum
- Optimierte Formate, z.B. Google's WebP
- Kompression von Bildern, ähnlich beispielsweise [Tinypng](https://tinypng.com/)

### Ziele:
- **Recherche**: Analyse und Vergleich von Bild-Optimierungs-Frameworks. Feature-Matrix aufstellen und nichtfunktionale Merkmale vergleichen (z.B. Skalierbarkeit, Erweiterbarkeit). Analyse der wissenschaftlichen State-of-the-art: implementieren aktuelle Tools bereits die besten Verfahren?
- **Implementation**: Bereitstellend der Operationen über eine REST API
	- **CDN Caching**: Bei Änderungen eines Basisbilds müssen alle abgeleiteten Bilder invalidiert werden
	- **Browser Caching**: Über einen Bloomfilter wird im Client ermittelt, wann Bilder revalidiert werden müssen
	- **Responsive Images**: Durch welche Mechanismen können Web-Anwendungen bei der Einbindung von Responsive-Images in verschiedenen Größen und Formaten unterstützt werden
- **Evaluation**: Auswertung repräsentativer Seiten (z.B. der Alexa Top 500) - welches Verbesserung der Performance lässt sich durch einen Klong der Seite erzielen, der durchgend die mit dem erarbeiten Verfahren ausgeliferten, optimierten Bilder lädt. Metriken: 
	- genutztes Datenvolumen
	- Page Load Time (DomContentLoaded, Loaded)
	- Time-to-Interactive und [Speed Index](https://sites.google.com/a/webpagetest.org/docs/using-webpagetest/metrics/speed-index)


### Literatur
- [Caching Papers](/paper/) inbesondere der Bloomfilter-basierte Ansatz
- [Thumbor Library](https://github.com/thumbor/thumbor) (ermöglicht u.a. Croppping, Resizing)
- Prinzip der [Tag-basierten Invalidierung](https://www.fastly.com/blog/surrogate-keys-part-1/)
- [Image Optimization Tool Vergleich](https://github.com/JamieMason/image-optimisation-tools-comparison) und ein [weiter Vergleich für Beispielbilder](https://jamiemason.github.io/ImageOptim-CLI/)
- Kommerzielle Optimizer: 
	- [Kraken](https://kraken.io/)
	- [Imgix](https://www.imgix.com/ )
	- [Cloudinary](http://cloudinary.com/)
- [Interessanter Erfahrungsbericht von Yelp](https://engineeringblog.yelp.com/2017/06/making-photos-smaller.html)