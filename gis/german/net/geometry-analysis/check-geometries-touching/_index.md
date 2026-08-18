---
date: 2026-06-05
description: Erfahren Sie, wie Sie in ASP.NET einen LineString erstellen und eine
  Netzwerk‑Routing‑Prüfung durchführen, indem Sie berührende Geometrien mit Aspose.GIS
  für .NET erkennen – eine leistungsstarke Bibliothek für die Handhabung und Analyse
  räumlicher Daten.
keywords:
- create line string asp.net
- touching geometries
- Aspose.GIS spatial analysis
linktitle: Wie man berührende Geometrien prüft
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create line string ASP.NET and perform a network routing
    check by detecting touching geometries with Aspose.GIS for .NET, a powerful library
    for spatial data handling and analysis.
  headline: Create line string ASP.NET – Touching Geometries Check with Aspose.GIS
  type: TechArticle
- description: Learn how to create line string ASP.NET and perform a network routing
    check by detecting touching geometries with Aspose.GIS for .NET, a powerful library
    for spatial data handling and analysis.
  name: Create line string ASP.NET – Touching Geometries Check with Aspose.GIS
  steps:
  - name: '**Visual Studio** (any recent version).'
    text: '**Visual Studio** (any recent version).'
  - name: '**Aspose.GIS for .NET** – download the latest package from the [official
      download page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download the latest package from the [official
      download page](https://releases.aspose.com/gis/net/).'
  - name: '**A valid license** (or a free trial) – obtain it from [here](https://purchase.aspose.com/temporary-license/)
      or view all releases at [here](https://releases.aspose.com/).'
    text: '**A valid license** (or a free trial) – obtain it from [here](https://purchase.aspose.com/temporary-license/)
      or view all releases at [here](https://releases.aspose.com/).'
  - name: Install Visual Studio if you haven’t already.
    text: Install Visual Studio if you haven’t already.
  - name: Add the Aspose.GIS NuGet package to your project (e.g., `Install-Package
      Aspose.GIS`).
    text: Add the Aspose.GIS NuGet package to your project (e.g., `Install-Package
      Aspose.GIS`).
  - name: Apply your license file in code (or use a temporary license for testing).
    text: Apply your license file in code (or use a temporary license for testing).
  type: HowTo
- questions:
  - answer: Yes. It supports .NET Framework, .NET Core, .NET 5+, and .NET 6+, giving
      you flexibility across desktop, web, and cloud projects.
    question: Is Aspose.GIS compatible with all .NET frameworks?
  - answer: Absolutely. You can obtain a free trial from the Aspose website [here](https://purchase.aspose.com/temporary-license/)
      to explore all features, including the `Touches` operation.
    question: Can I try Aspose.GIS before purchasing a license?
  - answer: Visit the official [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to ask questions, share examples, and get help from both the community and Aspose
      engineers.
    question: Where can I find support for Aspose.GIS‑related queries?
  - answer: Aspose releases regular updates that add new format support, performance
      improvements, and bug fixes, ensuring compatibility with the latest .NET releases.
    question: How often are updates released for Aspose.GIS?
  - answer: By confirming that road segments only meet at shared endpoints (touch),
      you can validate that a routing network is correctly connected without unintended
      overlaps.
    question: How does the `Touches` method help with a network routing check?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: LineString in ASP.NET erstellen – Prüfung berührender Geometrien mit Aspose.GIS
url: /de/net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen von Linienstrings in ASP.NET – Prüfung berührender Geometrien mit Aspose.GIS

## Einleitung
Wenn Sie einen **Netzwerk-Routing-Check** zwischen zwei räumlichen Objekten durchführen müssen, ist der erste Schritt, **LineString-Objekte in ASP.NET** zu erstellen, die Ihre Straßenabschnitte modellieren. Aspose.GIS für .NET bietet eine saubere, typensichere API, die diese Operation trivial macht und Ihnen ermöglicht, sich auf die Geschäftslogik statt auf niedrige Geometrie‑Mathematik zu konzentrieren. In diesem Tutorial führen wir Sie durch das Erstellen von Linienstrings, das Hinzufügen eines Punktes und die Verwendung der `Touches`‑Methode, um zu überprüfen, dass Geometrien nur an ihren Grenzen zusammentreffen – eine Schlüsselanforderung für Routenvalidierung, Kartenüberlagerungs‑Verifikation und Nähe‑Abfragen.

## Schnelle Antworten
- **Was bedeutet “touching”?** Zwei Geometrien teilen mindestens einen Grenzpunkt, aber ihre Innenbereiche überschneiden sich nicht.  
- **Welche Methode prüft das?** `Geometry.Touches(otherGeometry)`.  
- **Benötige ich eine Lizenz für dieses Feature?** Eine Testversion funktioniert für die Entwicklung; eine permanente Lizenz ist für die Produktion erforderlich.  
- **Unterstützte .NET‑Versionen?** .NET Framework, .NET Core, .NET 5/6/7 – alle von Aspose.GIS abgedeckt.  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten für ein einfaches Beispiel.  

## Was bedeutet “Touching” in der räumlichen Analyse?
**Touching** beschreibt eine räumliche Beziehung, bei der zwei Geometrien an ihren Kanten zusammentreffen, ohne dass sich ihre Innenbereiche überschneiden. Das unterscheidet sich von *intersects*, das ebenfalls Innenüberlappungen einschließt, und ist entscheidend, wenn Sie bestätigen müssen, dass Straßenabschnitte nur an Kreuzungen verbunden sind.

Die `Touches`‑Methode gibt **true** zurück, wenn die Geometrien einen Grenzpunkt teilen, aber keine Innenpunkte, was sie ideal für die Validierung der Netzwerk‑Konnektivität ohne unbeabsichtigte Kreuzungen macht.

## Warum Aspose.GIS für räumliche Analyse in .NET verwenden?
Aspose.GIS unterstützt **30+ Eingabe‑ und Ausgabeformate** (einschließlich Shapefile, GeoJSON, KML und GML) und kann Dateien bis zu **2 GB** verarbeiten, ohne das gesamte Dokument in den Speicher zu laden, dank seiner Streaming‑Architektur. Die Bibliothek bietet Hochleistungs‑Geometrie‑Operationen—`Touches`, `Intersects`, `Contains`, `Distance`—alle vollständig in .NET verwaltet, sodass Sie räumliche Analysen direkt in Web‑Services, Desktop‑Apps oder Azure Functions einbetten können, ohne externe GIS‑Installationen.

## Voraussetzungen
1. **Visual Studio** (jede aktuelle Version).  
2. **Aspose.GIS for .NET** – laden Sie das neueste Paket von der [offiziellen Download‑Seite](https://releases.aspose.com/gis/net/) herunter.  
3. **Eine gültige Lizenz** (oder eine kostenlose Testversion) – erhalten Sie [hier](https://purchase.aspose.com/temporary-license/) oder sehen Sie alle Releases unter [hier](https://releases.aspose.com/).  

### Einrichten Ihrer Umgebung
1. Installieren Sie Visual Studio, falls noch nicht geschehen.  
2. Fügen Sie das Aspose.GIS NuGet‑Paket zu Ihrem Projekt hinzu (z. B. `Install-Package Aspose.GIS`).  
3. Wenden Sie Ihre Lizenzdatei im Code an (oder verwenden Sie für Tests eine temporäre Lizenz).

## Namespaces importieren
Um die API zu nutzen, importieren Sie die erforderlichen Namespaces:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Wie prüft man berührende Geometrien in Aspose.GIS?
`Touches` ist eine Methode, die **true** zurückgibt, wenn zwei Geometrien nur einen Grenzpunkt teilen und keine Innenpunkte. Laden oder erstellen Sie die Geometrien und rufen Sie dann `Touches` auf, um die Beziehung zu bewerten. Die Methode gibt einen Boolean zurück, der angibt, ob die beiden Formen nur einen Grenzpunkt teilen. Diese einzeilige Prüfung reicht für die meisten Routing‑Validierungsszenarien aus und kann in einer engen Schleife für große Netzwerke ausgeführt werden.

## Schritt 1: Linienstrings erstellen (und einen Punkt)
`LineString` ist ein Geometrietyp, der eine Reihe verbundener Liniensegmente darstellt, die durch geordnete Punkte definiert sind.  

```csharp
var geometry1 = new LineString();
geometry1.AddPoint(0, 0);
geometry1.AddPoint(2, 2);
var geometry2 = new LineString();
geometry2.AddPoint(2, 2);
geometry2.AddPoint(3, 3);
var geometry3 = new Point(2, 2);
var geometry4 = new LineString();
geometry4.AddPoint(1, 1);
geometry4.AddPoint(4, 4);
```

*Erklärung*:
- `geometry1` und `geometry2` teilen den Endpunkt `(2, 2)`.  
- `geometry3` ist ein Punkt, der genau an diesem gemeinsamen Endpunkt liegt.  
- `geometry4` schneidet denselben Bereich, teilt jedoch **keine** Grenze mit `geometry1`.

## Schritt 2: Berührende Beziehungen prüfen
Jetzt rufen wir die `Touches`‑Methode auf, um zu sehen, welche Paare als berührend gelten.

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*Ergebnis*:
- Die ersten drei Prüfungen geben **True** zurück, weil die Geometrien an einem einzelnen Punkt ohne Innenüberlappung zusammentreffen.  
- Die letzte Prüfung gibt **False** zurück, weil die beiden Linienstrings über ein Liniensegment schneiden, nicht nur an einem Grenzpunkt.

## Häufige Probleme & Tipps
- **Präzisionsprobleme** – GIS‑Berechnungen basieren auf Fließkommazahlen. Wenn Sie unerwartete `False`‑Ergebnisse erhalten, sollten Sie die Koordinaten normalisieren oder eine Toleranz mit `Geometry.EqualsExact(other, tolerance)` verwenden.  
- **Gemischte Geometrietypen** – `Touches` funktioniert mit Punkten, Linien und Polygonen, aber die Semantik unterscheidet sich; prüfen Sie stets die erwartete Beziehung für Ihr Datenmodell.  
- **Performance** – Bei großen Datensätzen sollten Sie die Prüfungen stapelweise durchführen oder räumliche Indizes (z. B. R‑Tree) nutzen, die von Aspose.GIS bereitgestellt werden, um O(N²)-Vergleiche zu vermeiden.

## Häufig gestellte Fragen

**Q:** Ist Aspose.GIS mit allen .NET‑Frameworks kompatibel?  
A: Ja. Es unterstützt .NET Framework, .NET Core, .NET 5+, und .NET 6+, was Ihnen Flexibilität für Desktop-, Web- und Cloud‑Projekte bietet.

**Q:** Kann ich Aspose.GIS vor dem Kauf einer Lizenz testen?  
A: Absolut. Sie können eine kostenlose Testversion von der Aspose‑Website [hier](https://purchase.aspose.com/temporary-license/) erhalten, um alle Funktionen, einschließlich der `Touches`‑Operation, zu erkunden.

**Q:** Wo finde ich Unterstützung für Aspose.GIS‑bezogene Anfragen?  
A: Besuchen Sie das offizielle [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33), um Fragen zu stellen, Beispiele zu teilen und Hilfe sowohl von der Community als auch von Aspose‑Ingenieuren zu erhalten.

**Q:** Wie häufig werden Updates für Aspose.GIS veröffentlicht?  
A: Aspose veröffentlicht regelmäßig Updates, die neue Formatunterstützung, Leistungsverbesserungen und Fehlerbehebungen hinzufügen und die Kompatibilität mit den neuesten .NET‑Versionen sicherstellen.

**Q:** Wie hilft die `Touches`‑Methode bei einem Netzwerk‑Routing‑Check?  
A: Indem sie bestätigt, dass Straßenabschnitte nur an gemeinsamen Endpunkten (Touch) zusammentreffen, können Sie validieren, dass ein Routing‑Netzwerk korrekt verbunden ist, ohne unbeabsichtigte Überlappungen.

---

**Zuletzt aktualisiert:** 2026-06-05  
**Getestet mit:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Autor:** Aspose

## Verwandte Tutorials

- [Geodatenverarbeitung mit Aspose.GIS für .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Polygon‑Geometrie in C# erstellen und Schnittprüfung mit Aspose.GIS für .NET](/gis/net/geometry-analysis/check-geometries-intersection/)
- [Wie man die Länge einer Geometrie in .NET mit Aspose.GIS berechnet](/gis/net/geometry-analysis/get-geometry-length/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}