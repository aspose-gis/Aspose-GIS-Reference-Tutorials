---
date: 2026-01-07
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET KML-Dateien schreiben,
  KML erstellen, ein boolesches Attribut hinzufügen und in Ihren Anwendungen LineStrings
  erzeugen.
linktitle: Interact with KML Layer
second_title: Aspose.GIS .NET API
title: Wie man eine KML-Datei mit Aspose.GIS für .NET schreibt
url: /de/net/layer-interaction-and-data-access/interact-with-kml-layer/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man eine KML-Datei mit Aspose.GIS für .NET schreibt

## Einführung
In der heutigen datengetriebenen Welt ermöglicht Ihnen die Fähigkeit, **KML-Dateien** programmgesteuert zu **schreiben**, geografische Informationen plattformübergreifend zu teilen, Routen auf Karten zu visualisieren und Standortdaten in Web‑ oder Mobile‑Apps zu integrieren. Aspose.GIS für .NET macht diesen Prozess unkompliziert, sodass Sie sich auf die Logik statt auf die Dateiformat‑Details konzentrieren können. In diesem Tutorial führen wir Sie Schritt für Schritt durch das Erstellen einer KML‑Ebene, das Hinzufügen von Attributen (einschließlich eines booleschen Attributs) und das Erzeugen einer Line‑String‑Geometrie – alles mit klar verständlichem Code.

## Schnelle Antworten
- **Was bedeutet „KML-Datei schreiben“?** Generierung eines KML (Keyhole Markup Language) Dokuments, das geografische Features wie Punkte, Linien und Polygone beschreibt.  
- **Welche Bibliothek ist die beste für .NET?** Aspose.GIS für .NET bietet eine fluente API zum Erstellen und Bearbeiten von KML‑Dateien.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine Lizenz erforderlich.  
- **Kann ich benutzerdefinierte Attribute hinzufügen?** Ja – Sie können String-, Integer‑, Boolean‑ und Double‑Attribute zu jedem Feature hinzufügen.  
- **Wird die Erstellung von Geometrien unterstützt?** Absolut – Sie können Punkte, Line‑Strings, Polygone und mehr erzeugen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Aspose.GIS für .NET: Laden Sie die Bibliothek von der [Aspose.GIS für .NET Download‑Seite](https://releases.aspose.com/gis/net/) herunter und installieren Sie sie.
- Entwicklungsumgebung: Richten Sie eine geeignete Entwicklungsumgebung ein, z. B. Visual Studio, um Aspose.GIS nahtlos in Ihre .NET‑Projekte zu integrieren.

## Namespaces importieren
Bevor Sie mit KML‑Ebenen arbeiten, fügen Sie die erforderlichen Namespaces in Ihrem Projekt hinzu. Dieser Schritt stellt sicher, dass Sie Zugriff auf die Klassen und Methoden haben, die für die Manipulation von Geodaten nötig sind.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Drawing;
using System.Threading;
using Aspose.Gis.Formats.Kml;
using Aspose.Gis.Formats.Kml.Styles;
using Aspose.Gis.Geometries;
using Point = Aspose.Gis.Geometries.Point;
```

## Schritt 1: Das Dokumentenverzeichnis festlegen
Definieren Sie den Pfad zu Ihrem Dokumentenverzeichnis, in dem die KML‑Dateien gespeichert werden sollen.

```csharp
string dataDir = "Your Document Directory";
```

## Schritt 2: Eine KML‑Ebene erstellen
Initialisieren Sie eine KML‑Ebene mit Aspose.GIS und geben Sie den Pfad für die KML‑Datei an.

```csharp
using (var layer = Drivers.Kml.CreateLayer(dataDir + "Kml_File_out.kml"))
{
```

## Schritt 3: Attribute definieren (boolesches Attribut hinzufügen)
Fügen Sie Attribute zur KML‑Ebene hinzu, um verschiedene Datentypen wie String, Integer, **Boolean** und Double zu repräsentieren. Hier fügen Sie jedem Feature ein **boolesches Attribut** hinzu.

```csharp
layer.Attributes.Add(new FeatureAttribute("string_data", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("int_data", AttributeDataType.Integer));
layer.Attributes.Add(new FeatureAttribute("bool_data", AttributeDataType.Boolean));
layer.Attributes.Add(new FeatureAttribute("float_data", AttributeDataType.Double));
```

## Schritt 4: Features konstruieren und befüllen (Line‑String erstellen)
Erstellen Sie Features, die geospatiale Entitäten darstellen, und setzen Sie Werte für die definierten Attribute. Hier erzeugen wir eine **Line‑String**‑Geometrie, um einen einfachen Pfad zu illustrieren.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("string_data", "string value");
feature.SetValue("int_data", 10);
feature.SetValue("bool_data", true);
feature.SetValue("float_data", 3.14);
feature.Geometry = new LineString(new[] { new Point(0, 0), new Point(1, 1) });
layer.Add(feature);
```

## Schritt 5: Ein weiteres Feature hinzufügen
Wiederholen Sie den Vorgang, um ein zweites Feature mit anderen Attributwerten und einer Null‑Geometrie hinzuzufügen.

```csharp
Feature feature2 = layer.ConstructFeature();
feature2.SetValue("string_data", "string value2");
feature2.SetValue("int_data", 100);
feature2.SetValue("bool_data", false);
feature2.SetValue("float_data", 3.1415);
feature2.Geometry = Geometry.Null;
layer.Add(feature2);
```

## Wie man KML-Datei schreibt – Alles zusammenführen
Wenn Sie die obigen Schritte befolgt haben, besitzen Sie nun eine voll funktionsfähige KML‑Datei, die benutzerdefinierte Attribute (einschließlich eines booleschen Flags) und eine Line‑String‑Geometrie enthält. Sie können die resultierende `Kml_File_out.kml` in Google Earth, ArcGIS oder jedem GIS‑Viewer, der KML unterstützt, öffnen.

## Häufige Probleme & Fehlersuche
- **Dateipfad‑Fehler** – Stellen Sie sicher, dass `dataDir` mit einem Pfadtrennzeichen (`\` oder `/`) endet, das zu Ihrem Betriebssystem passt.  
- **Fehlende Lizenz** – Die Testversion funktioniert für die Evaluierung, aber für uneingeschränktes Schreiben von KML‑Dateien ist eine lizenzierte Version erforderlich.  
- **Null‑Geometrie** – Das Setzen von `Geometry.Null` ist beabsichtigt für Features ohne räumliche Daten; entfernen Sie es, wenn Sie immer Geometrien benötigen.

## Häufig gestellte Fragen
### Ist Aspose.GIS mit anderen GIS‑Formaten kompatibel?
Ja, Aspose.GIS unterstützt verschiedene GIS‑Formate, darunter Shapefile, GeoJSON und KML.

### Kann ich die mit Aspose.GIS erstellten Geodaten visualisieren?
Absolut! Aspose.GIS lässt sich nahtlos in Mapping‑Bibliotheken integrieren, sodass Sie Ihre Geodaten visualisieren können.

### Gibt es eine Testversion von Aspose.GIS?
Ja, Sie können die Funktionen von Aspose.GIS testen, indem Sie die [kostenlose Testversion](https://releases.aspose.com/) herunterladen.

### Wie erhalte ich Support für Aspose.GIS?
Besuchen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Community‑Support oder erkunden Sie Premium‑Support‑Optionen [hier](https://purchase.aspose.com/buy).

### Gibt es temporäre Lizenzen für Aspose.GIS?
Ja, Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erhalten.

## Weitere häufig gestellte Fragen

**Q: Wie erstelle ich **KML‑Dateien** mit benutzerdefiniertem Styling?**  
A: Verwenden Sie den Namespace `Aspose.Gis.Formats.Kml.Styles`, um Symbole, Linienfarben und Beschriftungsstile zu definieren, bevor Sie Features hinzufügen.

**Q: Kann ich große KML‑Dateien effizient schreiben?**  
A: Schreiben Sie Features in Batches und leeren Sie die Ebene periodisch, um den Speicherverbrauch gering zu halten.

**Q: Unterstützt Aspose.GIS .NET Core und .NET 6+?**  
A: Ja, die Bibliothek ist vollständig kompatibel mit .NET Core, .NET 5 und .NET 6.

---

**Zuletzt aktualisiert:** 2026-01-07  
**Getestet mit:** Aspose.GIS 24.10 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}