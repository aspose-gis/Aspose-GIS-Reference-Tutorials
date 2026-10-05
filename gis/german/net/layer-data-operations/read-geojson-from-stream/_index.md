---
date: 2026-10-05
description: Erfahren Sie, wie Sie GeoJSON aus einem Stream mit Aspose.GIS für .NET
  lesen. Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie den GeoJSON‑Stream
  laden, ihn parsen und Eigenschaften in C# extrahieren.
keywords:
- how to read geojson
- load geojson stream
- parse geojson c#
- open geojson layer
- extract geojson properties
lastmod: 2026-10-05
linktitle: GeoJSON aus Stream lesen
og_description: Erfahren Sie, wie Sie GeoJSON aus einem Stream mit Aspose.GIS für
  .NET lesen, einschließlich Parsen, Öffnen einer GeoJSON‑Ebene und Extrahieren von
  Eigenschaften in C#.
og_image_alt: Tutorial guide showing how to read geojson from a stream with Aspose.GIS
  in C#
og_title: Wie man GeoJSON aus einem Stream mit Aspose.GIS für .NET liest
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  headline: How to read geojson from a stream with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  name: How to read geojson from a stream with Aspose.GIS for .NET
  steps:
  - name: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
    text: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
  - name: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
    text: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET – it handles 30+ GIS formats out of the box.
    question: What library should I use?
  - answer: Yes – call `VectorLayer.Open` with `AbstractPath.FromStream`.
    question: Can I read GeoJSON directly from a stream?
  - answer: A free trial works for testing; a full license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Which .NET versions are supported?
  - answer: Absolutely – use `GetValue<T>(columnName)` on a feature.
    question: Is extracting properties simple?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET GIS
- C# geospatial
title: Wie man GeoJSON aus einem Stream mit Aspose.GIS für .NET liest
url: /de/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man GeoJSON aus einem Stream mit Aspose.GIS für .NET liest

## Einleitung
Wenn Sie sich fragen **wie man GeoJSON liest** in einer .NET-Anwendung, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch ein vollständiges **C# GeoJSON Beispiel**, das zeigt, wie man einen GeoJSON-String, **GeoJSON-Stream laden** in einen MemoryStream konvertiert, ein GeoJSON-Layer öffnet und GeoJSON-Eigenschaften mit Aspose.GIS extrahiert. Am Ende haben Sie ein wiederverwendbares Muster, das Sie in jedes Projekt einbinden können, das mit Geodaten arbeiten muss.

## Schnelle Antworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.GIS für .NET – es unterstützt mehr als 30 GIS-Formate sofort.  
- **Kann ich GeoJSON direkt aus einem Stream lesen?** Ja – rufen Sie `VectorLayer.Open` mit `AbstractPath.FromStream` auf.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert zum Testen; für die Produktion ist eine Volllizenz erforderlich.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Ist das Extrahieren von Eigenschaften einfach?** Absolut – verwenden Sie `GetValue<T>(columnName)` auf einem Feature.

**VectorLayer.Open** öffnet ein GIS-Layer aus einer Datenquelle wie einer Datei oder einem Stream. **AbstractPath.FromStream** erstellt ein abstraktes Pfadobjekt, das den bereitgestellten Stream für den GIS‑Treiber repräsentiert. **GetValue<T>(columnName)** liest den Wert des angegebenen Attributs aus einem Feature und gibt ihn als Typ T zurück.

## Was bedeutet das Lesen von GeoJSON?
Das Lesen von GeoJSON ist der Prozess, einen GeoJSON‑formatierten String oder Stream in im Speicher befindliche geografische Feature‑Objekte zu konvertieren. Dieses Format kodiert Punkte, Linien und Polygone mittels JSON, wodurch der Austausch von räumlichen Daten zwischen Web‑Services, Datenbanken und Client‑Anwendungen erleichtert wird. Sobald es geparst ist, können Sie die Features mit jeder GIS‑fähigen .NET‑Bibliothek, wie Aspose.GIS, abfragen, bearbeiten oder rendern.

## Warum Aspose.GIS zum Öffnen eines GeoJSON-Layers verwenden?
Aspose.GIS ermöglicht es Ihnen, einen GeoJSON‑Layer direkt aus einem Stream zu öffnen, wodurch temporäre Dateien entfallen und der I/O‑Overhead reduziert wird. Die Bibliothek unterstützt mehr als 30 GIS‑Formate und kann Dateien bis zu 2 GB verarbeiten, ohne das gesamte Dokument in den Speicher zu laden, was ideal für große Datensätze ist. Sie normalisiert außerdem Koordinatenreferenzsysteme automatisch, sodass Sie sich auf die Geschäftslogik statt auf Low‑Level‑Parsing konzentrieren können.

## Wann würden Sie einen GeoJSON-Stream laden?
Sie würden einen GeoJSON‑Stream laden, wenn Sie räumliche Daten von einer API erhalten, benutzer‑hochgeladene Dateien verarbeiten müssen, ohne sie auf die Festplatte zu schreiben, oder GeoJSON on‑the‑fly aus einer Datenbankabfrage generieren. Streaming vermeidet unnötige Festplatten‑Writes, verbessert die Leistung in Hoch‑Durchsatz‑Szenarien und hält Ihre Anwendung zustandslos, was besonders in cloud‑nativen Microservices wertvoll ist.

## Voraussetzungen
1. **Grundkenntnisse in C#** – Sie sollten mit der .NET‑Syntax und der Visual‑Studio‑IDE vertraut sein.  
2. **Aspose.GIS installiert** – laden Sie die Bibliothek von der [Aspose.GIS .NET download page](https://releases.aspose.com/gis/net/) herunter.  
3. **Eine Entwicklungsumgebung** – Visual Studio, Visual Studio Code oder JetBrains Rider funktionieren einwandfrei.  

## Namespaces importieren
Der Namespace `Aspose.GIS` stellt die Kern‑GIS‑Klassen bereit. `System.IO` liefert Ihnen `MemoryStream` und `System.Text` stellt UTF‑8‑Kodierungs‑Utilities bereit. Das Importieren dieser Namespaces macht den nachfolgenden Code prägnant und lesbar.

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Schritt 1: GeoJSON-String konvertieren – ein C# GeoJSON Beispiel
Zuerst erstellen wir einen JSON‑String, der eine einfache `FeatureCollection` darstellt. Dies ist der **GeoJSON-String konvertieren** Teil des Workflows.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Schritt 2: GeoJSON-Stream laden und GeoJSON‑Eigenschaften extrahieren
Jetzt übergeben wir den String an einen `MemoryStream`, öffnen ihn als GIS‑Layer und demonstrieren, wie man Attributwerte liest (der **GeoJSON‑Eigenschaften extrahieren** Schritt).

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
| **Invalid JSON format** | Überprüfen Sie, ob der GeoJSON‑String wohlgeformt ist; verwenden Sie einen JSON‑Validator. |
| **Encoding problems** | Stellen Sie sicher, dass der Stream UTF‑8 verwendet (`Encoding.UTF8.GetBytes`). |
| **Missing properties** | Prüfen Sie, ob der Property‑Name korrekt geschrieben ist (`"name"` im Beispiel). |
| **License exception** | Verwenden Sie eine Testlizenz zum Testen; setzen Sie eine permanente Lizenz für die Produktion ein. |

## Häufig gestellte Fragen
### Ist Aspose.GIS mit anderen GIS-Formaten kompatibel?
Ja, Aspose.GIS unterstützt GeoJSON, Shapefile, KML, GML und über 20 weitere Formate, sodass Sie zwischen Datenquellen wechseln können, ohne den Code zu ändern.

### Kann ich Aspose.GIS vor dem Kauf testen?
Sie können eine kostenlose Testversion von Aspose.GIS von der [Aspose.GIS free trial download page](https://releases.aspose.com/) herunterladen.

### Wo finde ich die Dokumentation für Aspose.GIS?
Sie finden die Dokumentation für Aspose.GIS unter [Aspose.GIS .NET API reference](https://reference.aspose.com/gis/net/).

### Wie kann ich Support für Aspose.GIS erhalten?
Sie können Support für Aspose.GIS im Aspose GIS‑Forum erhalten: [Aspose GIS forum](https://forum.aspose.com/c/gis/33).

### Benötige ich eine temporäre Lizenz für die Nutzung von Aspose.GIS?
Sie können eine temporäre Lizenz für Aspose.GIS von der [temporary license request page](https://purchase.aspose.com/temporary-license/) erhalten.

## Fazit
In diesem Leitfaden haben wir **wie man GeoJSON liest** aus einem Memory‑Stream mit Aspose.GIS für .NET behandelt, einen **C# GeoJSON‑Lese‑Workflow** demonstriert und gezeigt, wie man **GeoJSON‑Eigenschaften extrahiert** aus dem geöffneten Layer. Mit diesen Schritten können Sie die Verarbeitung von Geodaten nahtlos in jede .NET‑Anwendung integrieren.

---

**Zuletzt aktualisiert:** 2026-10-05  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man GeoJSON in einen Stream schreibt mit Aspose.GIS für .NET](/gis/net/layer-data-operations/write-geojson-to-stream/)
- [Wie man GeoJSON in GDB konvertiert mit Aspose.GIS für .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Shapefile in GeoJSON konvertieren mit Aspose.GIS für .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}