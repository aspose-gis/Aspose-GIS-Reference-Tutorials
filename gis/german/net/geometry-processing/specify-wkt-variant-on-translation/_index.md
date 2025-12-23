---
date: 2025-12-23
description: Erfahren Sie, wie Sie Geometrien mit verschiedenen Optionen in WKT konvertieren,
  das Zahlenformat festlegen und die Dezimalgenauigkeit mit Aspose.GIS für .NET anpassen.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Geometrie in WKT‑Variantenoptionen konvertieren mit Aspose.GIS
url: /de/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Geometrie in WKT-Variantenoptionen konvertieren mit Aspose.GIS

## Einleitung
In modernen .NET-Anwendungen ist **die Konvertierung von Geometrie zu WKT** ein gängiger Schritt, wenn Sie räumliche Daten mit anderen Systemen austauschen oder in einem textbasierten Format speichern müssen. Aspose.GIS für .NET macht diese Konvertierung mühelos und gibt Ihnen die volle Kontrolle über die WKT-Variante, das Zahlenformat und die Dezimalgenauigkeit. In diesem Tutorial lernen Sie, wie Sie Geometrie in WKT konvertieren, die richtige Variante auswählen und die Ausgabe feinabstimmen, um die genauen Anforderungen Ihres Projekts zu erfüllen.

## Schnelle Antworten
- **Was bedeutet “convert geometry to WKT”?** Es wandelt geometrische Objekte (Punkte, Linien, Polygone) in die Well‑Known Text-Darstellung um.  
- **Welche WKT-Varianten werden unterstützt?** `Iso`, `SimpleFeatureAccessOutdated` und `ExtendedPostGis`.  
- **Wie kann ich die Dezimalgenauigkeit steuern?** Verwenden Sie die `NumericFormat`‑Optionen wie `General`, `RoundTrip` oder `Flat`.  
- **Benötige ich eine Lizenz für die Produktion?** Ja, für die Nutzung außerhalb der Testphase ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET-Versionen sind kompatibel?** .NET Framework 4.0+ und .NET 5/6/7.

## Was bedeutet “convert geometry to WKT”?
Die Konvertierung von Geometrie zu WKT erzeugt einen menschenlesbaren String, der räumliche Objekte beschreibt. Dieses Format wird von GIS‑Tools, Datenbanken und Web‑Services weitgehend akzeptiert und ist ideal für den Datenaustausch.

## Warum Aspose.GIS für diese Konvertierung verwenden?
- **Präzisionskontrolle** – Wählen Sie, wie viele Dezimalstellen ausgegeben werden.  
- **Variantenflexibilität** – Passen Sie den genauen WKT‑Dialekt an, der von Ihrem nachgelagerten System benötigt wird.  
- **Keine externen Abhängigkeiten** – Reine .NET‑Bibliothek, keine nativen Binärdateien.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.GIS für .NET** – Laden Sie es von der [Download-Seite](https://releases.aspose.com/gis/net/) herunter und installieren Sie es.  
2. **Entwicklungsumgebung** – Jede aktuelle Version von Visual Studio oder VS Code mit .NET SDK.  
3. **Grundkenntnisse in C#** – Vertrautheit mit Klassen, Objekten und dem .NET‑Framework.

## Namespaces importieren
Zuerst bringen Sie die erforderlichen Namespaces in den Gültigkeitsbereich:

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

## Schritt 1: Ein Point‑Objekt erstellen
Erstellen Sie ein `Point`, das Sie später **in WKT konvertieren**. Der Punkt enthält Breiten- und Längengrad sowie einen optionalen Maßwert (M):

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Schritt 2: Spatial Reference System (SRS) festlegen
Weisen Sie ein räumliches Referenzsystem zu, damit die WKT‑Ausgabe weiß, auf welches Koordinatensystem verwiesen wird. Hier verwenden wir das gängige WGS84‑System:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Schritt 3: WKT‑Variante angeben
Wählen Sie die passende WKT‑Variante, wenn Sie **Geometrie in WKT konvertieren**. Jede Variante formatiert die Ausgabe leicht unterschiedlich:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Schritt 4: Numerisches Format steuern (Numerisches Format festlegen & Dezimalgenauigkeit anpassen)
Feinabstimmung der numerischen Darstellung von Koordinaten. Die Klasse `NumericFormat` ermöglicht es Ihnen, **das numerische Format festzulegen** und **die Dezimalgenauigkeit anzupassen**, um Ihren Anforderungen gerecht zu werden:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Häufige Probleme & Tipps
- **Fehlender M‑Wert** – Wenn Sie kein Maß benötigen, lassen Sie die `M`‑Eigenschaft weg; die ISO‑Variante entfernt sie automatisch.  
- **Unerwartete Präzision** – Überprüfen Sie, ob Sie das richtige `NumericFormat` verwenden; `General` bewahrt die volle Double‑Präzision, während `Flat` auf die angegebene Anzahl von Dezimalstellen rundet.  
- **SRID wird nicht angezeigt** – Nur die `ExtendedPostGis`‑Variante fügt dem Output das Präfix `SRID=` hinzu. Wählen Sie diese Variante, wenn Ihr Zielsystem eine SRID erwartet.

## Fazit
Durch das Befolgen dieser Schritte wissen Sie jetzt, wie Sie **Geometrie in WKT konvertieren**, die richtige Variante auswählen und die numerische Ausgabe präzise steuern. Das gibt Ihnen die Flexibilität, Aspose.GIS in jeden GIS‑Workflow, jede Datenbank oder jeden Web‑Service zu integrieren, der WKT verarbeitet.

## FAQ's
### Ist Aspose.GIS mit allen Versionen von .NET kompatibel?
Ja, Aspose.GIS unterstützt .NET Framework 4.0 und höher.  

### Kann ich Aspose.GIS für kommerzielle Projekte verwenden?
Ja, Aspose.GIS kann sowohl für private als auch für kommerzielle Projekte verwendet werden.  

### Bietet Aspose.GIS Unterstützung für andere räumliche Datenformate?
Ja, Aspose.GIS unterstützt eine breite Palette von räumlichen Datenformaten, einschließlich ESRI Shapefile, GeoJSON und KML.  

### Gibt es eine kostenlose Testversion von Aspose.GIS?
Ja, Sie können eine kostenlose Testversion von Aspose.GIS von [hier](https://releases.aspose.com/) herunterladen.  

### Wo kann ich Hilfe oder Support für Aspose.GIS erhalten?
Sie können Ihre Fragen im Aspose.GIS‑Community‑Forum unter [forum](https://forum.aspose.com/c/gis/33) stellen.

## Häufig gestellte Fragen
**Q: Wie exportiere ich eine Geometry‑Collection zu einem einzigen WKT‑String?**  
A: Durchlaufen Sie jede Geometrie in der Collection und verketten Sie deren `AsText`‑Ergebnisse, optional getrennt durch Kommata oder Zeilenumbrüche.

**Q: Kann ich die SRID ändern, ohne die Koordinaten zu verändern?**  
A: Ja, setzen Sie die Eigenschaft `SpatialReferenceSystem` auf die gewünschte SRID; die Koordinatenwerte bleiben unverändert.

**Q: Was passiert, wenn ich eine nicht unterstützte WKT‑Variante verwende?**  
A: Aspose.GIS wirft eine `ArgumentException`. Validieren Sie stets die Variante gegen die `WktVariant`‑Enum‑Werte.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}