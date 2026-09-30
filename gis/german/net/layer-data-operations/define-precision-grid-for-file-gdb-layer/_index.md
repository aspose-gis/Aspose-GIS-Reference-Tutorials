---
date: 2026-09-30
description: Erfahren Sie, wie Sie mit Aspose.GIS for .NET eine Geodatenbank erstellen
  und ein Präzisionsraster für einen File GDB layer festlegen, einschließlich des
  Hinzufügens von Features zu einem Layer und der Validierung des Koordinatenbereichs.
keywords:
- how to create geodatabase
- how to validate coordinates
- handle out of range
- configure coordinate grid
- validate coordinate range
lastmod: 2026-09-30
linktitle: Präzisionsraster für File GDB layer definieren
og_description: Erfahren Sie, wie Sie mit Aspose.GIS for .NET eine Geodatenbank erstellen
  und ein Präzisionsraster für einen File GDB layer festlegen, um genaue Koordinaten
  und out‑of‑range handling sicherzustellen.
og_image_alt: Developer guide showing how to create a geodatabase and configure a
  precision grid with Aspose.GIS
og_title: Wie man eine Geodatenbank erstellt und ein Präzisionsraster für einen File
  GDB layer festlegt
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create geodatabase and set a precision grid for a File
    GDB layer using Aspose.GIS for .NET, including adding features to a layer and
    validating coordinate range.
  headline: How to create geodatabase and set grid for File GDB layer
  type: TechArticle
- description: Learn how to create geodatabase and set a precision grid for a File
    GDB layer using Aspose.GIS for .NET, including adding features to a layer and
    validating coordinate range.
  name: How to create geodatabase and set grid for File GDB layer
  steps:
  - name: create a dataset
    text: '`Dataset` represents a file‑geodatabase container that holds one or more
      spatial layers.'
  - name: define precision grid options
    text: '`PrecisionGridOptions` specifies the origin, scale, and validation behavior
      for coordinates. *The `EnsureValidCoordinatesRange = true` flag tells Aspose.GIS
      to **validate coordinate range** for every feature you add.*'
  - name: create a layer with the grid
    text: '`FeatureLayer` is the object that stores vector features inside a dataset.'
  - name: add features to the layer
    text: '`Feature` represents a single geometric object (point, line, polygon) together
      with its attribute values.'
  - name: handle exceptions when adding out‑of‑range features
    text: '`FeatureException` is thrown when a geometry violates the defined grid
      limits.'
  - name: clean up
    text: The `using` statements automatically close and dispose of the dataset and
      layer, ensuring all resources are released.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports Shapefile, GeoJSON, KML, and many more formats—over
      30 in total.
    question: Can I use Aspose.GIS for .NET with other GIS file formats?
  - answer: Absolutely. The library works with .NET Framework, .NET Core, and .NET
      5/6+.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, the API includes methods for buffering, intersecting, and calculating
      distances.
    question: Can I perform spatial operations such as buffering or intersection?
  - answer: Yes, you can transform geometries between different spatial reference
      systems using the built‑in reprojection tools.
    question: Does Aspose.GIS provide coordinate transformation capabilities?
  - answer: Yes, you can download a free trial from the [website](https://releases.aspose.com/gis/net/).
    question: Is there a trial version available?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create geodatabase
- Aspose.GIS
- .NET GIS programming
- precision grid
title: Wie man eine Geodatenbank erstellt und ein Präzisionsraster für einen File
  GDB layer festlegt
url: /de/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Raster für File GDB-Layer in Aspose.GIS festlegt

## Einführung
In diesem Tutorial **erstellen Sie eine Geodatenbank**, fügen ein Layer hinzu und lernen, wie Sie für dieses File Geodatabase (GDB)-Layer mit Aspose.GIS für .NET ein **Präzisionsraster festlegen**. Das Definieren eines Präzisionsrasters ermöglicht es Ihnen, **Koordinatenbereiche zu validieren**, verhindert Out‑of‑Range‑Fehler und stellt sicher, dass jede **Add‑Features‑to‑Layer**‑Operation Daten exakt speichert. Sie erfahren, warum das wichtig ist, wie man ein **Koordinatenraster konfiguriert** und wie man **Out‑of‑Range‑Szenarien** elegant behandelt.

## Schnelle Antworten
- **Was bedeutet „Raster festlegen“?** Es definiert die Koordinatenpräzision und den gültigen Bereich für ein GIS‑Layer.  
- **Warum ein Präzisionsraster verwenden?** Es schützt Ihre Daten vor ungültigen Koordinaten und verbessert die Speichereffizienz.  
- **Welche Bibliothek bietet diese Funktion?** Aspose.GIS für .NET.  
- **Benötige ich eine Lizenz?** Eine Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich das mit .NET Core verwenden?** Ja, Aspose.GIS unterstützt .NET Framework und .NET Core.

## Was ist ein Präzisionsraster und warum es festlegen?
Ein Präzisionsraster ist ein Satz von Parametern (Ursprung, Maßstab usw.), die der GIS‑Engine mitteilen, wie Koordinatenwerte gerundet und gespeichert werden sollen. Durch die Konfiguration eines Rasters **validieren Sie automatisch den Koordinatenbereich**, und jeder Versuch, einen Punkt außerhalb des Rasters einzufügen, löst eine Ausnahme aus – wodurch Sie **Out‑of‑Range‑Szenarien** früh im Entwicklungsprozess behandeln können.

## Warum eine Geodatenbank mit einem Präzisionsraster erstellen?
Das Erstellen einer File‑Geodatenbank liefert Ihnen einen portablen, leistungsstarken Container für Vektordaten. Das Hinzufügen eines Präzisionsrasters bereits beim Erstellen stellt sicher, dass jedes gespeicherte Feature dieselben numerischen Grenzen einhält, verbessert die Indexierungsgeschwindigkeit und fängt ungültige Koordinaten ab, bevor sie den Datensatz beschädigen. Diese frühe Validierung reduziert nachträglichen Bereinigungsaufwand und gewährleistet konsistente Datenqualität im gesamten Projekt.

- **Konsistente Datenqualität** – jedes Feature respektiert dieselbe numerische Präzision.  
- **Schnellere Indexierung** – die Engine kann Koordinaten effizienter speichern.  
- **Frühe Fehlererkennung** – Out‑of‑Range‑Koordinaten werden abgefangen, bevor sie den Datensatz beschädigen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes installiert haben:

1. **Visual Studio** – jede aktuelle Version (Community, Professional oder Enterprise).  
2. **Aspose.GIS für .NET** – laden Sie es von der [Website](https://releases.aspose.com/gis/net/) herunter.  
3. **Grundkenntnisse in C#** – Sie sollten mit der Erstellung von .NET‑Konsolenprojekten vertraut sein.

## Häufige Anwendungsfälle
- **Felddatenerfassung**, bei der GPS‑Geräte Koordinaten leicht außerhalb des vorgesehenen Ausdehnungsbereichs erzeugen können.  
- **Datenmigration** von Altsystemen, die unterschiedliche Koordinatenpräzisionen verwendet haben.  
- **Automatisierte ETL‑Pipelines**, die räumliche Integrität durchsetzen müssen, bevor Daten in eine GIS‑Datenbank geladen werden.

## Namespaces importieren
Die erforderlichen Aspose.GIS‑Namespaces stellen die Klassen für die Arbeit mit Datasets, Layers und Geometrien bereit.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Wie man das Koordinatenraster in einem File GDB-Layer konfiguriert
In diesem Abschnitt gehen wir den kompletten Prozess durch: Erstellen eines Datasets, Definieren eines Präzisionsrasters, Hinzufügen eines Layers, Einfügen von Features und Behandeln etwaiger Fehler. Die Schritte werden mit knappen Code‑Snippets illustriert, und jeder Schritt enthält eine kurze Erklärung, warum die Operation für die Aufrechterhaltung räumlicher Integrität notwendig ist.

### Schritt 1: Dataset erstellen
`Dataset` repräsentiert einen File‑Geodatabase‑Container, der einen oder mehrere räumliche Layers enthält.  

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Schritt 2: Präzisionsraster‑Optionen definieren
`PrecisionGridOptions` gibt Ursprung, Maßstab und Validierungsverhalten für Koordinaten an.  

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*Das Flag `EnsureValidCoordinatesRange = true` weist Aspose.GIS an, **den Koordinatenbereich** für jedes hinzugefügte Feature zu **validieren**.*

### Schritt 3: Layer mit dem Raster erstellen
`FeatureLayer` ist das Objekt, das Vektor‑Features innerhalb eines Datasets speichert.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Schritt 4: Features zum Layer hinzufügen
`Feature` repräsentiert ein einzelnes geometrisches Objekt (Punkt, Linie, Polygon) zusammen mit seinen Attributwerten.  

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Schritt 5: Ausnahmen beim Hinzufügen von Out‑of‑Range‑Features behandeln
`FeatureException` wird ausgelöst, wenn eine Geometrie die definierten Rastergrenzen verletzt.  

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### Schritt 6: Aufräumen
Die `using`‑Anweisungen schließen und entsorgen das Dataset und den Layer automatisch, sodass alle Ressourcen freigegeben werden.

## Warum ein Präzisionsraster konfigurieren?
Aspose.GIS unterstützt **über 30 GIS‑Dateiformate** und kann **Datensätze mit mehreren hundert Seiten** verarbeiten, ohne die gesamte Datei in den Speicher zu laden. Die Verwendung eines Präzisionsrasters reduziert die Speichergröße um bis zu **15 %** und verkürzt die Indexierungszeit um etwa **20 %**, weil Koordinaten in einer normalisierten, gerundeten Form gespeichert werden.

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| **Exception: “X value … is out of valid range.”** | Koordinaten liegen außerhalb des Präzisionsrasters. | Passen Sie `XOrigin`, `YOrigin` oder `XYScale` an, um Ihre Daten abzudecken, oder stellen Sie sicher, dass Eingabedaten innerhalb des definierten Bereichs liegen. |
| **Features werden im GIS‑Viewer nicht angezeigt** | Layer nicht gespeichert oder falsches räumliches Referenzsystem. | Vergewissern Sie sich, dass `SpatialReferenceSystem.Wgs84` mit dem CRS des Viewers übereinstimmt und dass `Dataset.Create` erfolgreich war. |
| **M‑Werte werden ignoriert** | `MScale` ist auf 0 oder zu niedrig gesetzt. | Setzen Sie einen angemessenen `MScale` (z. B. `1e4`), um Messwerte zu speichern. |

## Tipps zur Fehlerbehebung
- **Überprüfen Sie die Rasterausdehnungen** bevor Sie große Datenmengen laden; ein kleiner Tippfehler in `XOrigin` kann viele Zeilen ablehnen.  
- **Protokollieren Sie die Ausnahme‑Nachricht** (wie im Try‑Catch‑Block gezeigt) in eine Datei, wenn Sie automatisierte Importe verarbeiten; das erleichtert das Erkennen von Mustern bei Out‑of‑Range‑Daten.  
- **Verwenden Sie `EnsureValidCoordinatesRange = false` nur für vertrauenswürdige Datenquellen** – das Deaktivieren der Validierung kann zu beschädigten Geometrien führen.

## Häufig gestellte Fragen

**F: Kann ich Aspose.GIS für .NET mit anderen GIS‑Dateiformaten verwenden?**  
A: Ja, Aspose.GIS unterstützt Shapefile, GeoJSON, KML und viele weitere Formate – insgesamt über 30.

**F: Ist Aspose.GIS für .NET mit .NET Core kompatibel?**  
A: Absolut. Die Bibliothek funktioniert mit .NET Framework, .NET Core und .NET 5/6+.

**F: Kann ich räumliche Operationen wie Buffering oder Intersection durchführen?**  
A: Ja, die API enthält Methoden für Buffering, Schnittmengen und Distanzberechnungen.

**F: Bietet Aspose.GIS Koordinatentransformations‑Funktionen?**  
A: Ja, Sie können Geometrien zwischen verschiedenen räumlichen Referenzsystemen mit den integrierten Reprojektionstools transformieren.

**F: Gibt es eine Testversion?**  
A: Ja, Sie können eine kostenlose Testversion von der [Website](https://releases.aspose.com/gis/net/) herunterladen.

---

**Zuletzt aktualisiert:** 2026-09-30  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man ein GDB‑Dataset mit Aspose.GIS für .NET erstellt](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Wie man mit Aspose.GIS einem File‑GDB‑Dataset mit räumlicher Referenz WGS84 einen Layer hinzufügt](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)
- [Wie man ein GDB‑Dataset erstellt und Toleranzen für einen Layer festlegt](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}