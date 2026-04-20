---
date: 2026-02-08
description: Erfahren Sie, wie Sie eine Netzwerk‑Routing‑Prüfung durchführen, indem
  Sie berührende Geometrien mit Aspose.GIS für .NET erkennen, einer leistungsstarken
  Bibliothek zur Verarbeitung räumlicher Daten und zur Durchführung räumlicher Analysen.
linktitle: How to Check Touching Geometries
second_title: Aspose.GIS .NET API
title: 'Netzwerk‑Routing‑Check: Berührende Geometrien mit Aspose.GIS'
url: /de/net/geometry-analysis/check-geometries-touching/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Netzwerk‑Routing‑Prüfung: Berührende Geometrien mit Aspose.GIS für .NET

## Einführung
Wenn Sie **eine Netzwerk‑Routing‑Prüfung** zwischen zwei räumlichen Objekten durchführen müssen, bietet Aspose.GIS für .NET eine saubere, typ‑sichere API, die die Aufgabe trivial macht. In diesem Tutorial sehen Sie, wie Sie Linienzüge, Punkte erstellen und anschließend die Methode `Touches` verwenden, um zu bestimmen, ob die Geometrien nur eine Grenze teilen. Dieser Vorgang ist ein Grundpfeiler vieler **spatial analysis .NET**‑Szenarien wie Routenvalidierung, Kartenüberlagerungs‑Verifizierung und Nähe‑Abfragen.

## Schnelle Antworten
- **Was bedeutet „touching“?** Zwei Geometrien teilen mindestens einen Grenzpunkt, ihre Innenbereiche überschneiden sich jedoch nicht.  
- **Welche Methode prüft das?** `Geometry.Touches(otherGeometry)`.  
- **Benötige ich eine Lizenz für dieses Feature?** Eine Testversion funktioniert für die Entwicklung; für den Produktionseinsatz ist eine permanente Lizenz erforderlich.  
- **Unterstützte .NET‑Versionen?** .NET Framework, .NET Core, .NET 5/6/7 – alles von Aspose.GIS abgedeckt.  
- **Wie lange dauert die Implementierung?** Etwa 5‑10 Minuten für ein einfaches Beispiel.  

## Wie man eine Netzwerk‑Routing‑Prüfung mit berührenden Geometrien durchführt
Im Folgenden führen wir die genauen Schritte aus, die Sie benötigen, um **berührende** Geometrien zu prüfen und das Ergebnis in einen Routing‑Validierungs‑Workflow zu integrieren.

### Was bedeutet „Touching“ in der räumlichen Analyse?
Im GIS‑Jargon beschreibt *touching* eine räumliche Beziehung, bei der sich zwei Geometrien an ihren Kanten treffen, aber nicht überlappen. Es unterscheidet sich von *intersects* (bei dem auch Innenüberlappungen zählen) und wird häufig verwendet, wenn Sie sicherstellen wollen, dass Features nur an einer Grenze zusammenstoßen – zum Beispiel Straßensegmente, die an einem Knotenpunkt verbinden, ohne sich zu kreuzen.

## Warum Aspose.GIS für Spatial Analysis .NET verwenden?
Aspose.GIS stellt eine vollständig verwaltete .NET‑Bibliothek bereit, mit der Sie **räumliche Daten** ohne native GIS‑Installationen verarbeiten können. Sie unterstützt ein breites Spektrum an Formaten (Shapefile, GeoJSON, KML usw.) und bietet Hochleistungs‑Geometrie‑Operationen wie `Touches`, `Intersects`, `Contains` und mehr. Da sie reines .NET ist, können Sie sie direkt in Web‑Services, Desktop‑Apps oder Cloud‑Funktionen einbetten.

## Voraussetzungen
Stellen Sie vor dem Start sicher, dass Sie Folgendes haben:

1. **Visual Studio** (eine aktuelle Version) auf Ihrem Rechner installiert.  
2. **Aspose.GIS for .NET** – laden Sie das neueste Paket von der [official download page](https://releases.aspose.com/gis/net/) herunter.  
3. **Eine gültige Lizenz** (oder eine kostenlose Testversion) – erhalten Sie [hier](https://releases.aspose.com/).  

### Einrichtung Ihrer Umgebung
1. Installieren Sie Visual Studio, falls noch nicht geschehen.  
2. Laden Sie Aspose.GIS for .NET über den obigen Link herunter und fügen Sie das NuGet‑Paket zu Ihrem Projekt hinzu.  
3. Registrieren Sie Ihre Lizenzdatei im Code (oder verwenden Sie für Tests eine temporäre Lizenz).

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

## Schritt 1: Linienzüge (und einen Punkt) erstellen
Im Folgenden **erstellen wir Linienzug‑Objekte** und einen Punkt, die zum Testen der Berührungsbeziehung verwendet werden.

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
- `geometry3` ist ein Punkt, der exakt an diesem gemeinsamen Endpunkt liegt.  
- `geometry4` durchquert denselben Bereich, teilt jedoch **keine** Grenze mit `geometry1`.

## Schritt 2: Berührungsbeziehungen prüfen
Jetzt rufen wir die Methode `Touches` auf, um zu sehen, welche Paare als berührend gelten.

```csharp
Console.WriteLine(geometry1.Touches(geometry2)); // True
Console.WriteLine(geometry2.Touches(geometry1)); // True
Console.WriteLine(geometry1.Touches(geometry3)); // True
Console.WriteLine(geometry1.Touches(geometry4)); // False
```

*Ergebnis*:  
- Die ersten drei Prüfungen geben **True** zurück, weil die Geometrien an einem einzelnen Punkt ohne Innenüberlappung zusammentreffen.  
- Die letzte Prüfung liefert **False**, weil die beiden Linienzüge sich über ein Liniensegment überschneiden und nicht nur an einem Grenzpunkt.

## Häufige Probleme & Tipps
- **Präzisionsprobleme** – GIS‑Berechnungen basieren auf Fließkomma. Wenn Sie unerwartete `False`‑Ergebnisse erhalten, überlegen Sie, die Koordinaten zu normalisieren oder eine Toleranz mit `Geometry.EqualsExact(other, tolerance)` zu verwenden.  
- **Gemischte Geometrietypen** – `Touches` funktioniert über Punkte, Linien und Polygone hinweg, jedoch unterscheiden sich die Semantik; prüfen Sie stets die erwartete Beziehung für Ihr Datenmodell.  
- **Performance** – Bei großen Datensätzen sollten Sie die Prüfungen stapelweise durchführen oder räumliche Indizes (z. B. R‑Tree) von Aspose.GIS nutzen, um O(N²)-Vergleiche zu vermeiden.

## Häufig gestellte Fragen

**F: Ist Aspose.GIS mit allen .NET‑Frameworks kompatibel?**  
A: Ja. Es unterstützt .NET Framework, .NET Core, .NET 5+, und .NET 6+, sodass Sie flexibel für Desktop-, Web‑ und Cloud‑Projekte arbeiten können.

**F: Kann ich Aspose.GIS vor dem Kauf testen?**  
A: Absolut. Sie können eine kostenlose Testversion von der Aspose‑Website [hier](https://purchase.aspose.com/temporary-license/) erhalten, um alle Funktionen, einschließlich der `Touches`‑Operation, zu erkunden.

**F: Wo finde ich Support für Aspose.GIS‑bezogene Fragen?**  
A: Besuchen Sie das offizielle [Aspose.GIS forum](https://forum.aspose.com/c/gis/33), um Fragen zu stellen, Beispiele zu teilen und Hilfe von der Community sowie den Aspose‑Entwicklern zu erhalten.

**F: Wie häufig werden Updates für Aspose.GIS veröffentlicht?**  
A: Aspose veröffentlicht regelmäßig Updates, die neue Formatunterstützung, Leistungsverbesserungen und Bugfixes enthalten und die Kompatibilität mit den neuesten .NET‑Versionen sicherstellen.

**F: Kann ich eine temporäre Lizenz für Aspose.GIS erhalten?**  
A: Ja, eine temporäre Lizenz ist [hier](https://purchase.aspose.com/temporary-license/) für Evaluierungszwecke verfügbar.

**F: Wie hilft die `Touches`‑Methode bei einer Netzwerk‑Routing‑Prüfung?**  
A: Durch die Bestätigung, dass Straßensegmente nur an gemeinsamen Endpunkten (touch) zusammentreffen, können Sie validieren, dass ein Routing‑Netzwerk korrekt verbunden ist, ohne unbeabsichtigte Überlappungen.

---

**Zuletzt aktualisiert:** 2026‑02‑08  
**Getestet mit:** Aspose.GIS for .NET 24.11 (zum Zeitpunkt der Erstellung)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}