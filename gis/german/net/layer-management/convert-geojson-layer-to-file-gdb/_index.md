---
title: GeoJSON-zu-Datei-GDB-Konvertierung entmystifiziert
linktitle: Konvertieren Sie den GeoJSON-Layer in eine Datei-GDB
second_title: Aspose.GIS .NET-API
description: Schalten Sie Geowunder mit Aspose.GIS für .NET frei! Konvertieren Sie GeoJSON-Layer mühelos in File-Geodatabases. Probieren Sie es jetzt! #Aspose #GIS
weight: 17
url: /de/net/layer-management/convert-geojson-layer-to-file-gdb/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GeoJSON-zu-Datei-GDB-Konvertierung entmystifiziert

## Einführung
Im dynamischen Bereich geografischer Informationssysteme (GIS) ist die Fähigkeit, Daten nahtlos zwischen verschiedenen Formaten zu konvertieren, von entscheidender Bedeutung. Aspose.GIS für .NET erweist sich als leistungsstarker Verbündeter und bietet eine umfassende Suite von Tools für den mühelosen Umgang mit Geodaten. In diesem Tutorial befassen wir uns mit dem Prozess der Konvertierung eines GeoJSON-Layers in eine File-Geodatabase (File GDB) mithilfe von Aspose.GIS für .NET.
## Voraussetzungen
Stellen Sie vor Beginn dieser Geodatenreise sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse in der .NET-Programmierung.
-  Aspose.GIS für .NET installiert. Wenn nicht, laden Sie es herunter von[Hier](https://releases.aspose.com/gis/net/) und befolgen Sie die Installationsanweisungen.
## Namespaces importieren
Um den Konvertierungsprozess zu starten, importieren Sie zunächst die erforderlichen Namespaces:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Lassen Sie uns den Prozess nun in einer Schritt-für-Schritt-Anleitung aufschlüsseln:
## Schritt 1: Richten Sie den GeoJSON-Layer ein
Erstellen Sie zunächst einen GeoJSON-Layer mit relevanten Attributen und Features. Hier ist ein Ausschnitt zur Orientierung:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Attribute hinzufügen
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Konstruieren und fügen Sie Features hinzu
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## Schritt 2: Testdatensatz kopieren
Um die Integrität Ihrer Testdaten zu wahren, erstellen Sie eine Kopie des Datensatzes. Verwenden Sie den folgenden Codeausschnitt:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## Schritt 3: Konvertieren Sie GeoJSON in File GDB
Jetzt ist es an der Zeit, die Konvertierung durchzuführen. Verwenden Sie den folgenden Code:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Attribute kopieren
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Funktionen hinzufügen
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## Abschluss
In diesem Tutorial haben wir uns durch das faszinierende Terrain der Konvertierung eines GeoJSON-Layers in eine File-Geodatabase mit Aspose.GIS für .NET bewegt. Mit diesem Wissen sind Sie nun in der Lage, Geodaten in Ihren .NET-Anwendungen nahtlos zu bearbeiten.
## FAQs
### Ist Aspose.GIS mit dem neuesten .NET Framework kompatibel?
Ja, Aspose.GIS ist mit den neuesten .NET Framework-Versionen kompatibel.
### Kann ich andere Geodatenformate mit Aspose.GIS konvertieren?
Absolut! Aspose.GIS unterstützt eine breite Palette von Geodatenformaten für eine vielseitige Datenbearbeitung.
### Gibt es eine Testversion für Aspose.GIS?
 Ja, Sie können die Funktionen von Aspose.GIS erkunden, indem Sie die Testversion herunterladen[Hier](https://releases.aspose.com/).
### Wie kann ich Unterstützung für Aspose.GIS-bezogene Abfragen erhalten?
 Gehen Sie zu Aspose.GIS[Forum](https://forum.aspose.com/c/gis/33) für engagierte Unterstützung.
### Kann ich eine temporäre Lizenz für Aspose.GIS erhalten?
 Ja, Sie können sich eine temporäre Lizenz sichern[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
