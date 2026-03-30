---
date: 2025-12-20
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET ein Polygon mit Lochgeometrie
  erstellen. Dieser Leitfaden zeigt Ihnen, wie Sie ein Loch in ein Polygon einfügen
  und mit Geodaten arbeiten.
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: Polygon mit Lochgeometrie mit Aspose.GIS erstellen
url: /de/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Polygon mit Loch‑Geometrie mit Aspose.GIS erstellen

## Einführung
In diesem Tutorial **erstellen Sie eine Polygon‑mit‑Loch**‑Geometrie mit Aspose.GIS für .NET. Egal, ob Sie eine Kartenanwendung entwickeln, räumliche Analysen durchführen oder Daten für GIS‑Dienste vorbereiten – zu wissen, wie man ein Loch in ein Polygon einbettet, ist unverzichtbar. Wir führen Sie Schritt für Schritt durch den gesamten Prozess, von der Einrichtung der Umgebung bis zur Erzeugung des finalen Polygon‑Objekts.

## Schnelle Antworten
- **Was bedeutet „Polygon mit Loch erstellen“?** Es bedeutet, ein Polygon zu bauen, das einen oder mehrere innere Ringe (Löcher) enthält, die vom Flächeninhalt ausgeschlossen sind.  
- **Welche Bibliothek übernimmt das?** Aspose.GIS für .NET bietet vollständige Unterstützung für äußere und innere Ringe.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Wie lange dauert es?** In der Regel weniger als 10 Minuten für Implementierung und Test.

## Was ist „Polygon mit Loch erstellen“?
Ein Polygon mit Loch zu erstellen bedeutet, einen **äußeren Ring** zu definieren, der die äußere Grenze umschließt, und einen oder mehrere **innere Ringe**, die leere Flächen ausschneiden. Die inneren Ringe werden oft als *Löcher* bezeichnet, weil sie Bereiche darstellen, die nicht zum Polygon‑Oberflächenbereich gehören.

## Warum ein Loch in ein Polygon mit Aspose.GIS einfügen?
- **Genaues räumliches Modellieren:** Real‑world‑Features wie Seen innerhalb von Grundstücken oder Innenhöfe in Gebäuden erfordern Löcher.  
- **Interoperabilität:** Formate wie Shapefile, GeoJSON und GML unterstützen innere Ringe nativ; Aspose.GIS bewahrt sie.  
- **Performance:** Die Bibliothek verwaltet die Geometrie‑Gültigkeit, sodass Sie keinen eigenen Validierungscode schreiben müssen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Aspose.GIS für .NET‑Bibliothek: Sie können sie von [hier](https://releases.aspose.com/gis/net/) herunterladen.  
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine Entwicklungsumgebung mit Visual Studio oder einer anderen .NET‑IDE eingerichtet haben.

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces importieren, um die Aspose.GIS‑Funktionalitäten zu nutzen. So geht’s:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nun fahren wir fort, eine Polygon‑mit‑Loch‑Geometrie mit Aspose.GIS für .NET zu erstellen.

## Schritt 1: Polygon‑Objekt erstellen
Wir beginnen damit, ein leeres `Polygon`‑Objekt zu instanziieren, das später sowohl den äußeren als auch die inneren Ringe aufnehmen wird.

```csharp
Polygon polygon = new Polygon();
```

## Schritt 2: Äußeren Ring definieren
Der äußere Ring definiert die äußere Begrenzung des Polygons. Fügen Sie Punkte in **Uhrzeigersinn** hinzu, um eine geschlossene Form zu erzeugen.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Schritt 3: Inneren Ring (Loch) definieren
Als Nächstes erstellen wir einen inneren Ring – das **Loch**, das vom Polygon‑Flächeninhalt ausgeschlossen wird. Punkte werden typischerweise **gegen den Uhrzeigersinn** hinzugefügt, aber Aspose.GIS kümmert sich automatisch um die Orientierung.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Schritt 4: Äußeren Ring zuweisen und inneren Ring zum Polygon hinzufügen
Zum Schluss verbinden wir den äußeren Ring mit dem Polygon und fügen anschließend den inneren Ring (das Loch) hinzu. Die Methode `AddInteriorRing` kann mehrfach aufgerufen werden, wenn Sie mehrere Löcher benötigen.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Häufige Probleme und Lösungen
| Problem | Ursache | Lösung |
|---------|----------|--------|
| Loch wird im GIS‑Viewer nicht angezeigt | Orientierung des inneren Rings ist umgekehrt | Stellen Sie sicher, dass die Punkte in die entgegengesetzte Richtung des äußeren Rings (gegen den Uhrzeigersinn) hinzugefügt werden. |
| Fehler „Polygon ungültig“ | Ringe nicht geschlossen (erster ≠ letzter Punkt) | Wiederholen Sie den ersten Punkt als letzten Punkt in jedem Ring (wie oben gezeigt). |
| Unerwartete leere Geometrie | `ExteriorRing` wurde nicht zugewiesen, bevor innere Ringe hinzugefügt wurden | Setzen Sie zuerst `polygon.ExteriorRing`, dann rufen Sie `AddInteriorRing` auf. |

## Fazit
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie man mit Aspose.GIS für .NET **Polygon mit Loch**‑Geometrien erstellt. Diese Technik ist grundlegend für viele geospatiale Szenarien, in denen komplexe Formen mit inneren Hohlräumen dargestellt werden müssen.

## Häufig gestellte Fragen
### 1. Was ist Aspose.GIS?
Aspose.GIS ist eine .NET‑Bibliothek, die Entwicklern die Arbeit mit Geodaten ermöglicht, indem sie das Erstellen, Lesen und Manipulieren verschiedener geospatiale Dateiformate erlaubt.

### 2. Kann ich Aspose.GIS für kommerzielle Projekte nutzen?
Ja, Sie können Aspose.GIS sowohl für private als auch für kommerzielle Projekte verwenden, indem Sie eine Lizenz erwerben. Weitere Details finden Sie [hier](https://purchase.aspose.com/buy).

### 3. Gibt es eine kostenlose Testversion von Aspose.GIS?
Ja, Sie können eine kostenlose Testversion von Aspose.GIS unter [hier](https://releases.aspose.com/) erhalten.

### 4. Wo finde ich Support für Aspose.GIS?
Support für Aspose.GIS erhalten Sie im [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33).

### 5. Wie kann ich eine temporäre Lizenz für Aspose.GIS erhalten?
Eine temporäre Lizenz für Aspose.GIS können Sie unter [hier](https://purchase.aspose.com/temporary-license/) beziehen.

---

**Zuletzt aktualisiert:** 2025-12-20  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}