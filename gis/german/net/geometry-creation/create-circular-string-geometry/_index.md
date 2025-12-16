---
date: 2025-12-12
description: Erfahren Sie, wie Sie einen Vektorlayer erstellen und eine kreisförmige
  String‑Geometrie mit Aspose.GIS für .NET hinzufügen – ein schneller Weg, GIS‑Anwendungen
  zu entwickeln.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Vektorlayer & Circular String in Aspose.GIS für .NET erstellen
url: /de/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektorlayer erstellen und Circular String-Geometrie mit Aspose.GIS für .NET

## Einführung
Wenn Sie eine GIS‑Anwendung auf der .NET‑Plattform entwickeln, besteht der erste Schritt häufig darin, **einen Vektorlayer** zu erstellen, der Ihre räumlichen Features speichert. Aspose.GIS für .NET macht diesen Prozess unkompliziert und ermöglicht es Ihnen, diese Layer mit fortgeschrittenen Geometrien wie Circular Strings anzureichern. In diesem Tutorial lernen Sie genau, wie Sie einen Vektorlayer erstellen, eine Circular String‑Geometrie hinzufügen und das Ergebnis als Shapefile speichern – alles mit sauberem, produktionsreifem C#‑Code.

## Schnelle Antworten
- **Was bedeutet „create vector layer“?** Es erstellt einen neuen Container (Layer), der räumliche Features wie Punkte, Linien oder Polygone halten kann.  
- **Welche Klasse repräsentiert einen Circular String?** `CircularString` aus `Aspose.Gis.Geometries`.  
- **Kann ich den Layer als Shapefile speichern?** Ja – verwenden Sie `Drivers.Shapefile` beim Erstellen des Layers.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine temporäre Lizenz reicht für die Evaluierung; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was ist „create vector layer“?
Ein Vektorlayer ist eine logische Gruppierung von Vektor‑Features (Punkten, Linien, Polygonen), die in einer einzigen Datenquelle gespeichert werden. In Aspose.GIS instanziieren Sie einen Layer, indem Sie `VectorLayer.Create` aufrufen und den Zieldateipfad sowie den gewünschten Treiber (z. B. Shapefile) übergeben. Sobald der Layer existiert, können Sie Features hinzufügen, Geometrien zuweisen und räumliche Operationen ausführen.

## Warum einen Circular String hinzufügen?
Circular Strings sind eine Art **linearer Geometrie**, die Bögen mithilfe einer Punktsequenz annähert. Sie sind nützlich, um gekrümmte Straßen, Flusskurven oder andere Features darzustellen, bei denen eine glatte Kurve benötigt wird, ohne viele kleine Liniensegmente zu verwenden.

## Voraussetzungen
- **.NET Framework oder .NET Core** auf Ihrem Rechner installiert.  
- **Aspose.GIS for .NET**‑Bibliothek – laden Sie sie von der offiziellen Seite **[hier](https://releases.aspose.com/gis/net/)** herunter.  
- Eine IDE wie **Visual Studio** oder **JetBrains Rider**.  
- Grundlegende Kenntnisse in der **C#**‑Programmierung.

## Namespaces importieren
Fügen Sie die erforderlichen Namespaces zu Ihrer C#‑Datei hinzu:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Ausgabepfad definieren
Legen Sie den Ort fest, an dem das Shapefile geschrieben wird.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Ersetzen Sie `"Your Document Directory"` durch den tatsächlichen Ordnerpfad auf Ihrem System.

### Schritt 2: **Vektorlayer erstellen**
Öffnen Sie einen `VectorLayer` mit der `Create`‑Methode. Dies ist der Kern der **create vector layer**‑Operation.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Schritt 3: Neues Feature konstruieren
Ein Feature repräsentiert einen einzelnen räumlichen Datensatz im Layer.

```csharp
    var feature = layer.ConstructFeature();
```

### Schritt 4: Circular String-Geometrie erstellen
Fügen Sie die Punkte hinzu, die die gekrümmte Form definieren. Die Punktsequenz erzeugt einen Bogen, der am selben Ort beginnt und endet und so einen geschlossenen Circular String bildet.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Schritt 5: Geometrie zuweisen und das Feature dem Layer hinzufügen
Verknüpfen Sie die Geometrie mit dem Feature und speichern Sie es im Layer.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

Wenn der `using`‑Block endet, wird der Layer automatisch auf das Shapefile auf dem Datenträger geschrieben.

## Häufige Probleme & Lösungen
| Problem | Lösung |
|---------|--------|
| **Ungültiger Dateipfad** | Stellen Sie sicher, dass das Verzeichnis existiert und Sie Schreibrechte haben. |
| **CircularString erscheint als gerade Linie** | Vergewissern Sie sich, dass die Punkte in der richtigen Reihenfolge hinzugefügt werden; der erste und letzte Punkt sollten für eine geschlossene Form identisch sein. |
| **Lizenzausnahme** | Verwenden Sie während der Entwicklung eine temporäre Lizenz oder erwerben Sie eine Voll‑Lizenz für den Produktionseinsatz. |

## Häufig gestellte Fragen

### Ist Aspose.GIS für .NET mit allen Versionen des .NET Framework kompatibel?
Ja, Aspose.GIS für .NET ist so konzipiert, dass es mit einer breiten Palette von .NET‑Versionen funktioniert, vom Framework 4.5 bis zu den neuesten .NET 8‑Releases.

### Kann ich Aspose.GIS für .NET mit anderen GIS‑Bibliotheken integrieren?
Absolut! Sie können Daten mit anderen Bibliotheken einlesen, mit Aspose.GIS bearbeiten und anschließend wieder schreiben, dank seiner flexiblen API.

### Unterstützt Aspose.GIS für .NET die Visualisierung räumlicher Daten?
Ja, die Bibliothek enthält Rendering‑Utilities, mit denen Sie Karten und visuelle Darstellungen Ihrer Geometrien erzeugen können.

### Gibt es ein Community‑Forum, in dem ich Hilfe zu Aspose.GIS für .NET erhalten kann?
Ja, Sie können das Aspose.GIS‑Forum **[hier](https://forum.aspose.com/c/gis/33)** besuchen, um Fragen zu stellen und Erfahrungen zu teilen.

### Kann ich eine temporäre Lizenz erhalten, um Aspose.GIS für .NET zu evaluieren?
Natürlich! Eine temporäre Evaluationslizenz ist **[hier](https://purchase.aspose.com/temporary-license/)** verfügbar.

### Wie füge ich komplexere Geometrien (z. B. MultiLineString) zum selben Layer hinzu?
Erstellen Sie das entsprechende Geometrie‑Objekt (z. B. `MultiLineString`), füllen Sie es mit einzelnen `LineString`‑Objekten, weisen Sie es `feature.Geometry` zu und fügen Sie das Feature wie beim Circular String hinzu.

## Fazit
Durch das Befolgen dieser Schritte wissen Sie jetzt, wie Sie **vector layer**‑Objekte erstellen und mit einer Circular String‑Geometrie mithilfe von Aspose.GIS für .NET anreichern. Diese Grundlage ermöglicht es Ihnen, umfangreichere GIS‑Lösungen zu bauen – sei es beim Kartieren von Verkehrsnetzen, Visualisieren von Umweltdaten oder Entwickeln benutzerdefinierter räumlicher Analyse‑Tools.

---

**Zuletzt aktualisiert:** 2025-12-12  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}