---
date: 2026-08-30
description: Erfahren Sie, wie Sie ein Shapefile mit Circular String Geometry mithilfe
  von Aspose.GIS für .NET erstellen. Die Schritt‑für‑Schritt‑Anleitung zeigt die Erstellung
  eines vector layer, das Hinzufügen von Geometry und den Export des Shapefiles.
keywords:
- how to create shapefile
- circular string geometry
- Aspose.GIS .NET
lastmod: 2026-08-30
linktitle: Circular String Geometry erstellen
og_description: Erfahren Sie, wie Sie ein Shapefile mit Circular String Geometry mithilfe
  von Aspose.GIS für .NET erstellen. Folgen Sie dem Schritt‑für‑Schritt‑Tutorial,
  um einen vector layer zu erstellen und ein Shapefile zu exportieren.
og_image_alt: 'Tutorial: create shapefile with circular string geometry using Aspose.GIS
  for .NET'
og_title: Wie man ein Shapefile mit Circular String in Aspose.GIS erstellt
schemas:
- author: Aspose
  dateModified: '2026-08-30'
  description: Learn how to create shapefile with circular string geometry using Aspose.GIS
    for .NET. Step-by-step guide shows vector layer creation, geometry addition, and
    Shapefile export.
  headline: How to create shapefile with circular string Aspose.GIS
  type: TechArticle
- description: Learn how to create shapefile with circular string geometry using Aspose.GIS
    for .NET. Step-by-step guide shows vector layer creation, geometry addition, and
    Shapefile export.
  name: How to create shapefile with circular string Aspose.GIS
  steps:
  - name: define the output file path
    text: Set the location where the Shapefile will be written. Replace `"Your Document
      Directory"` with the actual folder path on your system.
  - name: create vector layer
    text: Open a `VectorLayer` using the `Create` method. This is the core of the
      **create vector layer** operation.
  - name: construct a new feature
    text: A feature represents a single spatial record inside the layer.
  - name: build the circular string geometry
    text: Add the points that define the curved shape. The sequence of points creates
      an arc that starts and ends at the same location, forming a closed circular
      string.
  - name: assign geometry and add the feature to the layer
    text: Link the geometry to the feature and store it in the layer. When the `using`
      block ends, the layer is automatically flushed to the Shapefile on disk.
  type: HowTo
- questions:
  - answer: It creates a new container (layer) that can hold spatial features like
      points, lines, or polygons.
    question: What does “create vector layer” mean?
  - answer: '`CircularString` from `Aspose.Gis.Geometries`.'
    question: Which class represents a circular string?
  - answer: Yes – use `Drivers.Shapefile` when creating the layer.
    question: Can I save the layer as a Shapefile?
  - answer: A temporary license works for evaluation; a full license is required for
      production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- shapefile creation
- Aspose.GIS
- GIS development
title: Wie man ein Shapefile mit Circular String in Aspose.GIS erstellt
url: /de/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Shapefile mit Circular String in Aspose.GIS erstellt

## Einleitung
Wenn Sie eine GIS-Anwendung auf der .NET-Plattform entwickeln, ist das Erlernen **wie man ein Shapefile erstellt** mit Circular-String-Geometrie ein grundlegender Schritt. Aspose.GIS für .NET rationalisiert den gesamten Arbeitsablauf: Sie erstellen einen Vektorlayer, fügen erweiterte Geometrien hinzu und schreiben das Ergebnis mit nur wenigen Zeilen C#‑Code in ein Shapefile.

## Schnelle Antworten
- **Was bedeutet „create vector layer“?** Es erstellt einen neuen Container (Layer), der räumliche Features wie Punkte, Linien oder Polygone halten kann.  
- **Welche Klasse repräsentiert einen Circular String?** `CircularString` aus `Aspose.Gis.Geometries`.  
- **Kann ich den Layer als Shapefile speichern?** Ja – verwenden Sie `Drivers.Shapefile` beim Erstellen des Layers.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine temporäre Lizenz reicht für die Evaluierung; für die Produktion ist eine Volllizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was bedeutet „create vector layer“?
Der **Vectorlayer** ist eine logische Sammlung, die Vektor-Features (Punkte, Linien, Polygone) in einer einzigen Datenquelle speichert.  
*Direkte Antwort:* Sie erstellen einen Vectorlayer, indem Sie `VectorLayer.Create(path, Drivers.Shapefile)` innerhalb eines `using`‑Blocks aufrufen; dadurch wird die Datei auf dem Datenträger angelegt und für das Einfügen von Features vorbereitet. Nachdem der Layer existiert, können Sie jede unterstützte Geometrie, einschließlich Circular Strings, hinzufügen, und die Bibliothek übernimmt die räumliche Indexierung automatisch.

## Warum einen Circular String hinzufügen?
Circular Strings ermöglichen es, glatte Bögen zu modellieren, ohne manuell viele kurze Liniensegmente zu erzeugen.  
*Direkte Antwort:* Das Hinzufügen eines Circular Strings reduziert die Anzahl der für die Darstellung von Kurven benötigten Scheitelpunkte um bis zu 80 %, was die Dateigröße und die Renderleistung verbessert, während die geometrische Treue für Straßen, Flusskurven und andere gebogene Features erhalten bleibt.

## Voraussetzungen
- **.NET Framework oder .NET Core** auf Ihrem Rechner installiert.  
- **Aspose.GIS für .NET** Bibliothek – laden Sie sie von der offiziellen Seite **[hier](https://releases.aspose.com/gis/net/)** herunter.  
- Eine IDE wie **Visual Studio** oder **JetBrains Rider**.  
- Grundlegende Kenntnisse in der **C#**‑Programmierung.

## Namespaces importieren
Die folgenden Namespaces geben Ihnen Zugriff auf die Kern‑GIS‑Klassen:

Der Namespace `Aspose.Gis` enthält die Treiber‑Infrastruktur, während `Aspose.Gis.Geometries` Geometrietypen wie `CircularString` bereitstellt.

## Wie man ein Shapefile mit Aspose.GIS erstellt?
VectorLayer ist die Klasse, die zum Erstellen und Verwalten von Vektor‑Datenquellen verwendet wird.  
Laden Sie den Ausgabepfad, öffnen Sie einen Vectorlayer, bauen Sie einen Circular String und schreiben Sie das Feature – alles in einer kompakten Sequenz.  
*Direkte Antwort:* Rufen Sie `VectorLayer.Create(outputPath, Drivers.Shapefile)` innerhalb eines `using`‑Blocks auf, instanziieren Sie ein `Feature`, weisen Sie ihm eine mit `AddPoint` erstellte `CircularString`‑Geometrie zu und fügen Sie das Feature dem Layer hinzu; der Layer wird automatisch beim Verlassen des Blocks geschrieben und erzeugt ein einsatzbereites Shapefile.

### Schritt 1: Ausgabedateipfad festlegen
Legen Sie den Ort fest, an dem das Shapefile geschrieben wird.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ersetzen Sie `"Your Document Directory"` durch den tatsächlichen Ordnerpfad auf Ihrem System.

### Schritt 2: Vectorlayer erstellen
Öffnen Sie einen `VectorLayer` mit der `Create`‑Methode. Dies ist der Kern der **create vector layer**‑Operation.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

### Schritt 3: Neues Feature konstruieren
Ein Feature repräsentiert einen einzelnen räumlichen Datensatz innerhalb des Layers.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Schritt 4: Circular‑String‑Geometrie erstellen
Fügen Sie die Punkte hinzu, die die gekrümmte Form definieren. Die Punktsequenz erzeugt einen Bogen, der am selben Ort beginnt und endet und einen geschlossenen Circular String bildet.

```csharp
    var feature = layer.ConstructFeature();
```

### Schritt 5: Geometrie zuweisen und das Feature dem Layer hinzufügen
Verknüpfen Sie die Geometrie mit dem Feature und speichern Sie es im Layer.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

Wenn der `using`‑Block endet, wird der Layer automatisch auf das Shapefile auf dem Datenträger geschrieben.

## Häufige Probleme & Lösungen
| Problem | Lösung |
|---------|--------|
| **Dateipfad ungültig** | Stellen Sie sicher, dass das Verzeichnis existiert und Sie Schreibrechte haben. |
| **CircularString erscheint als gerade Linie** | Überprüfen Sie, ob die Punkte in der richtigen Reihenfolge hinzugefügt wurden; der erste und letzte Punkt sollten für eine geschlossene Form identisch sein. |
| **Lizenzausnahme** | Verwenden Sie während der Entwicklung eine temporäre Lizenz oder erwerben Sie eine Volllizenz für den Produktionseinsatz. |

## Häufig gestellte Fragen

### Ist Aspose.GIS für .NET mit allen Versionen des .NET Frameworks kompatibel?
Ja, Aspose.GIS für .NET ist so konzipiert, dass es mit einer breiten Palette von .NET‑Versionen funktioniert, von Framework 4.5 bis zu den neuesten .NET 8‑Versionen.

### Kann ich Aspose.GIS für .NET mit anderen GIS‑Bibliotheken integrieren?
Absolut! Sie können Daten mit anderen Bibliotheken einlesen, mit Aspose.GIS bearbeiten und anschließend wieder schreiben, dank seiner flexiblen API.

### Unterstützt Aspose.GIS für .NET die Visualisierung räumlicher Daten?
Ja, die Bibliothek enthält Rendering‑Werkzeuge, mit denen Sie Karten und visuelle Darstellungen Ihrer Geometrien erzeugen können.

### Gibt es ein Community‑Forum, in dem ich Hilfe zu Aspose.GIS für .NET erhalten kann?
Ja, Sie können das Aspose.GIS‑Forum **[hier](https://forum.aspose.com/c/gis/33)** besuchen, um Fragen zu stellen und Erfahrungen zu teilen.

### Kann ich eine temporäre Lizenz erhalten, um Aspose.GIS für .NET zu evaluieren?
Natürlich! Eine temporäre Evaluierungslizenz ist **[hier](https://purchase.aspose.com/temporary-license/)** verfügbar.

### Wie füge ich komplexere Geometrien (z. B. MultiLineString) zum selben Layer hinzu?
Erstellen Sie das passende Geometrie‑Objekt (z. B. `MultiLineString`), füllen Sie es mit einzelnen `LineString`‑Objekten, weisen Sie es `feature.Geometry` zu und fügen Sie das Feature genauso hinzu wie beim Circular String.

## FAQ (Kurzreferenz)

**Q:** Wie erstelle ich **create vector layer** programmgesteuert?  
**A:** Rufen Sie `VectorLayer.Create(path, Drivers.Shapefile)` (oder einen anderen Treiber) innerhalb eines `using`‑Blocks auf.

**Q:** Welche Methode fügt Punkte zu einem Circular String hinzu?  
**A:** Verwenden Sie `circularString.AddPoint(x, y)` für jede Koordinate.

**Q:** Kann ich mehrere Geometrien im selben Layer speichern?  
**A:** Ja, erstellen Sie für jede Geometrie ein neues Feature und fügen Sie es mit `layer.Add(feature)` hinzu.

**Q:** Was soll ich tun, wenn das Shapefile nicht erstellt wird?  
**A:** Überprüfen Sie, ob das Ausgabeverzeichnis existiert, Sie Schreibrechte haben und der Treiber (`Drivers.Shapefile`) korrekt referenziert ist.

**Q:** Wird für das Evaluierungs‑Build eine Lizenz benötigt?  
**A:** Eine temporäre Lizenz reicht für Entwicklung und Tests aus; für den Produktionseinsatz ist eine Volllizenz erforderlich.

## Fazit
Durch das Befolgen dieser Schritte wissen Sie jetzt **wie man ein Shapefile** erstellt und es mit einer **Circular String**‑Geometrie mithilfe von Aspose.GIS für .NET anreichert. Diese Grundlage ermöglicht es Ihnen, umfangreichere GIS‑Lösungen zu entwickeln – egal, ob Sie Verkehrsnetze kartieren, Umweltdaten visualisieren oder benutzerdefinierte räumliche Analyse‑Tools erstellen.

---

**Zuletzt aktualisiert:** 2026-08-30  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

## Verwandte Tutorials

- [Wie man ein Shapefile mit Aspose.GIS für .NET erstellt](/gis/net/layer-management/create-new-shapefile/)
- [Vectorlayer und Kurvenpolygon mit Aspose.GIS erstellen](/gis/net/geometry-creation/create-curve-polygon-geometry/)
- [Wie man einen Vectorlayer mit SRS mithilfe von Aspose.GIS für .NET erstellt](/gis/net/layer-management/create-vector-layer-with-srs/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}