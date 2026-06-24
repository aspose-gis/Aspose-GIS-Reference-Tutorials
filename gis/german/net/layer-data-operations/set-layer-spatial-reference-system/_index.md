---
date: 2026-06-15
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET einen Vektorlayer erstellen
  und das räumliche Referenzsystem des Layers festlegen. Lernen Sie, wie man eine
  räumliche Referenz definiert, ein Punkt-Feature hinzufügt und den EPSG-Code abruft.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Räumliches Referenzsystem des Layers festlegen
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Vektorlayer erstellen und das räumliche Referenzsystem des Layers festlegen
url: /de/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektorlayer erstellen und räumliches Referenzsystem des Layers festlegen

## Einführung
Im weiten Feld der Geoinformationssysteme (GIS) zeichnet sich **Aspose.GIS für .NET** als robuste, leistungsstarke Bibliothek aus, die **mehr als 70** Vektor‑ und Rasterformate unterstützt und Dateien größer als **10 GB** verarbeiten kann, ohne den gesamten Datensatz in den Speicher zu laden. In diesem Tutorial werden Sie **einen Vektorlayer erstellen**, seine räumliche Referenz definieren, **ein Punkt‑Feature hinzufügen** und den EPSG‑Code abrufen – alles mit klaren, schrittweisen Anleitungen. Egal, ob Sie einen Kartendienst, eine Datenkonvertierungspipeline oder eine räumliche Analyse‑Engine bauen, das Beherrschen dieser Grundlagen sorgt dafür, dass das Koordinatensystem Ihrer Shapefile genau bleibt und Ihr GIS‑Workflow zuverlässig ist.

## Schnelle Antworten
- **Was bedeutet „create vector layer“?** Es erstellt einen neuen GIS‑Layer (z. B. eine Shapefile), der Geometrien wie Punkte, Linien oder Polygone speichern kann.  
- **Welcher EPSG‑Code wird im Beispiel verwendet?** EPSG 26918 (NAD83 / UTM‑Zone 18N).  
- **Kann ich nach dem Erstellen des Layers ein Punkt‑Feature hinzufügen?** Ja – verwenden Sie `ConstructFeature()` und weisen Sie eine `Point`‑Geometrie zu.  
- **Wie rufe ich das CRS des Layers ab?** Lesen Sie `layer.SpatialReferenceSystem.EpsgCode` oder `.Name`.  
- **Benötige ich eine Lizenz für Aspose.GIS?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine Lizenz erforderlich.

## Was bedeutet „create vector layer“?
Der Vorgang **create vector layer** erstellt einen neuen Vektordatensatz (wie eine Shapefile), der geometrische Features und Attributdaten enthalten kann. In Aspose.GIS geschieht dies durch Instanziierung eines `VectorLayer`‑Objekts mit einem Treiber und einem räumlichen Referenzsystem.

## Warum das Koordinatensystem des Layers (CRS) korrekt setzen?
Das Festlegen des korrekten Koordinatenreferenzsystems (CRS) stellt sicher, dass jede gespeicherte Geometrie mit anderen räumlichen Datensätzen übereinstimmt. Mit Aspose.GIS können Sie das CRS mithilfe eines standardisierten EPSG‑Codes definieren, was die Interoperabilität mit GIS‑Software weltweit garantiert. Zum Beispiel definiert EPSG 26918 NAD83 / UTM‑Zone 18N, eine gängige Projektion für Daten im Osten der USA.

## Voraussetzungen
- .NET-Entwicklungserfahrung (C# oder VB.NET).  
- Visual Studio 2022 oder neuer.  
- Aspose.GIS für .NET Bibliothek – laden Sie sie **[hier](https://releases.aspose.com/gis/net/)** herunter.  
- Grundlegende Kenntnisse von räumlichen Referenzsystemen (CRS/EPSG).

## Namespaces importieren
Der Namespace `Aspose.Gis` stellt die Kern‑GIS‑Klassen bereit, während `Aspose.Gis.Geometries` Geometrietypen wie `Point` liefert.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Wie erstellt man einen Vektorlayer in Aspose.GIS für .NET?
VectorLayer repräsentiert einen Vektordatensatz wie eine Shapefile und bietet Methoden zum Erstellen, Lesen und Bearbeiten von Features.  
SpatialReferenceSystem definiert das Koordinatenreferenzsystem mittels eines EPSG‑Codes.

Laden Sie den Zielordner, definieren Sie ein EPSG‑kodiertes `SpatialReferenceSystem` und rufen Sie `VectorLayer.Create` mit dem Shapefile‑Treiber auf. Dieser einzelne Aufruf erstellt eine neue `.shp`‑Datei, schreibt die zugehörigen `.shx`‑ und `.dbf`‑Dateien und bettet die CRS‑Metadaten ein, sodass Features effizient eingefügt werden können.

### Schritt 1: Dokumentverzeichnis angeben
Beginnen Sie damit, den Pfad zu Ihrem Dokumentverzeichnis anzugeben. Dies wird der Ort sein, an dem Ihre räumlichen Datendateien gespeichert werden.

```csharp
string dataDir = "Your Document Directory";
```

### Schritt 2: Räumliche Referenz definieren und Shapefile‑Koordinatensystem festlegen
SpatialReferenceSystem repräsentiert das CRS eines Layers, identifiziert durch einen EPSG‑Code.

Definieren Sie den Pfad für die Shapefile und **definieren Sie die räumliche Referenz** mit dem EPSG‑Code (26918 in diesem Beispiel). Dieser Schritt **legt das Shapefile‑Koordinatensystem** für den Layer fest.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Wie kann man ein Punkt‑Feature zu einem Vektorlayer hinzufügen?
`Point` ist ein Geometrietyp, der ein einzelnes X/Y‑Koordinatenpaar darstellt.

Erstellen Sie ein neues Feature, weisen Sie ihm eine `Point`‑Geometrie mit den gewünschten X/Y‑Koordinaten zu und fügen Sie das Feature dem offenen `VectorLayer` hinzu. Der Vorgang schreibt die Geometrie in die `.shp`‑Datei und den Attributdatensatz in die `.dbf`‑Datei in einer einzigen Transaktion.

### Schritt 3: Vektorlayer erstellen
`ConstructFeature` erstellt ein neues Feature‑Objekt, das Geometrie‑ und Attributdaten enthalten kann.

Jetzt **erstellen Sie den Vektorlayer** mit dem angegebenen Shapefile‑Pfad, dem Treibertyp (Shapefile) und dem gerade definierten räumlichen Referenzsystem.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Schritt 4: Punkt‑Feature zum Layer hinzufügen
Erstellen Sie ein neues Feature und **fügen Sie ein Punkt‑Feature hinzu**, indem Sie seine Geometrie (ein `Point` mit den Koordinaten 60, 24) setzen. Dann fügen Sie das Feature dem Vektorlayer hinzu.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Schritt 5: Informationen zum räumlichen Referenzsystem abrufen (EPSG‑Code ermitteln)
Öffnen Sie den Vector Layer und rufen Sie Informationen zum räumlichen Referenzsystem ab, wie den EPSG‑Code und den lesbaren Namen. Dies zeigt, wie man **den EPSG‑Code ermittelt** und **das Layer‑CRS setzt**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| **Layer lässt sich nicht öffnen** | Falscher Treiber oder beschädigter Dateipfad | Überprüfen Sie `Drivers.Shapefile` und stellen Sie sicher, dass `path` auf eine vorhandene `.shp`‑Datei verweist. |
| **Falsches CRS angezeigt** | Verwendung des falschen EPSG‑Codes | Überprüfen Sie den EPSG‑Code anhand einer autoritativen Quelle (z. B. EPSG.io). |
| **Feature nicht gespeichert** | Aufruf von `layer.Add(feature)` fehlt im `using`‑Block | Stellen Sie sicher, dass die `Add`‑Methode ausgeführt wird, bevor der Layer freigegeben wird. |

## Häufig gestellte Fragen
**F:** Wie ändere ich das CRS einer bestehenden Shapefile?  
**A:** Öffnen Sie den Layer, erstellen Sie ein neues `SpatialReferenceSystem` mit dem gewünschten EPSG‑Code, weisen Sie es `layer.SpatialReferenceSystem` zu und speichern Sie anschließend den Layer.

**F:** Kann ich andere Geometrietypen (z. B. Polygone) mit demselben Ansatz hinzufügen?  
**A:** Ja – ersetzen Sie `new Point(x, y)` durch `new Polygon(...)` oder `new LineString(...)` nach Bedarf.

**F:** Ist es möglich, effizient mit großen Datensätzen zu arbeiten?  
**A:** Verwenden Sie Streaming‑APIs (`VectorLayer.Create` mit `FeatureCollection`) und geben Sie Layer zügig frei, um Ressourcen zu schonen.

**F:** Unterstützt Aspose.GIS Koordinatentransformationen?  
**A:** Ja – verwenden Sie `Geometry.Transform(targetSrs)`, um Geometrien zwischen verschiedenen räumlichen Referenzen zu reprojizieren.

**F:** Welche .NET‑Versionen werden unterstützt?  
**A:** Aspose.GIS funktioniert mit .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

---

**Zuletzt aktualisiert:** 2026-06-15  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Vektorlayer erstellen und Linearisationstoleranz festlegen mit Aspose.GIS für .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Vektorlayer in File GDB erstellen – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Räumliche Referenz wgs84 – Layer zu GDB hinzufügen mit Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}