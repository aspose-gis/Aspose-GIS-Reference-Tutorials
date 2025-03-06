---
title: Koordinatenkonvertierung mit Aspose.GIS
linktitle: Koordinaten konvertieren
second_title: Aspose.GIS .NET-API
description: Erfahren Sie, wie Sie Koordinaten mit Aspose.GIS für .NET konvertieren. Schritt-für-Schritt-Anleitung, Voraussetzungen und FAQs bereitgestellt.
weight: 25
url: /de/net/geometry-creation/convert-coordinates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Koordinatenkonvertierung mit Aspose.GIS

## Einführung
In diesem Tutorial tauchen wir mithilfe der leistungsstarken Aspose.GIS-Bibliothek für .NET in die Welt der geografischen Informationssysteme (GIS) ein. Aspose.GIS ist ein umfassendes Toolkit, das Entwicklern die mühelose Arbeit mit Geodaten ermöglicht. Unabhängig davon, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, führt Sie dieses Tutorial durch den Prozess der Verwendung von Aspose.GIS zur effektiven Konvertierung von Koordinaten.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Grundkenntnisse in C#: Um die bereitgestellten Codebeispiele zu verstehen und umzusetzen, ist die Vertrautheit mit der Programmiersprache C# unerlässlich.
  
2.  Installation von Aspose.GIS: Stellen Sie sicher, dass Sie die Aspose.GIS-Bibliothek für .NET heruntergeladen und installiert haben. Sie können es hier herunterladen[Aspose.GIS-Website](https://releases.aspose.com/gis/net/).

## Namespaces importieren
Bevor wir beginnen, importieren wir die erforderlichen Namespaces, um auf die Funktionen von Aspose.GIS zuzugreifen:
```csharp
using System;
using Aspose.Gis;
```

Lassen Sie uns das bereitgestellte Beispiel zum besseren Verständnis in mehrere Schritte unterteilen:
## Schritt 1: Starten Sie den Konvertierungsprozess
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
In dieser Zeile wird lediglich eine Meldung angezeigt, die den Beginn des Koordinatenkonvertierungsprozesses angibt.
## Schritt 2: In Dezimalgrade umrechnen
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 Hier konvertieren wir die Koordinaten (25,5, 45,5) mithilfe von in das Dezimalgradformat`AsPointText` Methode mit der`PointFormats.DecimalDegrees` Parameter. Das Ergebnis wird dann auf der Konsole ausgegeben.
## Schritt 3: Konvertieren Sie in Grad-Dezimalminuten
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
Dieser Schritt wandelt die Koordinaten in das Grad-Dezimal-Minutenformat um und druckt das Ergebnis aus.
## Schritt 4: Konvertieren Sie in Gradminuten und Sekunden
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
Ebenso konvertieren wir die Koordinaten in das Grad-Minuten-Sekunden-Format und zeigen die Ausgabe an.
## Schritt 5: In GeoRef konvertieren
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
Abschließend konvertieren wir die Koordinaten in das GeoRef-Format und drucken das Ergebnis aus.

## Abschluss
In diesem Tutorial haben wir den Prozess der Koordinatenkonvertierung mit Aspose.GIS für .NET untersucht. Indem Sie der Schritt-für-Schritt-Anleitung folgen und die Aspose.GIS-Bibliothek nutzen, können Sie räumliche Daten in Ihren .NET-Anwendungen effizient bearbeiten.
## FAQs
### Ist Aspose.GIS mit anderen Programmiersprachen kompatibel?
Aspose.GIS richtet sich in erster Linie an .NET-Entwickler, bietet jedoch durch Aspose.GIS für Java Interoperabilität mit Java.
### Kann ich Aspose.GIS vor dem Kauf testen?
 Ja, Sie können auf eine kostenlose Testversion von Aspose.GIS zugreifen[Webseite](https://releases.aspose.com/).
### Wie kann ich Unterstützung für Aspose.GIS erhalten?
 Sie können Hilfe im Aspose.GIS-Community-Forum suchen[Hier](https://forum.aspose.com/c/gis/33).
### Sind temporäre Lizenzen für Aspose.GIS verfügbar?
 Ja, temporäre Lizenzen sind bei erhältlich[temporäre Lizenzseite](https://purchase.aspose.com/temporary-license/).
### Wo kann ich Aspose.GIS kaufen?
 Sie können Aspose.GIS bei erwerben[Kaufseite](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
