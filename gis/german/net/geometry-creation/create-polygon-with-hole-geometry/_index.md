---
title: Erstellen Sie mit Aspose.GIS ein Polygon mit Lochgeometrie
linktitle: Erstellen Sie ein Polygon mit Lochgeometrie
second_title: Aspose.GIS .NET-API
description: Erfahren Sie, wie Sie mit Aspose.GIS für .NET Polygone mit Lochgeometrie erstellen. Schritt-für-Schritt-Anleitung mit Codebeispielen.
weight: 13
url: /de/net/geometry-creation/create-polygon-with-hole-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen Sie mit Aspose.GIS ein Polygon mit Lochgeometrie

## Einführung
In diesem Tutorial führen wir den Prozess der Erstellung eines Polygons mit Lochgeometrie mithilfe von Aspose.GIS für .NET durch. Aspose.GIS ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, in ihren .NET-Anwendungen mit Geodaten zu arbeiten. 
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Aspose.GIS für .NET-Bibliothek: Sie können sie herunterladen unter[Hier](https://releases.aspose.com/gis/net/).
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine Entwicklungsumgebung mit Visual Studio oder einer anderen installierten .NET-IDE eingerichtet haben.
## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces importieren, um mit Aspose.GIS-Funktionen arbeiten zu können. So geht's:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Fahren wir nun mit der Erstellung eines Polygons mit Lochgeometrie mit Aspose.GIS für .NET fort.
## Schritt 1: Polygonobjekt erstellen
```csharp
Polygon polygon = new Polygon();
```
## Schritt 2: Außenring definieren
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## Schritt 3: Innenring (Loch) definieren
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## Schritt 4: Außenring zuweisen und Innenring zum Polygon hinzufügen
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.GIS für .NET ein Polygon mit Lochgeometrie erstellen. Dieses Wissen wird für verschiedene Geodatenanwendungen von Vorteil sein, bei denen solche Geometrien unerlässlich sind.
## FAQs
### 1. Was ist Aspose.GIS?
Aspose.GIS ist eine .NET-Bibliothek, die es Entwicklern ermöglicht, mit Geodaten zu arbeiten und verschiedene Geodatenformate zu erstellen, zu lesen und zu bearbeiten.
### 2. Kann ich Aspose.GIS für kommerzielle Projekte verwenden?
 Ja, Sie können Aspose.GIS sowohl für persönliche als auch für kommerzielle Projekte verwenden, indem Sie eine Lizenz erwerben. Besuchen[Hier](https://purchase.aspose.com/buy) für mehr Details.
### 3. Gibt es eine kostenlose Testversion für Aspose.GIS?
 Ja, Sie können eine kostenlose Testversion von Aspose.GIS nutzen[Hier](https://releases.aspose.com/).
### 4. Wo finde ich Unterstützung für Aspose.GIS?
 Unterstützung für Aspose.GIS finden Sie auf der[Aspose.GIS-Forum](https://forum.aspose.com/c/gis/33).
### 5. Wie kann ich eine temporäre Lizenz für Aspose.GIS erhalten?
 Eine temporäre Lizenz für Aspose.GIS erhalten Sie bei[Hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
