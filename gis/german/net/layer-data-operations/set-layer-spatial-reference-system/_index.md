---
date: 2025-12-31
description: Erfahren Sie, wie Sie einen Vektorlayer erstellen und das räumliche Referenzsystem
  des Layers mit Aspose.GIS für .NET festlegen. Beherrschen Sie die Definition des
  räumlichen Referenzsystems, das Hinzufügen eines Punkt‑Features und das Abrufen
  des EPSG‑Codes.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: Vektorlayer erstellen und das räumliche Referenzsystem des Layers festlegen
url: /de/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektorlayer erstellen und räumliches Referenzsystem des Layers festlegen

## Einleitung
Im weiten Feld der Geoinformationssysteme (GIS) zeichnet sich **Aspose.GIS for .NET** als robustes und vielseitiges Werkzeug für Entwickler aus. In diesem Tutorial **erstellen Sie einen Vektorlayer**, definieren dessen räumliche Referenz, fügen ein Punkt‑Feature hinzu und rufen den EPSG‑Code ab – alles mit klarer, schrittweiser Anleitung. Egal, ob Sie ein erfahrener GIS‑Ingenieur sind oder gerade erst anfangen, diese Techniken helfen Ihnen, das Koordinatensystem der Shapefile korrekt zu setzen und die Zuverlässigkeit Ihrer räumlichen Daten‑Workflows zu erhöhen.

## Schnelle Antworten
- **Was bedeutet „Vektorlayer erstellen“?** Es erzeugt einen neuen GIS‑Layer (z. B. eine Shapefile), der Geometrien wie Punkte, Linien oder Polygone speichern kann.  
- **Welcher EPSG‑Code wird im Beispiel verwendet?** EPSG 26918 (NAD83 / UTM‑Zone 18N).  
- **Kann ich nach dem Erstellen des Layers ein Punkt‑Feature hinzufügen?** Ja – verwenden Sie `ConstructFeature()` und weisen Sie eine `Point`‑Geometrie zu.  
- **Wie rufe ich das CRS des Layers ab?** Lesen Sie `layer.SpatialReferenceSystem.EpsgCode` oder `.Name`.  
- **Benötige ich eine Lizenz für Aspose.GIS?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine Lizenz erforderlich.

## Voraussetzungen
Bevor Sie in das Tutorial einsteigen, stellen Sie sicher, dass Sie folgende Voraussetzungen erfüllt haben:
- Grundkenntnisse in .NET‑Programmierung.  
- Visual Studio auf Ihrem System installiert.  
- Aspose.GIS for .NET‑Bibliothek, die Sie [hier](https://releases.aspose.com/gis/net/) herunterladen können.  
- Grundlegendes Verständnis von räumlichen Referenzsystemen in GIS.

## Namespaces importieren
Importieren Sie in Ihrem .NET‑Projekt die erforderlichen Namespaces, um auf die von Aspose.GIS bereitgestellten Funktionen zuzugreifen. Verwenden Sie das folgende Code‑Snippet:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Schritt 1: Dokumentverzeichnis angeben
Geben Sie den Pfad zu Ihrem Dokumentverzeichnis an. Dies ist der Ort, an dem Ihre räumlichen Daten‑Dateien gespeichert werden.

```csharp
string dataDir = "Your Document Directory";
```

## Schritt 2: Räumliche Referenz definieren und Koordinatensystem der Shapefile festlegen
Definieren Sie den Pfad für die Shapefile und **definieren Sie die räumliche Referenz** mithilfe des EPSG‑Codes (26918 in diesem Beispiel). Dieser Schritt **setzt das Koordinatensystem der Shapefile** für den Layer.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Schritt 3: Vektorlayer erstellen
Jetzt **erstellen Sie den Vektorlayer** mit dem angegebenen Shapefile‑Pfad, dem Treibertyp (Shapefile) und dem gerade definierten räumlichen Referenzsystem.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Schritt 4: Punkt‑Feature zum Layer hinzufügen
Konstruieren Sie ein neues Feature und **fügen Sie ein Punkt‑Feature hinzu**, indem Sie dessen Geometrie setzen (ein `Point` mit den Koordinaten 60, 24). Anschließend fügen Sie das Feature dem Vektorlayer hinzu.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Schritt 5: Informationen zum räumlichen Referenzsystem abrufen (EPSG‑Code abrufen)
Öffnen Sie den Vektorlayer und rufen Sie Informationen zum räumlichen Referenzsystem ab, wie den EPSG‑Code und den menschenlesbaren Namen. Dies demonstriert, wie man **den EPSG‑Code abruft** und **das CRS des Layers setzt**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Wiederholen Sie diese Schritte entsprechend Ihrem Anwendungsfall, und Sie sind gut gerüstet, um das **Erstellen von Vektorlayern** und das Verwalten von räumlichen Referenzen mit Aspose.GIS for .NET zu meistern.

## Häufige Probleme und Lösungen
| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| **Layer lässt sich nicht öffnen** | Falscher Treiber oder beschädigter Dateipfad | Überprüfen Sie `Drivers.Shapefile` und stellen Sie sicher, dass `path` auf eine vorhandene `.shp`‑Datei verweist. |
| **Falsches CRS angezeigt** | Falscher EPSG‑Code verwendet | Prüfen Sie den EPSG‑Code anhand einer autoritativen Quelle (z. B. EPSG.io). |
| **Feature wird nicht gespeichert** | `layer.Add(feature)` wurde nicht innerhalb des `using`‑Blocks aufgerufen | Stellen Sie sicher, dass die `Add`‑Methode ausgeführt wird, bevor der Layer freigegeben wird. |

## Häufig gestellte Fragen
### Ist Aspose.GIS mit anderen GIS‑Bibliotheken kompatibel?
Ja, Aspose.GIS lässt sich gut in andere GIS‑Bibliotheken integrieren und kann zusammen mit ihnen verwendet werden.

### Kann ich Aspose.GIS sowohl für Desktop‑ als auch für Web‑Anwendungen verwenden?
Absolut! Aspose.GIS ist vielseitig einsetzbar und kann sowohl in Desktop‑ als auch in webbasierten Anwendungen genutzt werden.

### Gibt es Lizenzoptionen für Aspose.GIS?
Ja, Sie können Lizenzoptionen prüfen und einen Kauf tätigen [hier](https://purchase.aspose.com/buy).

### Gibt es eine kostenlose Testversion von Aspose.GIS?
Natürlich! Sie können eine kostenlose Testversion [hier](https://releases.aspose.com/) herunterladen.

### Wo kann ich Unterstützung für Aspose.GIS‑bezogene Fragen erhalten?
Für Support oder Fragen besuchen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33).

## Zusätzliche häufig gestellte Fragen
**F: Wie ändere ich das CRS einer bestehenden Shapefile?**  
A: Öffnen Sie den Layer, erstellen Sie ein neues `SpatialReferenceSystem` mit dem gewünschten EPSG‑Code und weisen Sie es `layer.SpatialReferenceSystem` zu, bevor Sie speichern.

**F: Kann ich andere Geometrietypen (z. B. Polygone) mit demselben Ansatz hinzufügen?**  
A: Ja – ersetzen Sie `new Point(x, y)` durch `new Polygon(...)` oder `new LineString(...)` nach Bedarf.

**F: Ist es möglich, effizient mit großen Datensätzen zu arbeiten?**  
A: Verwenden Sie Streaming‑APIs (`VectorLayer.Create` mit `FeatureCollection`) und geben Sie Layer zeitnah frei, um Ressourcen zu schonen.

**F: Unterstützt Aspose.GIS Koordinatentransformationen?**  
A: Ja – nutzen Sie `Geometry.Transform(targetSrs)`, um Geometrien zwischen verschiedenen räumlichen Referenzen zu reprojizieren.

**F: Welche .NET‑Versionen werden unterstützt?**  
A: Aspose.GIS funktioniert mit .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Fazit
In diesem Tutorial haben wir gezeigt, wie man **einen Vektorlayer erstellt**, dessen räumliche Referenz definiert, **ein Punkt‑Feature hinzufügt** und **den EPSG‑Code abruft** mit Aspose.GIS for .NET. Durch das Beherrschen dieser Schritte können Sie das Koordinatensystem der Shapefile sicher festlegen, das CRS des Layers verwalten und zuverlässige GIS‑Anwendungen entwickeln.

---

**Zuletzt aktualisiert:** 2025-12-31  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}