---
date: 2026-04-03
description: Erfahren Sie, wie Sie ein Polygon mit Lochgeometrie mithilfe von Aspose.GIS
  für .NET erstellen. Dieser Leitfaden zeigt Ihnen, wie Sie ein Loch in ein Polygon
  einfügen und mit Geodaten arbeiten.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: Polygon mit Lochgeometrie erstellen
second_title: Aspose.GIS .NET API
title: Polygon mit Lochgeometrie mit Aspose.GIS erstellen
url: /de/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Polygon mit Loch-Geometrie mit Aspose.GIS erstellen

## Einführung
In diesem Tutorial erstellen Sie **Polygon mit Loch**-Geometrie mit Aspose.GIS für .NET. Egal, ob Sie eine Kartenanwendung entwickeln, räumliche Analysen durchführen oder Daten für GIS‑Dienste vorbereiten – das Einbetten eines Lochs in ein Polygon ist essenziell. Wir gehen den gesamten Prozess Schritt für Schritt durch, von der Einrichtung der Umgebung bis zur Erzeugung des finalen Polygon‑Objekts.

## Schnelle Antworten
- **Was bedeutet „Polygon mit Loch erstellen“?** Das bedeutet, ein Polygon zu bauen, das einen oder mehrere innere Ringe (Löcher) enthält, die vom Flächeninhalt ausgeschlossen sind.  
- **Welche Bibliothek übernimmt das?** Aspose.GIS für .NET bietet vollständige Unterstützung für äußere und innere Ringe.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Wie lange dauert das?** In der Regel weniger als 10 Minuten für Implementierung und Test.

## Wie man ein Loch zu einem Polygon mit Aspose.GIS hinzufügt
Ein Loch hinzuzufügen besteht einfach darin, einen **inneren Ring** zu definieren und ihn dem Polygon zuzuweisen. Die Bibliothek kümmert sich um Orientierung und Gültigkeit, sodass Sie sich auf die Koordinaten konzentrieren können, die die gewünschte Leere darstellen.

## Was ist „Polygon mit Loch erstellen“?
Das Erstellen eines Polygons mit einem Loch beinhaltet die Definition eines **äußeren Rings**, der die äußere Grenze umreißt, und eines oder mehrerer **inneren Ringe**, die leere Bereiche ausschneiden. Die inneren Ringe werden häufig *Löcher* genannt, weil sie Flächen darstellen, die nicht zum Polygon gehören.

## Warum ein Loch in ein Polygon mit Aspose.GIS einfügen?
- **Genaues räumliches Modellieren:** Real‑world‑Features wie Seen innerhalb von Grundstücken oder Innenhöfe in Gebäuden erfordern Löcher.  
- **Interoperabilität:** Formate wie Shapefile, GeoJSON und GML unterstützen innere Ringe nativ; Aspose.GIS bewahrt sie.  
- **Performance:** Die Bibliothek verwaltet die Geometrie‑Gültigkeit, sodass Sie keinen eigenen Validierungscode schreiben müssen.

## Praxisbeispiele für Polygone mit Löchern
1. **Grundstück mit einem internen See** – Der See wird als Loch modelliert, sodass er nicht in die Flächenberechnung des Grundstücks einfließt.  
2. **Gebäudekonturen mit Innenhöfen** – Der Innenhof wird von der Gebäudekontur ausgeschlossen.  
3. **Geschützte Zonen innerhalb eines größeren Naturschutzgebiets** – Sie können eingeschränkte Abschnitte ausschließen, ohne separate Layer zu erstellen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Aspose.GIS für .NET‑Bibliothek: Sie können sie von [hier](https://releases.aspose.com/gis/net/) herunterladen.  
2. Entwicklungsumgebung: Stellen Sie sicher, dass eine Entwicklungsumgebung mit Visual Studio oder einer anderen .NET‑IDE eingerichtet ist.

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces importieren, um mit den Aspose.GIS‑Funktionalitäten zu arbeiten. So geht’s:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Jetzt gehen wir weiter und erstellen eine Polygon‑mit‑Loch‑Geometrie mit Aspose.GIS für .NET.

## Schritt 1: Polygon‑Objekt erstellen
Wir beginnen damit, ein leeres `Polygon`‑Objekt zu instanziieren, das später sowohl den äußeren als auch den inneren Ring enthält.

```csharp
Polygon polygon = new Polygon();
```

## Schritt 2: Äußeren Ring definieren
Der äußere Ring definiert die äußere Grenze des Polygons. Fügen Sie Punkte im Uhrzeigersinn hinzu, um eine geschlossene Form zu erzeugen.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Schritt 3: Inneren Ring (Loch) definieren
Als Nächstes erstellen wir einen inneren Ring – das **Loch**, das vom Flächeninhalt des Polygons ausgeschlossen wird. Punkte werden typischerweise gegen den Uhrzeigersinn hinzugefügt, aber Aspose.GIS korrigiert die Orientierung automatisch.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Schritt 4: Äußeren Ring zuweisen und inneren Ring zum Polygon hinzufügen
Zum Schluss verbinden wir den äußeren Ring mit dem Polygon und fügen dann den inneren Ring (das Loch) hinzu. Die Methode `AddInteriorRing` kann mehrfach aufgerufen werden, wenn Sie mehrere Löcher benötigen.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Tipps und bewährte Vorgehensweisen
- **Orientierung ist für die Lesbarkeit wichtig** – Während Aspose.GIS die Orientierung automatisch korrigiert, erleichtert das Beibehalten von äußeren Ringen im Uhrzeigersinn und inneren Ringen gegen den Uhrzeigersinn die Inspektion in GIS‑Viewern die Arbeit.  
- **Jeden Ring schließen** – Wiederholen Sie stets den ersten Koordinatenpunkt als letzten Punkt; das garantiert eine gültige geschlossene Form.  
- **Nach der Erstellung validieren** – Sie können `polygon.IsValid` aufrufen, um sicherzustellen, dass die Geometrie den OGC‑Standards entspricht, bevor Sie sie speichern.

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|-------|--------|-----|
| Loch wird im GIS‑Viewer nicht angezeigt | Orientierung des Innenrings ist umgekehrt | Stellen Sie sicher, dass Punkte in die entgegengesetzte Richtung des Außenrings (gegen den Uhrzeigersinn) hinzugefügt werden. |
| Ungültiger Polygon‑Fehler | Ringe nicht geschlossen (erste ≠ letzte Punkt) | Wiederholen Sie den ersten Punkt als letzten Punkt in jedem Ring (wie oben gezeigt). |
| Unerwartete leere Geometrie | Vergessen, `ExteriorRing` zuzuweisen, bevor Innenringe hinzugefügt werden | Setzen Sie zuerst `polygon.ExteriorRing` und rufen dann `AddInteriorRing` auf. |

## Häufig gestellte Fragen
### 1. Was ist Aspose.GIS?
Aspose.GIS ist eine .NET‑Bibliothek, die Entwicklern ermöglicht, mit Geodaten zu arbeiten, indem sie das Erstellen, Lesen und Manipulieren verschiedener geospatiale Dateiformate unterstützt.

### 2. Kann ich Aspose.GIS für kommerzielle Projekte verwenden?
Ja, Sie können Aspose.GIS sowohl für private als auch für kommerzielle Projekte nutzen, indem Sie eine Lizenz erwerben. Weitere Details finden Sie [hier](https://purchase.aspose.com/buy).

### 3. Gibt es eine kostenlose Testversion für Aspose.GIS?
Ja, Sie können eine kostenlose Testversion von Aspose.GIS unter [hier](https://releases.aspose.com/) erhalten.

### 4. Wo finde ich Support für Aspose.GIS?
Support für Aspose.GIS finden Sie im [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33).

### 5. Wie kann ich eine temporäre Lizenz für Aspose.GIS erhalten?
Eine temporäre Lizenz für Aspose.GIS erhalten Sie [hier](https://purchase.aspose.com/temporary-license/).

---

**Zuletzt aktualisiert:** 2026-04-03  
**Getestet mit:** Aspose.GIS 24.11 für .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}