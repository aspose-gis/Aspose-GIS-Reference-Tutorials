---
date: 2026-09-05
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET einen Innenring eines Polygons
  mit einem Loch erstellen. Dieser Leitfaden zeigt Ihnen, wie Sie einem Polygon ein
  Loch hinzufügen und mit Daten arbeiten.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Polygon mit Loch‑Geometrie erstellen
og_description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET einen Innenring eines
  Polygons mit einem Loch erstellen. Dieser Leitfaden zeigt Ihnen, wie Sie einem Polygon
  ein Loch hinzufügen und mit Daten arbeiten.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Erstellen eines Innenrings eines Polygons mit einem Loch mithilfe von Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Erstellen eines Innenrings eines Polygons mit einem Loch mithilfe von Aspose.GIS
url: /de/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen eines Polygon‑Innenrings mit einem Loch mithilfe von Aspose.GIS

## Einführung
In diesem Tutorial lernen Sie, **einen Polygon‑Innenring** zu **erstellen**, der ein Loch enthält, mithilfe von Aspose.GIS für .NET. Egal, ob Sie eine Mapping‑Anwendung bauen, räumliche Analysen durchführen oder Daten für GIS‑Dienste vorbereiten – das Einbetten eines Lochs in ein Polygon ist eine Kernkompetenz. Wir führen Sie durch den gesamten Workflow – von der Einrichtung der Entwicklungsumgebung bis zur Erzeugung eines gültigen Polygon‑Objekts, das in jedem unterstützten Geodatenformat gespeichert werden kann.

## Schnelle Antworten
- **Was bedeutet „Polygon mit Loch erstellen“?** Es bedeutet, ein Polygon zu bauen, das einen oder mehrere Innenringe (Löcher) enthält, die vom Flächeninhalt ausgeschlossen werden.  
- **Welche Bibliothek übernimmt das?** Aspose.GIS für .NET bietet vollständige Unterstützung für Außen‑ und Innenringe.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Entwicklung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Wie lange dauert das?** In der Regel weniger als 10 Minuten für Implementierung und Test.

## Wie man ein Loch zu einem Polygon mit Aspose.GIS hinzufügt
Laden Sie Ihre GIS‑Umgebung, definieren Sie einen Außenring und fügen Sie dann einen oder mehrere Innenringe hinzu. Aspose.GIS orientiert die Ringe automatisch und validiert die Geometrie, sodass Sie sich auf die Koordinaten konzentrieren können, die das gewünschte Loch darstellen.

## Was ist ein Polygon‑Innenring?
Ein **Polygon‑Innenring** ist eine innere Grenze, die Fläche vom äußeren Polygon abzieht.  
Sie erstellen ihn, indem Sie eine geschlossene Punktsequenz definieren, die Aspose.GIS als Loch behandelt und die bei Flächenberechnung oder Darstellung ausgeschlossen wird.

## Warum einen Polygon‑Innenring mit Aspose.GIS erstellen?
Aspose.GIS validiert und korrigiert die Ring‑Orientierung in unter 5 ms für typische 200‑Punkte‑Polygone und eliminiert damit den Bedarf an eigenem Validierungscode. Es unterstützt zudem **30+ Geodaten‑Dateiformate** (Shapefile, GeoJSON, GML, KML usw.) und kann Polygone mit bis zu 10.000 Punkten verarbeiten, ohne die gesamte Datei in den Speicher zu laden – das bietet sowohl Geschwindigkeit als auch Skalierbarkeit.

## Praxisbeispiele für Polygone mit Löchern
1. **Grundstück mit einem internen See** – der See wird als Loch modelliert, sodass er nicht in die Flächenberechnung des Grundstücks einfließt.  
2. **Gebäudeflächen mit Innenhöfen** – der Innenhof wird vom Gebäudefußabdruck ausgeschlossen.  
3. **Geschützte Zonen innerhalb eines größeren Naturschutzgebiets** – Sie können eingeschränkte Abschnitte ausschließen, ohne separate Layer zu erstellen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Aspose.GIS für .NET Bibliothek: Sie können sie von der **Aspose.GIS für .NET Download‑Seite**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)) herunterladen.  
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine Entwicklungsumgebung mit Visual Studio oder einer anderen .NET‑IDE eingerichtet haben.

## Namespaces importieren
Der `Aspose.Gis`‑Namespace enthält alle Geometrietypen, die Sie benötigen, einschließlich `Polygon`, `LinearRing` und Hilfsmethoden zur Validierung.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Nun fahren wir fort, eine Polygon‑mit‑Loch‑Geometrie mit Aspose.GIS für .NET zu erstellen.

## Schritt 1: Polygon‑Objekt erstellen
`Polygon` ist der Geometrietyp von Aspose.GIS, der ein planares Polygon mit optionalen Innenringen darstellt. Wir beginnen mit der Instanziierung eines leeren `Polygon`‑Objekts, das später sowohl den Außen‑ als auch den Innenring aufnehmen wird.

```csharp
Polygon polygon = new Polygon();
```

## Schritt 2: Außenring definieren
`LinearRing` ist die Klasse, die sowohl für Außen‑ als auch für Innengrenzen verwendet wird. Der Außenring definiert die äußere Begrenzung des Polygons. Fügen Sie Punkte im Uhrzeigersinn hinzu, um eine geschlossene Form zu erzeugen.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Schritt 3: Innenring (Loch) definieren
`LinearRing` repräsentiert ebenfalls Innenringe. Der Innenring ist das **Loch**, das vom Polygon‑Flächeninhalt ausgeschlossen wird. Punkte werden typischerweise gegen den Uhrzeigersinn hinzugefügt, aber Aspose.GIS kümmert sich automatisch um die Orientierung.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Schritt 4: Außenring zuweisen und Innenring zum Polygon hinzufügen
Die Methode `AddInteriorRing` fügt einem `Polygon` einen oder mehrere Innenringe hinzu. Rufen Sie sie auf, nachdem Sie die Eigenschaft `ExteriorRing` gesetzt haben; Sie können den Aufruf wiederholen, um mehrere Löcher hinzuzufügen.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Tipps und bewährte Verfahren
- **Orientierung ist wichtig für die Lesbarkeit** – obwohl Aspose.GIS die Orientierung automatisch korrigiert, erleichtert das Beibehalten von Außenringen im Uhrzeigersinn und Innenringen gegen den Uhrzeigersinn die Inspektion der Geometrie in GIS‑Betrachtern.  
- **Jeden Ring schließen** – wiederholen Sie stets die erste Koordinate als letzte Punkt; das garantiert eine gültige geschlossene Form.  
- **Nach der Erstellung validieren** – Sie können `polygon.IsValid` aufrufen, um sicherzustellen, dass die Geometrie den OGC‑Standards entspricht, bevor Sie sie speichern.

## Häufige Probleme und Lösungen
| Problem | Grund | Lösung |
|-------|--------|-----|
| Loch wird im GIS‑Betrachter nicht angezeigt | Orientierung des Innenrings ist umgekehrt | Stellen Sie sicher, dass die Punkte in die entgegengesetzte Richtung des Außenrings (gegen den Uhrzeigersinn) hinzugefügt werden. |
| Polygon‑Ungültigkeitsfehler | Ringe nicht geschlossen (erste ≠ letzte Koordinate) | Wiederholen Sie den ersten Punkt als letzten Punkt in jedem Ring (wie oben gezeigt). |
| Unerwartete leere Geometrie | `ExteriorRing` wurde nicht zugewiesen, bevor Innenringe hinzugefügt wurden | Setzen Sie zuerst `polygon.ExteriorRing`, dann rufen Sie `AddInteriorRing` auf. |

## Häufig gestellte Fragen
### 1. Was ist Aspose.GIS?
Aspose.GIS ist eine .NET‑Bibliothek, die Entwicklern die Arbeit mit Geodaten ermöglicht, sodass sie verschiedene Geodaten‑Dateiformate erstellen, lesen und manipulieren können.

### 2. Kann ich Aspose.GIS für kommerzielle Projekte verwenden?
Ja, Sie können Aspose.GIS sowohl für private als auch für kommerzielle Projekte nutzen, indem Sie eine Lizenz erwerben. Besuchen Sie die **Aspose.GIS Kauf‑Seite**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) für weitere Details.

### 3. Gibt es eine kostenlose Testversion von Aspose.GIS?
Ja, Sie können eine kostenlose Testversion von Aspose.GIS von der **Aspose.GIS kostenlose Test‑Download‑Seite**([https://releases.aspose.com/](https://releases.aspose.com/)) erhalten.

### 4. Wo finde ich Support für Aspose.GIS?
Support für Aspose.GIS finden Sie im [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33).

### 5. Wie kann ich eine temporäre Lizenz für Aspose.GIS erhalten?
Eine temporäre Lizenz für Aspose.GIS erhalten Sie auf der **Aspose.GIS temporäre Lizenz‑Seite**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**Last Updated:** 2026-09-05  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Verwandte Tutorials

- [Wie man Polygon‑Geometrie mit Aspose.GIS für .NET erstellt](/gis/net/geometry-creation/create-polygon-geometry/)
- [Erfahren Sie, wie Sie MultiPolygon‑Geometrie mit Aspose.GIS erstellen](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Polygon in Linie konvertieren mit Aspose.GIS für .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}