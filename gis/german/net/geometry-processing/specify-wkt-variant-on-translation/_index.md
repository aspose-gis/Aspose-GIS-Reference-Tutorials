---
title: Geben Sie die WKT-Variante für die Übersetzung mit Aspose.GIS an
linktitle: Geben Sie die WKT-Variante bei der Übersetzung an
second_title: Aspose.GIS .NET-API
description: Erfahren Sie, wie Sie WKT-Varianten in Aspose.GIS für .NET angeben, um das Format und die Genauigkeit der räumlichen Datendarstellung effektiv zu steuern.
type: docs
weight: 19
url: /de/net/geometry-processing/specify-wkt-variant-on-translation/
---
## Einführung
Aspose.GIS für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, mühelos mit Daten von geografischen Informationssystemen (GIS) in ihren .NET-Anwendungen zu arbeiten. Eine der wesentlichen Funktionen von Aspose.GIS ist die Möglichkeit, während der Übersetzung die Variante „Well-Known Text“ (WKT) anzugeben, sodass Benutzer das Format und die Genauigkeit räumlicher Datendarstellungen steuern können. In diesem Tutorial erfahren Sie Schritt für Schritt, wie Sie WKT-Varianten mit Aspose.GIS für .NET angeben.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Aspose.GIS für .NET: Laden Sie Aspose.GIS für .NET von herunter und installieren Sie es[Download-Seite](https://releases.aspose.com/gis/net/).
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine .NET-Entwicklungsumgebung eingerichtet haben.
3. Grundkenntnisse: Vertrautheit mit der Programmiersprache C# und dem .NET Framework.

## Namespaces importieren
Bevor Sie die Aspose.GIS-Funktionalität in Ihrem Code verwenden, importieren Sie die erforderlichen Namespaces:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## Schritt 1: Erstellen Sie ein Punktobjekt
 Erstellen Sie zunächst eine`Point` Objekt mit Breitengrad, Längengrad und optionalen Maßwerten (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Schritt 2: Raumbezugssystem (SRS) festlegen
Weisen Sie dem Punktobjekt ein räumliches Bezugssystem (SRS) zu. In diesem Beispiel verwenden wir das räumliche Bezugssystem WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Schritt 3: WKT-Variante angeben
 Geben Sie nun die WKT-Variante für die Übersetzung an. Aspose.GIS unterstützt verschiedene WKT-Varianten, darunter`Iso`, `SimpleFeatureAccessOutdated` , Und`ExtendedPostGis`. Wählen Sie je nach Ihren Anforderungen die passende Variante:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // PUNKT M (23,5732, 25,3421, 40,3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // PUNKT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```
## Schritt 4: Steuern Sie das numerische Format
Sie können das numerische Format der Koordinaten in der WKT-Darstellung steuern. Aspose.GIS bietet Optionen zum Festlegen der Dezimalgenauigkeit:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // PUNKT M (23,5732 25,342099999999999 40,299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // PUNKT M (23,5732 25,3421 40,3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // PUNKT M (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // PUNKT M (23,573 25,342 40,3)
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man WKT-Varianten für die Übersetzung mit Aspose.GIS für .NET angibt. Durch Befolgen der oben beschriebenen Schritte können Entwickler das Format und die Präzision räumlicher Datendarstellungen in ihren .NET-Anwendungen effektiv steuern und so die Flexibilität und Benutzerfreundlichkeit geografischer Informationssysteme verbessern.
## FAQs
### Ist Aspose.GIS mit allen Versionen von .NET kompatibel?
Ja, Aspose.GIS unterstützt .NET Framework 4.0 und höher.
### Kann ich Aspose.GIS für kommerzielle Projekte verwenden?
Ja, Aspose.GIS kann sowohl für persönliche als auch für kommerzielle Projekte verwendet werden.
### Bietet Aspose.GIS Unterstützung für andere Geodatenformate?
Ja, Aspose.GIS unterstützt eine Vielzahl räumlicher Datenformate, einschließlich ESRI Shapefile, GeoJSON und KML.
### Gibt es eine kostenlose Testversion für Aspose.GIS?
 Ja, Sie können eine kostenlose Testversion von Aspose.GIS herunterladen[Hier](https://releases.aspose.com/).
### Wo erhalte ich Hilfe oder Support für Aspose.GIS?
 Sie können Ihre Fragen posten oder Hilfe von der Aspose.GIS-Community anfordern unter[Forum](https://forum.aspose.com/c/gis/33).