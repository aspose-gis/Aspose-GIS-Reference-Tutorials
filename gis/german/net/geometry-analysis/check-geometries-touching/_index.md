---
date: 2025-12-04
description: Erfahren Sie, wie Sie berührende Geometrien mit Aspose.GIS für .NET prüfen,
  einer leistungsstarken Bibliothek zur Verarbeitung räumlicher Daten und zur Durchführung
  räumlicher Analysen in .NET.
linktitle: How to Check Touching Geometries
second_title: Aspose.GIS .NET API
title: Wie man berührende Geometrien mit Aspose.GIS für .NET prüft
url: /de/net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man berührende Geometrien prüft

## Einführung
Wenn Sie **wie man berührende** zwischen zwei räumlichen Objekten prüfen müssen, bietet Aspose.GIS für .NET eine saubere, typensichere API, die die Aufgabe trivial macht. In diesem Tutorial sehen Sie, wie man Linienzüge und Punkte erstellt und dann die `Touches`‑Methode verwendet, um zu bestimmen, ob die Geometrien nur eine Grenze teilen. Dies ist ein Kernvorgang in vielen räumlichen Analyse‑.NET‑Szenarien, wie Netzwerk‑Routing, Karten‑Overlay‑Validierung und Näheprüfungen.

## Schnelle Antworten
- **Was bedeutet „touching“?** Zwei Geometrien teilen mindestens einen Grenzpunkt, aber ihre Innenräume schneiden sich nicht.  
- **Welche Methode prüft das?** `Geometry.Touches(otherGeometry)`.  
- **Benötige ich eine Lizenz für dieses Feature?** Eine Testversion funktioniert für die Entwicklung; für die Produktion ist eine permanente Lizenz erforderlich.  
- **Unterstützte .NET‑Versionen?** .NET Framework, .NET Core, .NET 5/6/7 – alle von Aspose.GIS abgedeckt.  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten für ein einfaches Beispiel.

## Was bedeutet „Touching“ in der räumlichen Analyse?
Im GIS‑Jargon beschreibt *touching* eine räumliche Beziehung, bei der zwei Geometrien an ihren Kanten aufeinandertreffen, aber sich nicht überlappen. Es unterscheidet sich von *intersects* (das auch Innenüberlappungen einschließt) und wird häufig verwendet, wenn Sie validieren müssen, dass Features nur an einer Grenze zusammentreffen – zum Beispiel Straßensegmente, die an einem Knotenpunkt verbinden, ohne sich zu kreuzen.

## Warum Aspose.GIS für räumliche Analyse in .NET verwenden?
Aspose.GIS stellt eine vollständig verwaltete .NET‑Bibliothek bereit, mit der Sie **räumliche Daten** ohne native GIS‑Installationen verarbeiten können. Sie unterstützt eine Vielzahl von Formaten (Shapefile, GeoJSON, KML usw.) und bietet Hochleistungs‑Geometrie‑Operationen wie `Touches`, `Intersects`, `Contains` und mehr. Da sie reines .NET ist, können Sie sie direkt in Web‑Services, Desktop‑Anwendungen oder Cloud‑Funktionen einbetten.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Visual Studio** (eine aktuelle Version) auf Rechner installiert.  
2. **Aspose.GIS for .NET** – laden Sie das neueste Paket von der [offiziellen Download‑Seite](https://releases.aspose.com/gis/net/) herunter.  
3. **Eine gültige Lizenz** (oder eine kostenlose Testversion) – erhalten Sie [hier](https://releases.aspose.com/).  

### Einrichtung Ihrer Umgebung
1. Installieren Sie Visual Studio, falls noch nicht geschehen.  
2. Laden Sie Aspose.GIS für .NET über den obigen Link herunter und fügen Sie das NuGet‑Paket Ihrem Projekt hinzu.  
3. Wenden Sie Ihre Lizenzdatei im Code an (oder verwenden Sie eine temporäre Lizenz zum Testen).

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

## Schritt 1: Linienzüge erstellen (und einen Punkt)
Im Folgenden **erstellen wir Linienzug**‑Objekte und einen Punkt, die zum Testen der Touch‑Beziehung verwendet werden.

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
- `geometry4` durchquert denselben Bereich, teilt jedoch **keine** Grenze mit `geometry1`.

## Schritt 2: Touch‑Beziehungen prüfen
Jetzt rufen wir die `Touches`‑Methode auf, um zu sehen, welche Paare als berührend gelten.

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*Ergebnis*:  
- Die ersten drei Prüfungen geben **True** zurück, weil die Geometrien sich an einem einzelnen Punkt treffen, ohne Innenüberlappung.  
- Die letzte Prüfung gibt **False** zurück, weil die beiden Linienzüge über ein Liniensegment schneiden, nicht nur an einem Grenzpunkt.

## Häufige Probleme & Tipps
- **Genauigkeitsprobleme** – GIS‑Berechnungen basieren auf Fließkommazahlen. Wenn Sie unerwartete `False`‑Ergebnisse erhalten, sollten Sie die Koordinaten normalisieren oder eine Toleranz mit `Geometry.EqualsExact(other, tolerance)` verwenden.  
- **Gemischte Geometrietypen** – `Touches` funktioniert mit Punkten, Linien und Polygonen, aber die Semantik unterscheidet sich; prüfen Sie stets die erwartete Beziehung für Ihr Datenmodell.  
- **Leistung** – Bei großen Datensätzen sollten Sie die Prüfungen stapelweise durchführen oder räumliche Indizes (z. B. R‑Tree) von Aspose.GIS nutzen, um O(N²)-Vergleiche zu vermeiden.

## Häufig gestellte Fragen

**F: Ist Aspose.GIS mit allen .NET‑Frameworks kompatibel?**  
A: Ja. Es unterstützt .NET Framework, .NET Core, .NET 5+ und .NET 6+, was Ihnen Flexibilität für Desktop-, Web‑ und Cloud‑Projekte bietet.

**F: Kann ich Aspose.GIS vor dem Kauf einer Lizenz testen?**  
A: Absolut. Sie können eine kostenlose Testversion von der Aspose‑Website [hier](https://purchase.aspose.com/temporary-license/) erhalten, um alle Funktionen, einschließlich der `Touches`‑Operation, zu erkunden.

**F: Wo finde ich Unterstützung für Aspose.GIS‑bezogene Anfragen?**  
A: Besuchen Sie das offizielle [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) ,um Fragen zu stellen, Beispiele zu teilen und Hilfe von der Community sowie den Aspose‑Ingenieuren zu erhalten.

**F: Wie häufig werden Updates für Aspose.GIS veröffentlicht?**  
A: Aspose veröffentlicht regelmäßig Updates, die neue Formatunterstützung, Leistungsverbesserungen und Fehlerbehebungen hinzufügen und die Kompatibilität mit den neuesten .NET‑Versionen sicherstellen.

**F: Kann ich eine temporäre Lizenz für Aspose.GIS erhalten?**  
A: Ja, eine temporäre Lizenz ist [hier](https://purchase.aspose.com/temporary-license/) für Evaluierungszwecke verfügbar.

---

**Zuletzt aktualisiert:** 2025-12-04  
**Getestet mit:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}