---
title: Überprüfen Sie, ob die Geometrie eine andere enthält
linktitle: Überprüfen Sie, ob die Geometrie eine andere enthält
second_title: Aspose.GIS .NET-API
description: Entdecken Sie Aspose.GIS für .NET, eine robuste Bibliothek für die nahtlose Integration von Geodaten in Ihre .NET-Anwendungen.
type: docs
weight: 14
url: /de/net/geometry-analysis/check-geometry-contains-another/
---
## Einführung
Aspose.GIS für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, nahtlos mit Geodaten in ihren .NET-Anwendungen zu arbeiten. Unabhängig davon, ob Sie eine Kartenanwendung erstellen, Geodatenanalysen durchführen oder standortbasierte Funktionen in Ihre Software integrieren, Aspose.GIS vereinfacht den Prozess durch die Bereitstellung intuitiver APIs und robuster Funktionen.
## Voraussetzungen
Bevor Sie mit der Verwendung von Aspose.GIS für .NET beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
### 1. Einrichtung der .NET-Entwicklungsumgebung
Stellen Sie sicher, dass auf Ihrem Computer eine funktionierende .NET-Entwicklungsumgebung eingerichtet ist. Dazu gehört die ordnungsgemäße Installation und Konfiguration des .NET SDK.
### 2. Aspose.GIS-Installation
 Installieren Sie Aspose.GIS für .NET, indem Sie die Bibliothek von der Release-Seite herunterladen[Hier](https://releases.aspose.com/gis/net/) . Befolgen Sie die Installationsanweisungen in der Dokumentation[Hier](https://reference.aspose.com/gis/net/)um Aspose.GIS in Ihr Projekt zu integrieren.
### 3. Grundlegendes Verständnis von C#
Machen Sie sich mit der Programmiersprache C# vertraut, da Aspose.GIS für .NET hauptsächlich mit C# verwendet wird.

## Namespaces importieren
Importieren Sie in Ihrem C#-Projekt die erforderlichen Namespaces, um die Aspose.GIS-Funktionen zu nutzen:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt 1: Geometrieobjekte definieren
Definieren Sie zunächst die Geometrieobjekte mithilfe der Aspose.GIS-Klassen:
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## Schritt 2: Überprüfen Sie die räumliche Eingrenzung
Überprüfen Sie als Nächstes, ob eine Geometrie eine andere enthält:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // FALSCH
```
## Schritt 3: Definieren Sie eine andere Geometrie
Definieren Sie ein weiteres Geometrieobjekt:
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## Schritt 4: Überprüfen Sie die räumliche Eingrenzung erneut
Überprüfen Sie, ob die neu definierte Geometrie in der ersten Geometrie enthalten ist:
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // WAHR
```
## Schritt 5: Gleichwertige Funktionalität
 Verstehe das`a.SpatiallyContains(b)` ist äquivalent zu`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // WAHR
```

## Abschluss
Zusammenfassend stellt Aspose.GIS für .NET leistungsstarke Tools für den Umgang mit Geodaten in .NET-Anwendungen bereit. Wenn Sie diesem Leitfaden folgen und das bereitgestellte Beispiel verwenden, können Sie räumliche Eindämmungsprüfungen effizient durchführen und andere Geodatenfunktionen in Ihren Projekten nutzen.
## FAQs
### F1: Ist Aspose.GIS mit .NET Core kompatibel?
A: Ja, Aspose.GIS unterstützt .NET Core vollständig, sodass Sie Geodatenanwendungen auf verschiedenen Plattformen entwickeln können.
### F2: Kann ich mit Aspose.GIS Geodatenanalysen durchführen?
A: Absolut, Aspose.GIS bietet verschiedene Funktionalitäten für die Geoanalyse, einschließlich räumlicher Abfragen, Entfernungsberechnungen und Geometriemanipulationen.
### F3: Wie häufig werden Updates für Aspose.GIS veröffentlicht?
A: Aspose.GIS veröffentlicht regelmäßig Updates, um die Leistung zu verbessern, neue Funktionen hinzuzufügen und alle gemeldeten Probleme zu beheben. Sie können auf dem Laufenden bleiben, indem Sie die Release-Seite besuchen.
### F4: Gibt es ein Community-Forum für Aspose.GIS-Benutzer?
A: Ja, Sie können dem Aspose.GIS-Community-Forum beitreten[Hier](https://forum.aspose.com/c/gis/33) um mit anderen Benutzern in Kontakt zu treten, Fragen zu stellen und Ihre Erfahrungen auszutauschen.
### F5: Kann ich Aspose.GIS vor dem Kauf testen?
 A: Natürlich können Sie Aspose.GIS erkunden, indem Sie die kostenlose Testversion von herunterladen[Hier](https://releases.aspose.com/).