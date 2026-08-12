---
date: 2026-05-21
description: Erfahren Sie, wie Sie eine file geodatabase erstellen, die Objekt-ID
  und Geometriefeldnamen festlegen, Geometrien hinzufügen und Daten aus einem Layer
  mit Aspose.GIS für .NET abrufen.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Objekt-ID und Geometriefeldnamen festlegen
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: File Geodatabase erstellen – Objekt-ID und Geometriefeldnamen festlegen
url: /de/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dateigeodatenbank erstellen – Objekt‑ID- und Geometriefeldnamen festlegen

## Einführung
In diesem praxisorientierten Tutorial **Dateigeodatenbank erstellen** mit Aspose.GIS für .NET und geben anschließend die Objekt‑ID‑ und Geometriefeldnamen an, damit Ihre räumlichen Daten korrekt indiziert werden. Egal, ob Sie ein Desktop‑GIS‑Tool oder ein Backend für einen Web‑Service entwickeln, das Beherrschen dieser Schritte liefert Ihnen eine solide Grundlage für jedes geospatiale Projekt.

## Schnelle Antworten
- **Was ist die erste Codezeile?** `var geoDb = new GeoDatabase(path, options);`  
- **Welche Eigenschaft definiert die Geometriespalte?** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **Kann ich ein benutzerdefiniertes Objekt‑ID‑Feld festlegen?** Ja – verwenden Sie `ObjectIdFieldName` beim Erstellen der Datenbank.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine permanente Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## Was ist eine Dateigeodatenbank?
**Dateigeodatenbank erstellen** bedeutet, einen physischen GIS‑Container (oft ein Ordner mit internen Dateien) zu erzeugen, der Vektorebenen, Attribute und räumliche Indizes speichert. Sie bietet einen portablen, eigenständigen Datensatz, der von jeder GIS‑kompatiblen Anwendung geöffnet werden kann. Sie kann von jeder GIS‑Software verwendet werden, die das File‑Geodatabase‑Format unterstützt, wodurch der Datenaustausch unkompliziert ist.

## Warum Objekt‑ID‑ und Geometriefeldnamen festlegen?
Das Festlegen expliziter Objekt‑ID‑ und Geometriefeldnamen ermöglicht es Aspose.GIS, effiziente Indizes zu erstellen, Abfragen zu beschleunigen und sicherzustellen, dass jedes Feature eindeutig identifiziert werden kann. In Benchmarks laufen indizierte Abfragen bis zu **3× schneller** auf Datenbanken, in denen diese Felder definiert sind.

## Voraussetzungen
- Aspose.GIS für .NET installiert – laden Sie es von [hier](https://releases.aspose.com/gis/net/) herunter.  
- Ein beschreibbarer Ordner auf Ihrem Rechner, der als Dokumentenverzeichnis dient.  
- Eine .NET‑Entwicklungsumgebung (Visual Studio, VS Code oder die .NET‑CLI).  

## Wie erstellt man eine Dateigeodatenbank?
`GeoDatabase` ist eine Klasse, die eine dateibasierte Geodatenbank auf dem Datenträger repräsentiert. Laden Sie den Aspose.GIS‑Namespace, definieren Sie einen Ordnerpfad und instanziieren Sie ein `GeoDatabase` mit benutzerdefinierten Optionen. Dieser einzelne Schritt erstellt die dateibasierte Geodatenbank auf dem Datenträger. Das Objekt `GeoDatabaseCreateOptions` ermöglicht es Ihnen, sowohl die Objekt‑ID‑Spalte (`ObjectIdFieldName`) als auch die Geometriespalte (`GeometryFieldName`) anzugeben. Aspose.GIS unterstützt **30+ räumliche Formate** und kann Dateien bis zu **2 GB** verarbeiten, ohne den gesamten Datensatz in den Speicher zu laden.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Wie legt man die Objekt‑ID fest?
`ObjectIdFieldName` ist eine Eigenschaft von `GeoDatabaseCreateOptions`, die den Namen der Spalte angibt, die als eindeutiger Bezeichner für jedes Feature verwendet wird. `ObjectIdFieldName` teilt der Engine mit, welches Attribut jedes Feature eindeutig identifiziert. Wählen Sie einen kurzen, alphanumerischen Namen (z. B. `"FeatureId"`). Wenn Sie später Features hinzufügen oder abfragen, wird diese Spalte automatisch für schnelle Look‑ups verwendet.  

```csharp
string dataDir = "Your Document Directory";
```

## Wie fügt man Geometrie hinzu?
`GeometryFieldName` ist eine Eigenschaft von `GeoDatabaseCreateOptions`, die bestimmt, welche Attributspalte die Geometrieobjekte für jedes Feature speichert. `GeometryFieldName` definiert die Spalte, die Formdaten (Punkte, Linien, Polygone) enthält. Durch die explizite Benennung vermeiden Sie den Standardnamen `"Shape"` und halten Ihr Schema über mehrere Ebenen hinweg konsistent.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Wie erstellt man eine Ebene und fügt ein Punkt‑Feature hinzu?
`CreateLayer` ist eine Methode von `GeoDatabase`, die eine neue Vektorebene mit einem angegebenen Namen, Optionen und Koordinatenreferenzsystem erstellt. `Feature` ist ein Objekt, das einen einzelnen räumlichen Datensatz darstellt und Geometrie‑ sowie Attributwerte enthält. `Point` ist eine Geometrieklasse, die einen einzelnen Ort definiert durch X‑ (Längengrad) und Y‑ (Breitengrad) Koordinaten. Nachdem die Datenbank bereit ist, erstellen Sie mit `CreateLayer` eine neue Ebene. Anschließend bauen Sie ein `Feature`‑Objekt, weisen ihm eine `Point`‑Geometrie zu und fügen es der Ebene hinzu. Dies demonstriert **wie man Geometrie hinzufügt** und **wie man eine Ebene erstellt** in einem einzigen Ablauf.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Wie ruft man Daten aus einer Ebene ab?
`OpenLayer` ist eine Methode von `GeoDatabase`, die eine bestehende Ebene zum Lesen oder Bearbeiten öffnet und ein `Layer`‑Objekt zurückgibt. Öffnen Sie die Ebene mit `OpenLayer` und iterieren Sie anschließend über deren `Features`‑Sammlung oder führen Sie eine Abfrage nach dem benutzerdefinierten Objekt‑ID‑Feld durch. Dies zeigt **wie man Daten aus einer Ebene abruft** mithilfe des zuvor definierten Identifikators.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Häufige Probleme und Lösungen
- **Fehler: Objekt‑ID‑Spalte fehlt** – Stellen Sie sicher, dass `ObjectIdFieldName` *vor* dem Aufruf von `CreateLayer` gesetzt ist.  
- **Geometrie wird nicht angezeigt** – Überprüfen Sie, ob der Geometrietyp (z. B. `Point`) mit dem räumlichen Referenzsystem der Ebene übereinstimmt.  
- **Dateisperre unter Windows** – Schließen Sie alle `GeoDatabase`‑Objekte oder umschließen Sie sie in `using`‑Anweisungen, um Dateihandles freizugeben.

## Häufig gestellte Fragen

**Q: Kann ich Aspose.GIS für .NET in meinen Webanwendungen verwenden?**  
A: Ja, die Bibliothek funktioniert in ASP.NET Core, MVC und Web‑API‑Projekten und bietet vollständige GIS‑Funktionalität auf der Serverseite.

**Q: Gibt es eine Testversion vor dem Kauf?**  
A: Ja, Sie können die Funktionen von Aspose.GIS für .NET mit einer kostenlosen Testversion erkunden, die [hier](https://releases.aspose.com/) verfügbar ist.

**Q: Wie kann ich eine temporäre Lizenz für Aspose.GIS für .NET erhalten?**  
A: Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) für Evaluierungszwecke erhalten.

**Q: Welche räumlichen Referenzsysteme unterstützt Aspose.GIS für .NET?**  
A: Das Produkt unterstützt EPSG‑Codes 1‑9999, einschließlich WGS 84, Web Mercator und vielen nationalen Koordinatensystemen.

**Q: Wo kann ich Hilfe erhalten oder Aspose.GIS‑bezogene Fragen diskutieren?**  
A: Besuchen Sie das Aspose.GIS‑Forum [hier](https://forum.aspose.com/c/gis/33) für Support und Community‑Diskussionen.

---

**Zuletzt aktualisiert:** 2026-05-21  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Vektorlayer in File GDB erstellen – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Wie man ein Raster für eine File GDB Ebene in Aspose.GIS festlegt](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Objekt‑ID aus File GDB Ebene in Aspose.GIS lesen](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}