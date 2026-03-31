---
date: 2025-12-28
description: Erfahren Sie, wie Sie GeoJSON aus einem Stream mit Aspose.GIS für .NET
  lesen. Dieser C#‑Leitfaden zum Lesen von GeoJSON bietet ein Schritt‑für‑Schritt‑Beispiel
  zur Integration von Geodaten.
linktitle: Read GeoJSON from Stream
second_title: Aspose.GIS .NET API
title: Wie man GeoJSON aus einem Stream mit Aspose.GIS für .NET liest
url: /de/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man GeoJSON aus einem Stream mit Aspose.GIS für .NET liest

## Einleitung
Wenn Sie sich fragen **wie man GeoJSON liest** in einer .NET‑Anwendung, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch ein vollständiges **C# GeoJSON Beispiel**, das zeigt, wie man einen GeoJSON‑String konvertiert, einen GeoJSON‑Layer aus einem Memory‑Stream öffnet und GeoJSON‑Eigenschaften mit Aspose.GIS extrahiert. Am Ende haben Sie ein wiederverwendbares Muster, das Sie in jedes Projekt einbinden können, das mit Geodaten arbeiten muss.

## Schnelle Antworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.GIS for .NET  
- **Kann ich GeoJSON direkt aus einem Stream lesen?** Ja – verwenden Sie `VectorLayer.Open` mit `AbstractPath.FromStream`.  
- **Brauche ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine Lizenz erforderlich.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Ist das Extrahieren von Eigenschaften einfach?** Ja – rufen Sie `GetValue<T>(columnName)` auf einem Feature auf.

## Was bedeutet „wie man GeoJSON liest“?
GeoJSON zu lesen bedeutet, das JSON‑basierte Format zu parsen, das geografische Features (Punkte, Linien, Polygone) beschreibt, und diese Features als Objekte verfügbar zu machen, die Sie in Ihrer Anwendung abfragen, bearbeiten oder rendern können.

## Warum Aspose.GIS zum **GeoJSON‑Layer öffnen** verwenden?
Aspose.GIS abstrahiert die Low‑Level‑Parsing‑Details und bietet Ihnen eine konsistente API für viele GIS‑Formate. Es ermöglicht Ihnen, **GeoJSON‑Layer öffnen** direkt aus einem Stream, große Dateien effizient zu verarbeiten und Feature‑Attribute zuzugreifen, ohne eigene JSON‑Parser schreiben zu müssen.

## Voraussetzungen
1. **Grundkenntnisse in C#** – Sie sollten mit der .NET‑Syntax und der Visual‑Studio‑IDE vertraut sein.  
2. **Aspose.GIS installiert** – Laden Sie die Bibliothek von [hier](https://releases.aspose.com/gis/net/) herunter.  
3. **Eine Entwicklungsumgebung** – Visual Studio, Visual Studio Code oder JetBrains Rider funktionieren einwandfrei.  

## Namespaces importieren
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Schritt 1: **GeoJSON‑String konvertieren** – ein **C# GeoJSON Beispiel**
Zuerst erstellen wir einen JSON‑String, der eine einfache `FeatureCollection` darstellt. Dies ist der **GeoJSON‑String konvertieren** Teil des Workflows.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Schritt 2: **GeoJSON‑Layer öffnen** aus einem Stream und **GeoJSON‑Eigenschaften extrahieren**
Jetzt übergeben wir den String an einen `MemoryStream`, öffnen ihn als GIS‑Layer und zeigen, wie Attributwerte gelesen werden (der **GeoJSON‑Eigenschaften extrahieren** Schritt).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Pro Tipp:** `VectorLayer.Open` erkennt das GeoJSON‑Format automatisch, wenn Sie `Drivers.GeoJson` übergeben. Sie können Dateien auch direkt öffnen, indem Sie einen Dateipfad anstelle eines Streams angeben.

## Häufige Probleme & Lösungen
| Problem | Lösung |
|-------|----------|
| **Ungültiges JSON‑Format** | Überprüfen Sie, ob der GeoJSON‑String wohlgeformt ist; verwenden Sie einen JSON‑Validator. |
| **Kodierungsprobleme** | Stellen Sie sicher, dass der Stream UTF‑8 verwendet (`Encoding.UTF8.GetBytes`). |
| **Fehlende Eigenschaften** | Prüfen Sie, ob der Property‑Name korrekt geschrieben ist (`"name"` im Beispiel). |
| **Lizenzausnahme** | Verwenden Sie eine Testlizenz für Tests; setzen Sie eine permanente Lizenz für die Produktion ein. |

## Häufig gestellte Fragen
### Ist Aspose.GIS mit anderen GIS‑Formaten kompatibel?
Ja, Aspose.GIS unterstützt GeoJSON, Shapefile, KML, GML und viele weitere Formate.

### Kann ich Aspose.GIS vor dem Kauf testen?
Ja, Sie können eine kostenlose Testversion von Aspose.GIS von [hier](https://releases.aspose.com/) herunterladen.

### Wo finde ich die Dokumentation für Aspose.GIS?
Sie finden die Dokumentation für Aspose.GIS [hier](https://reference.aspose.com/gis/net/).

### Wie kann ich Support für Aspose.GIS erhalten?
Sie können Support für Aspose.GIS im Aspose‑Forum [hier](https://forum.aspose.com/c/gis/33) erhalten.

### Benötige ich eine temporäre Lizenz für die Nutzung von Aspose.GIS?
Sie können eine temporäre Lizenz für Aspose.GIS von [hier](https://purchase.aspose.com/temporary-license/) erhalten.

## Fazit
In diesem Leitfaden haben wir **wie man GeoJSON liest** aus einem Memory‑Stream mit Aspose.GIS für .NET behandelt, einen **C# GeoJSON‑Lese‑Workflow** demonstriert und gezeigt, wie man **GeoJSON‑Eigenschaften extrahiert** aus dem geöffneten Layer. Mit diesen Schritten können Sie die Verarbeitung geospatialer Daten nahtlos in jede .NET‑Anwendung integrieren.

---

**Zuletzt aktualisiert:** 2025-12-28  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}