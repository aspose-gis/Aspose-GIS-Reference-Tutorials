---
date: 2025-12-21
description: Erfahren Sie, wie Sie Linestring-Geometrie erstellen und Geometrie mit
  Aspose.GIS für .NET in WKB konvertieren, wobei Sie die ExtendedPostGis-Variante
  verwenden.
linktitle: Specify WKB Variant on Translation
second_title: Aspose.GIS .NET API
title: Linestring‑Geometrie und WKB‑Variante in Aspose.GIS .NET erstellen
url: /de/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# WKB‑Variante bei der Übersetzung in Aspose.GIS für .NET angeben

## Einführung
Im Bereich der Entwicklung von Geoinformationssystemen (GIS) zeichnet sich Aspose.GIS für .NET als leistungsstarkes Toolset aus. Wenn Sie **eine Linestring‑Geometrie erstellen** und anschließend **die Geometrie in WKB konvertieren** möchten, sind Sie hier genau richtig. Seine Vielseitigkeit und Effizienz machen es zur bevorzugten Wahl für Entwickler, die GIS‑Funktionalitäten nahtlos in ihre .NET‑Anwendungen integrieren wollen. Dieser Artikel dient als umfassende Anleitung zur Nutzung von Aspose.GIS für .NET, wobei der Fokus speziell auf das Angeben von WKB‑Varianten (Well‑Known Binary) während Übersetzungsvorgängen liegt.

## Schnellantworten
- **Wofür steht WKB?** Well‑Known Binary, eine kompakte binäre Darstellung geometrischer Objekte.  
- **Welche WKB‑Variante speichert SRID‑Informationen?** Die `ExtendedPostGis`‑Variante (EWKB).  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Für den Produktionseinsatz ist eine temporäre oder vollständige Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, und .NET 5/6+.  
- **Wie lange dauert die Implementierung?** In der Regel unter 10 Minuten für ein einfaches Beispiel.

## Was ist eine Linestring‑Geometrie?
Ein Linestring ist eine einfache geometrische Form, die aus einer Sequenz von Punkten besteht, die durch gerade Liniensegmente verbunden sind. Er wird häufig verwendet, um Straßen, Flüsse oder andere lineare Merkmale in GIS‑Daten darzustellen.

## Warum eine WKB‑Variante angeben?
Die Wahl der richtigen WKB‑Variante stellt sicher, dass wichtige Metadaten – wie der Spatial Reference System Identifier (SRID) – erhalten bleiben, wenn Sie Geometriedaten speichern oder austauschen. Die `ExtendedPostGis`‑Variante (EWKB) ist besonders nützlich, wenn Sie mit PostgreSQL/PostGIS oder einem System arbeiten, das SRID‑Informationen im Binärformat erwartet.

## Voraussetzungen
Bevor Sie sich mit dem Angeben von WKB‑Varianten in Aspose.GIS für .NET befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

### Installation von Aspose.GIS für .NET
1. Aspose.GIS herunterladen: Besuchen Sie den [Download‑Link](https://releases.aspose.com/gis/net/), um das Aspose.GIS‑Paket für .NET zu erhalten.  
2. Paket installieren: Folgen Sie den Installationsanweisungen in der Dokumentation, um Aspose.GIS nahtlos in Ihre .NET‑Umgebung zu integrieren.

### Vertrautheit mit C#‑Programmierung
1. Grundkenntnisse in C#: Stellen Sie sicher, dass Sie ein grundlegendes Verständnis der C#‑Syntax und -Konzepte besitzen.

## Namespaces importieren
Um Ihre Arbeit mit Aspose.GIS für .NET zu starten und die Funktionen effektiv zu nutzen, müssen Sie die erforderlichen Namespaces in Ihr Projekt einbinden. Hier ein Schritt‑für‑Schritt‑Leitfaden:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Diese Namespaces ermöglichen den Zugriff auf die Aspose.GIS‑Funktionalitäten, sodass Sie geografische Daten mühelos verarbeiten können.

## Wie erstellt man eine Linestring‑Geometrie?
Wir zerlegen das bereitgestellte Beispiel in mehrere Schritte, um den Prozess des Angebens von WKB‑Varianten bei der Übersetzung gründlich zu verstehen.

### Schritt 1: Erstellen eines Geometrie‑Objekts
```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
In diesem Schritt **erstellen wir eine Linestring‑Geometrie**, die ein lineares Merkmal mit den angegebenen Koordinaten darstellt.

### Schritt 2: Generieren der WKB‑Darstellung
```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Hier **konvertieren wir die Geometrie in WKB** unter Verwendung der `ExtendedPostGis`‑Variante, die SRID‑Informationen einbettet.

### Schritt 3: Schreiben in eine Datei
```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Abschließend schreiben wir die erzeugten WKB‑Binärdaten in eine Datei namens `EWkbFile.ewkb` im gewünschten Verzeichnis.

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|-------|--------|----------|
| **Leere Datei** | `Path.Combine` verweist auf ein nicht existierendes Verzeichnis. | Stellen Sie sicher, dass das Zielverzeichnis existiert, oder erstellen Sie es mit `Directory.CreateDirectory`. |
| **Falscher SRID** | Verwendung von `WkbVariant.Standard` verliert den SRID. | Verwenden Sie stets `WkbVariant.ExtendedPostGis`, wenn die SRID‑Erhaltung erforderlich ist. |
| **Lizenz‑Ausnahme** | Ausführung ohne gültige Lizenz in der Produktion. | Laden Sie vor dem Ausführen in einer Produktionsumgebung eine temporäre oder vollständige Lizenz. |

## FAQ's
### Ist Aspose.GIS für .NET mit allen .NET‑Versionen kompatibel?
Aspose.GIS für .NET ist so konzipiert, dass es mit verschiedenen .NET‑Versionen kompatibel ist und somit Flexibilität und Zugänglichkeit für Entwickler bietet.

### Kann ich Support oder Hilfe bei der Nutzung von Aspose.GIS für .NET anfordern?
Ja, Sie können über das dedizierte [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) Support und Hilfe erhalten, wo Experten und andere Entwickler Ihre Fragen beantworten.

### Bietet Aspose.GIS für .NET eine kostenlose Testversion an?
Ja, Sie können die Funktionen von Aspose.GIS für .NET über eine kostenlose Testversion unter [diesem Link](https://releases.aspose.com/) ausprobieren.

### Wie erhalte ich eine temporäre Lizenz für Aspose.GIS für .NET?
Eine temporäre Lizenz erhalten Sie, indem Sie die [temporäre Lizenz‑Seite](https://purchase.aspose.com/temporary-license/) besuchen und den dortigen Anweisungen folgen.

### Wo kann ich eine Lizenz für Aspose.GIS für .NET erwerben?
Eine Lizenz können Sie über die Kaufseite unter [diesem Link](https://purchase.aspose.com/buy) erwerben.

## Häufig gestellte Fragen
**F: Kann ich die EWKB‑Datei mit PostGIS verwenden?**  
A: Ja, die `ExtendedPostGis`‑Variante erzeugt EWKB, das den SRID enthält und von PostGIS direkt gelesen werden kann.

**F: Ist es möglich, eine WKB‑Datei wieder in ein Geometrie‑Objekt zu laden?**  
A: Absolut. Verwenden Sie `Geometry.FromBinary(byteArray)`, um die Geometrie zu rekonstruieren.

**F: Unterstützt die Bibliothek weitere Geometrietypen wie Polygone?**  
A: Ja, Aspose.GIS verarbeitet Punkte, Linestrings, Polygone, Multipolygone und mehr.

**F: Wie gebe ich beim Erstellen der Geometrie einen anderen SRID an?**  
A: Setzen Sie den SRID am Geometrie‑Objekt, bevor Sie `AsBinary` aufrufen, z. B. `geometry.SRID = 4326;`.

**F: Funktioniert dieser Code auch unter .NET Core?**  
A: Ja, dieselbe API funktioniert über .NET Framework, .NET Core und .NET 5/6 hinweg.

---

**Zuletzt aktualisiert:** 2025-12-21  
**Getestet mit:** Aspose.GIS für .NET 23.9 (zum Zeitpunkt der Erstellung)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}