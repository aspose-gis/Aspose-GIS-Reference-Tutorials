---
date: 2025-12-06
description: Erfahren Sie, wie Sie GeoJSON mit Gruppierung in TopoJSON konvertieren,
  das Objektname‑Attribut festlegen und GeoJSON‑Features mit Aspose.GIS für .NET gruppieren.
linktitle: How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS
second_title: Aspose.GIS .NET API
title: Wie man GeoJSON zu TopoJSON mit Gruppierung unter Verwendung von Aspose.GIS
  konvertiert
url: /de/net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man GeoJSON zu TopoJSON mit Gruppierung mittels Aspose.GIS konvertiert

## Einführung

In diesem Schritt‑für‑Schritt‑Tutorial lernen Sie **wie man GeoJSON**‑Dateien in TopoJSON konvertiert, während Sie Features basierend auf einem ausgewählten Attribut gruppieren. Die Verwendung der Aspose.GIS .NET‑API macht die Konvertierung schnell, zuverlässig und vollständig aus Ihrem C#‑Code steuerbar. Egal, ob Sie einen ASP.NET‑GeoJSON‑Konvertierungsservice oder ein Desktop‑GIS‑Tool erstellen, zeigt Ihnen dieser Leitfaden genau, was Sie tun müssen.

## Schnelle Antworten
- **Welche Bibliothek übernimmt die Konvertierung?** Aspose.GIS for .NET  
- **Wie lange dauert die Implementierung?** In der Regel 5‑10 Minuten für ein Basis‑Setup  
- **Benötige ich eine Lizenz für die Produktion?** Ja, eine kommerzielle Lizenz ist erforderlich (Kostenlose Testversion verfügbar)  
- **Kann ich Features nach beliebigem Attribut gruppieren?** Ja – setzen Sie das `ObjectNameAttribute` auf das Feld, nach dem Sie gruppieren möchten  
- **Wird .NET Core unterstützt?** Absolut – die API funktioniert mit .NET Core, .NET 5/6 und dem klassischen .NET Framework  

## Was ist GeoJSON und TopoJSON?

GeoJSON ist ein weit verbreitetes JSON‑Format zur Kodierung geografischer Features wie Punkte, Linien und Polygone. TopoJSON erweitert GeoJSON, indem es Topologie (gemeinsame Liniensegmente) speichert, was die Dateigröße reduziert und die Render‑Performance für komplexe Karten verbessert. Die Konvertierung zwischen beiden ist ein gängiger Schritt, wenn Sie kompakte Kartendaten für Web‑Visualisierungen benötigen.

## Warum GeoJSON‑Features gruppieren?

Das Gruppieren (`group geojson features`) ermöglicht es Ihnen, verwandte Geometrien unter einem einzigen benannten Objekt im resultierenden TopoJSON zu organisieren. Dies ist besonders nützlich, wenn:
- Sie separate Ebenen für verschiedene Verwaltungsregionen erstellen möchten.  
- Ihre Front‑End‑Mapping‑Bibliothek benannte Objekte für Styling oder Interaktion erwartet.  
- Sie Duplikate reduzieren müssen, indem Sie Grenzen zwischen benachbarten Features teilen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. **Aspose.GIS for .NET** – herunterladen und installieren von der offiziellen Seite [here](https://releases.aspose.com/gis/net/).  
2. **Entwicklungsumgebung** – Visual Studio, Visual Studio Code oder jede IDE, die C# unterstützt.  
3. **Beispiel‑GeoJSON‑Datei** – eine Datei, die die Features enthält, die Sie konvertieren möchten.  

## Namespaces importieren

Fügen Sie zunächst die erforderlichen Namespaces in Ihrem Projekt ein:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Dateipfade definieren

Geben Sie an, wo das Quell‑GeoJSON liegt und wohin das TopoJSON geschrieben werden soll:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **Pro Tipp:** Verwenden Sie `Path.Combine` für plattformübergreifende Pfadkonstruktion, wenn Sie .NET Core anvisieren.

### Schritt 2: Konvertierungsoptionen konfigurieren (Object Name Attribute festlegen)

Erstellen Sie eine `ConversionOptions`‑Instanz und teilen Sie Aspose.GIS mit, wie die Features gruppiert werden sollen:

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

Ersetzen Sie `"group"` durch den tatsächlichen Eigenschaftsnamen in Ihrem GeoJSON, den Sie für die **GeoJSON‑Feature‑Gruppierung** verwenden möchten. Das `DefaultObjectName` stellt sicher, dass jedes Feature in ein TopoJSON‑Objekt gelangt, selbst wenn das Attribut fehlt.

### Schritt 3: Konvertierung durchführen (GeoJSON zu TopoJSON konvertieren)

Führen Sie die Konvertierung mit einem einzigen API‑Aufruf aus:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Nach der Ausführung enthält `convertedSampleWithGrouping_out.topojson` die TopoJSON‑Darstellung, wobei die Features gemäß dem von Ihnen angegebenen Attribut gruppiert sind.

## Häufige Probleme und Fehlerbehebung

| Symptom | Wahrscheinliche Ursache | Lösung |
|---------|--------------------------|--------|
| **Alle Features landen in „unnamed“** | `ObjectNameAttribute` stimmt mit keiner Eigenschaft im GeoJSON überein | Überprüfen Sie den genauen Eigenschaftsnamen (Groß‑/Kleinschreibung) und aktualisieren Sie die Option |
| **Ausgabedatei ist leer** | Falscher Dateipfad oder fehlende Leseberechtigungen | Verwenden Sie absolute Pfade oder stellen Sie sicher, dass die Anwendung Zugriff auf das Dateisystem hat |
| **Konvertierung wirft `NotSupportedException`** | Versuch, ein GeoJSON mit nicht unterstützten Geometrietypen zu konvertieren (z. B. GeometryCollection) | Vereinfachen Sie die Quelldaten oder aktualisieren Sie auf die neueste Aspose.GIS‑Version |

## Häufig gestellte Fragen

**F: Kann ich Features basierend auf mehreren Attributen gruppieren?**  
A: Ja, Sie können mehrere Felder zu einem einzigen virtuellen Attribut verketten oder mehrere Konvertierungsdurchläufe mit unterschiedlichen `ObjectNameAttribute`‑Werten ausführen.

**F: Ist Aspose.GIS mit ASP.NET Core kompatibel?**  
A: Absolut – die Bibliothek funktioniert mit ASP.NET Core, .NET 5, .NET 6 und dem klassischen .NET Framework.

**F: Kann ich andere geografische Formate neben GeoJSON konvertieren?**  
A: Ja, Aspose.GIS unterstützt Shapefile, KML, GML, CSV und viele weitere Formate für Import und Export.

**F: Bietet Aspose.GIS eine kostenlose Testversion an?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.GIS unter [here](https://releases.aspose.com/) erhalten.

**F: Wo kann ich Unterstützung für Aspose.G erhalten?**  
A: Sie können Unterstützung im Aspose.GIS‑Community‑Forum [here](https://forum.aspose.com/c/gis/33) erhalten.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Zuletzt aktualisiert:** 2025-12-06  
**Getestet mit:** Aspose.GIS for .NET (neueste Version)  
**Autor:** Aspose  

---