---
date: 2026-05-31
description: Erfahren Sie, wie Sie GeoJSON erstellen, GeoJSON-Optionen konfigurieren
  und ein Feature zu einem Layer hinzufügen, indem Sie Aspose.GIS für .NET verwenden.
  Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Linearisationstoleranz festlegen
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Erstellen von GeoJSON mit Toleranz in Aspose.GIS für .NET
url: /de/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man GeoJSON mit Toleranz in Aspose.GIS für .NET erstellt

## Einführung
Wenn Sie **erfahren möchten, wie man GeoJSON**-Dateien erstellt, die Kurvenpräzision steuert und das Ergebnis als sofort einsetzbares Dokument exportiert, macht Aspose.GIS für .NET das unkompliziert. In diesem Tutorial erfahren Sie, wie Sie GeoJSON-Optionen konfigurieren, die Linearisationstoleranz festlegen und **add feature to layer**-Objekten hinzufügen, während der Code sauber und produktionsreif bleibt.

## Schnelle Antworten
- **Was bedeutet „create vector layer“?** Es erstellt ein neues GIS-Vektor-Dataset (z. B. eine GeoJSON-Datei), das Geometrien und Attribute speichern kann.  
- **Wie setze ich die Linearisationstoleranz?** Setzen Sie die Eigenschaft `LinearizationTolerance` in einer `GeoJsonOptions`-Instanz, bevor Sie den Layer erstellen.  
- **Kann ich eine GeoJSON-Datei direkt exportieren?** Ja – verwenden Sie `VectorLayer.Create` mit dem Treiber `Drivers.GeoJson` und den konfigurierten Optionen.  
- **Brauche ich eine Lizenz?** Eine gültige Aspose.GIS-Lizenz schaltet alle Funktionen frei; ein temporärer Evaluierungsschlüssel funktioniert für Tests.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was bedeutet „create vector layer“?
Ein Vektor-Layer zu erstellen bedeutet, einen neuen GIS-Container (wie eine GeoJSON-Datei) zu initialisieren, der Punkte, Linien, Polygone und zugehörige Attributdaten speichern kann. Dieser Layer wird zum Ziel für jede von Ihnen erstellte Geometrie und alle angehängten Attribute.

## Warum GeoJSON-Optionen konfigurieren?
Das Konfigurieren von GeoJSON-Optionen – insbesondere der **linearization tolerance** – stellt sicher, dass gekrümmte Geometrien (z. B. `CircularString`) mit einer Präzision approximiert werden, die den Genauigkeitsanforderungen Ihrer Anwendung entspricht. Eine korrekte Konfiguration reduziert die Dateigröße, während die visuelle Treue erhalten bleibt, was entscheidend ist, wenn das GeoJSON von Webkarten oder räumlichen Analysetools verwendet wird.

## Voraussetzungen
1. **Visual Studio** (jede aktuelle Version).  
2. **Aspose.GIS-Lizenz** (oder ein temporärer Evaluierungsschlüssel).  
3. **Aspose.GIS for .NET**-Bibliothek, die in Ihrem Projekt referenziert ist.  
4. Grundlegende Kenntnisse in **C#**.

## Namespaces importieren
Zuerst importieren Sie die erforderlichen Namespaces, damit der Compiler weiß, wo die GIS-Klassen zu finden sind:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: GeoJSON-Optionen konfigurieren (wie man die Toleranz festlegt)
`GeoJsonOptions` gibt die Serialisierungseinstellungen an, die beim Schreiben von GeoJSON-Dateien verwendet werden.  
`GeoJsonOptions` definiert, wie Aspose.GIS GeoJSON serialisiert, einschließlich Linearisationstoleranz, Koordinatenpräzision und anderer Ausgabeeinstellungen.  
Wir werden ein `GeoJsonOptions`‑Objekt erstellen und Aspose.GIS mitteilen, wie nahe die linearisierten Geometrien an die ursprüngliche Kurve herankommen müssen.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Schritt 2: Ausgabepfad festlegen (wie man GeoJSON exportiert)
Geben Sie den vollständigen Dateipfad an, an dem das resultierende GeoJSON gespeichert werden soll. Stellen Sie sicher, dass der Ordner existiert und die Anwendung Schreibrechte hat.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Schritt 3: **Create Vector Layer** mit den konfigurierten Optionen
Die Klasse `VectorLayer` stellt einen GIS-Container dar, der räumliche Daten lesen und schreiben kann.  
`Drivers.GeoJson` ist der Treiberbezeichner zum Schreiben von GeoJSON-Dateien.  
Die Verwendung von `VectorLayer.Create` zusammen mit dem Treiber `Drivers.GeoJson` und den zuvor konfigurierten `GeoJsonOptions` erzeugt eine neue GeoJSON-Datei, die bereit für das Einfügen von Features ist.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Schritt 4: Geometrie konstruieren (z. B. einen CircularString)
`CircularString` ist eine gekrümmte Liniengeometrie, die Aspose.GIS basierend auf der von Ihnen festgelegten Toleranz linearisiert. Sie können dies durch jede gültige WKT-Darstellung wie `POINT`, `LINESTRING` oder `POLYGON` ersetzen.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Schritt 5: **Add Feature to Layer** und speichern
`Feature` ist das Objekt, das eine Geometrie mit Attributdaten verknüpft. Nachdem Sie eine `Feature`‑Instanz erstellt haben, weisen Sie die Geometrie zu, fügen optional Attributwerte hinzu und rufen `layer.Add(feature)` auf, um sie zu speichern. Wenn der `using`‑Block endet, wird der Layer automatisch in die in `path` definierte Datei geschrieben.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Wenn der `using`‑Block endet, wird der Layer automatisch in die in `path` definierte Datei geschrieben und liefert Ihnen eine sofort einsetzbare GeoJSON-Datei.

## Häufige Probleme & Tipps
- **Falscher Pfad** – Stellen Sie sicher, dass das Verzeichnis existiert und Sie Schreibrechte haben.  
- **Toleranz zu niedrig** – Das Setzen von `LinearizationTolerance` auf einen sehr kleinen Wert kann die Dateigröße stark erhöhen; eine Toleranz von 0,001 balanciert in der Regel Präzision und Größe.  
- **Lizenzfehler** – Wenn Sie Lizenzwarnungen sehen, stellen Sie sicher, dass die Lizenzdatei vor allen Aspose.GIS-Aufrufen geladen wird.  
- **Hinweis zur Leistung** – Aspose.GIS unterstützt die Verarbeitung von Dateien bis zu 2 GB, ohne das gesamte Dokument in den Speicher zu laden, dank seiner Streaming-Architektur.

## Häufig gestellte Fragen

**Q: Ist Aspose.GIS für .NET mit anderen .NET-Frameworks kompatibel?**  
A: Ja, es funktioniert mit .NET Framework 4.5+, .NET Core 3.1+ und .NET 5/6/7.

**Q: Kann ich Aspose.GIS in kommerziellen Projekten verwenden?**  
A: Absolut. Eine kommerzielle Lizenz entfernt alle Evaluierungsbeschränkungen und bietet vollen technischen Support.

**Q: Unterstützt Aspose.GIS andere GIS-Formate neben GeoJSON?**  
A: Ja, es unterstützt über 30 Formate – einschließlich Shapefile, KML, GML und CSV – und ermöglicht nahtlose Konvertierungen zwischen ihnen.

**Q: Gibt es eine Testversion?**  
A: Sie können eine kostenlose 30‑tägige Testversion von der Aspose-Website herunterladen; sie enthält alle Funktionen.

**Q: Wo kann ich Support erhalten?**  
A: Nutzen Sie die Aspose-Foren, das dedizierte Support-Portal oder den Link „Contact Support“ im Produkt‑Dashboard.

## Fazit
Durch das Befolgen dieser Schritte wissen Sie jetzt **wie man GeoJSON erstellt**, die Linearisationstoleranz konfiguriert und **add feature to layer** für einen nahtlosen GeoJSON-Export verwendet. Erkunden Sie weitere Geometrietypen, die Handhabung von Attributen und Bulk‑Verarbeitungsszenarien, um Aspose.GIS in Ihren .NET-GIS-Projekten vollständig zu nutzen.

---

**Zuletzt aktualisiert:** 2026-05-31  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Wie man GeoJSON konvertiert – Aspose.GIS für .NET](/gis/net/geo-data-conversion/)
- [Vector Layer erstellen, Präzision begrenzen mit Aspose.GIS für .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Vector Layer in File GDB erstellen – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}