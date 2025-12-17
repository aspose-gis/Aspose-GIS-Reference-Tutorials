---
date: 2025-12-17
description: Erfahren Sie, wie Sie Multipolygon‑Geometrien in ASP.NET mit Aspose.GIS
  für .NET erstellen. Schritt‑für‑Schritt‑Anleitung, kostenlose Testversion und Lizenzinformationen.
linktitle: Create MultiPolygon Geometry
second_title: Aspose.GIS .NET API
title: Wie man Multipolygon‑Geometrie in ASP.NET mit Aspose.GIS erstellt
url: /de/net/geometry-creation/create-multipolygon-geometry/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MultiPolygon-Geometrie mit Aspose.GIS erstellen

## Einführung
Wenn Sie **create multipolygon geometry asp.net** erstellen müssen, bietet Aspose.GIS für .NET eine saubere, typensichere API, die auf jeder .NET‑Plattform funktioniert. In diesem Tutorial führen wir Sie durch den gesamten Prozess – von der Installation der Bibliothek bis zum Erstellen eines MultiPolygon‑Objekts, das Sie in Shapefile, GeoJSON oder ein anderes unterstütztes Format exportieren können. Egal, ob Sie einen Mapping‑Webservice oder ein Desktop‑GIS‑Tool entwickeln, das Beherrschen dieses Workflows spart Zeit und reduziert Fehler.

## Schnelle Antworten
- **Was kann ich damit bauen?** Jede GIS‑Anwendung, die komplexe polygonale Regionen benötigt, z. B. Flächennutzungs‑Karten oder Lieferzonen.  
- **Brauche ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine permanente Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Wie lange dauert das Schreiben des Codes?** Etwa 5‑10 Minuten für ein einfaches MultiPolygon.  
- **Kann ich das Ergebnis exportieren?** Ja – verwenden Sie die integrierten `Save`‑Methoden, um in Shapefile, GeoJSON usw. zu schreiben.

## Was ist eine MultiPolygon‑Geometrie?
Ein **MultiPolygon** ist eine Sammlung einzelner Polygone, die getrennt sein können oder Löcher enthalten. In der GIS‑Terminologie stellt es eine Menge räumlicher Features dar, die dasselbe Attribut teilen, aber geometrisch getrennt sind – ideal zur Darstellung von Ländern, die aus Inseln bestehen, oder von Parzellen mit mehreren Teilen.

## Warum Aspose.GIS für .NET verwenden?
- **Voll ausgestattete API** – Keine externen nativen Abhängigkeiten, reiner verwalteter Code.  
- **Plattformübergreifend** – Funktioniert unter Windows, Linux und macOS.  
- **Umfangreiche Formatunterstützung** – Lesen/Schreiben von Dutzenden Vektorformate sofort einsatzbereit.  
- **Leistungsoptimiert** – Verarbeitet große Datensätze mit geringem Speicherverbrauch.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Visual Studio 2022** (oder jede C#‑IDE) mit installiertem .NET 6 SDK.  
2. **Aspose.GIS for .NET**‑Paket – laden Sie es von der [Download‑Seite](https://releases.aspose.com/gis/net/) herunter und folgen Sie dem Installationsleitfaden in der Dokumentation.

## Namespaces importieren
Fügen Sie die erforderlichen `using`‑Direktiven zu Ihrem Projekt hinzu, damit der Compiler weiß, wo die GIS‑Typen definiert sind:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: LinearRinge erstellen
Ein **LinearRing** ist ein geschlossener `LineString`, der die äußere oder innere Grenze eines Polygons definiert. Hier erstellen wir zwei einfache Ringe:

```csharp
LinearRing firstRing = new LinearRing();
firstRing.AddPoint(8.5, -2.5);
firstRing.AddPoint(-8.5, 2.5);
firstRing.AddPoint(8.5, -2.5);
LinearRing secondRing = new LinearRing();
secondRing.AddPoint(7.6, -3.6);
secondRing.AddPoint(-9.6, 1.5);
secondRing.AddPoint(7.6, -3.6);
```

> **Profi‑Tipp:** Der erste und letzte Punkt müssen identisch sein, um den Ring zu schließen; Aspose.GIS schließt ihn automatisch, wenn Sie den letzten Punkt weglassen, aber eine explizite Angabe vermeidet Verwirrung.

## Schritt 2: Polygone erstellen
Jedes `Polygon` wird aus einem `LinearRing` erstellt. Sie können bei Bedarf später innere Ringe (Löcher) hinzufügen.

```csharp
Polygon firstPolygon = new Polygon(firstRing);
Polygon secondPolygon = new Polygon(secondRing);
```

## Schritt 3: MultiPolygon erstellen
Jetzt kombinieren wir die beiden Polygone zu einem einzigen `MultiPolygon`‑Objekt – das ist der genaue Schritt, der es Ihnen ermöglicht, **create multipolygon geometry asp.net** zu erstellen.

```csharp
MultiPolygon multiPolygon = new MultiPolygon();
multiPolygon.Add(firstPolygon);
multiPolygon.Add(secondPolygon);
```

Sie haben nun ein voll funktionsfähiges `MultiPolygon`, das Sie manipulieren, abfragen oder serialisieren können.

## Häufige Probleme & Lösungen
| Problem | Ursache | Lösung |
|---------|---------|--------|
| **Ring nicht geschlossen** | Fehlende Duplikation des ersten Punktes | Stellen Sie sicher, dass der erste und letzte Punkt identisch sind, oder rufen Sie `LinearRing.Close()` explizit auf. |
| **Falsche Koordinatenreihenfolge** | Breiten-/Längengrad vertauscht | Aspose.GIS erwartet **X = Längengrad**, **Y = Breitengrad**. Überprüfen Sie Ihre Datenquelle. |
| **Ausnahme bei `Add`** | Hinzufügen eines null‑Polygons | Stellen Sie sicher, dass jede `Polygon`‑Instanz erstellt wurde, bevor Sie sie zu `MultiPolygon` hinzufügen. |

## Fazit
Durch das Befolgen dieser Schritte haben Sie gelernt, wie man **create multipolygon geometry asp.net** mit Aspose.GIS für .NET erstellt. Diese Grundlage ermöglicht es Ihnen, reichhaltigere räumliche Modelle zu bauen, räumliche Abfragen durchzuführen und Daten in jedes unterstützte GIS‑Format zu exportieren. Als Nächstes können Sie Methoden wie `Contains`, `Intersects` oder `Transform` erkunden, um Ihrer Anwendung analytische Fähigkeiten hinzuzufügen.

## FAQ
### Ist Aspose.GIS für .NET für Anfänger geeignet?
Absolut! Aspose.GIS bietet umfassende Dokumentation und Tutorials, um Entwicklern aller Erfahrungsstufen den Einstieg zu erleichtern.

### Kann ich Aspose.GIS vor dem Kauf testen?
Ja, Sie können eine kostenlose Testversion von [hier](https://releases.aspose.com/) herunterladen, um die Funktionen vor dem Kauf zu testen.

### Wo finde ich Support für Aspose.GIS?
Sie können das Aspose.GIS‑Forum [hier](https://forum.aspose.com/c/gis/33) besuchen, um Fragen zu stellen und Unterstützung von der Community zu erhalten.

### Gibt es eine temporäre Lizenz für Aspose.GIS?
Ja, Sie können eine temporäre Lizenz von [hier](https://purchase.aspose.com/temporary-license/) für Evaluierungszwecke erhalten.

### Kann ich Aspose.GIS direkt kaufen?
Ja, Sie können Aspose.GIS über die Website [hier](https://purchase.aspose.com/buy) kaufen.

## Häufig gestellte Fragen
**F: Wie speichere ich das MultiPolygon in einer Datei?**  
A: Verwenden Sie die `Feature`‑Klasse, um die Geometrie zu kapseln, und rufen Sie `feature.Save("output.shp", Drivers.Shapefile);` auf.

**F: Kann ich einem Polygon innere Ringe (Löcher) hinzufügen?**  
A: Ja – erstellen Sie einen zweiten `LinearRing` und übergeben Sie ihn als zweites Argument an den `Polygon`‑Konstruktor.

**F: Ist es möglich, Koordinaten in ein anderes räumliches Referenzsystem zu transformieren?**  
A: Auf jeden Fall. Rufen Sie `multiPolygon.Transform(sourceCRS, targetCRS);` auf, wobei die CRS‑Objekte über EPSG‑Codes definiert werden.

---

**Zuletzt aktualisiert:** 2025-12-17  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}