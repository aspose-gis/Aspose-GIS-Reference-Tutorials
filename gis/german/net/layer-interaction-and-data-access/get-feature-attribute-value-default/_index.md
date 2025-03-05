---
title: Feature-Attributwert abrufen (Standard)
linktitle: Feature-Attributwert abrufen (Standard)
second_title: Aspose.GIS .NET-API
description: Nutzen Sie die Leistungsfähigkeit von Aspose.GIS für .NET! Mit dieser Schritt-für-Schritt-Anleitung können Sie Feature-Attributwerte mühelos abrufen und bearbeiten. Laden Sie jetzt Ihre Testversion herunter!
type: docs
weight: 14
url: /de/net/layer-interaction-and-data-access/get-feature-attribute-value-default/
---
## Einführung
Willkommen in der Welt von Aspose.GIS für .NET! In diesem umfassenden Leitfaden befassen wir uns mit den Feinheiten des Abrufens von Feature-Attributwerten mithilfe der leistungsstarken Funktionen von Aspose.GIS. Unabhängig davon, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, bietet Ihnen dieses Tutorial eine Schritt-für-Schritt-Anleitung, die sicherstellt, dass Sie das volle Potenzial dieses bemerkenswerten Tools ausschöpfen.
## Voraussetzungen
Bevor wir uns auf dieses Programmierabenteuer einlassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Grundkenntnisse in C# und .NET Framework.
-  Aspose.GIS für .NET installiert. Wenn nicht, laden Sie es herunter von[Hier](https://releases.aspose.com/gis/net/).
- Ein Code-Editor wie Visual Studio, der nahtlos mitverfolgt werden kann.
## Namespaces importieren
Stellen Sie in Ihrem C#-Projekt sicher, dass Sie die erforderlichen Namespaces einschließen:
```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Lassen Sie uns nun jedes Beispiel in eine Reihe leicht verständlicher Schritte unterteilen.
## Feature-Attributwert abrufen (Standard)
### Schritt 1: Richten Sie die Umgebung ein
Beginnen Sie mit der Definition des Pfads zu Ihrem Dokumentenverzeichnis:
```csharp
string dataDir = "Your Document Directory";
```
### Schritt 2: Erstellen Sie eine GeoJson-Ebene
Erstellen Sie eine GeoJson-Ebene und definieren Sie ein Attribut mit Standardwerten:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data1_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Integer);
    attribute.CanBeNull = true;
    attribute.CanBeUnset = true;
    layer.Attributes.Add(attribute);
```
### Schritt 3: Konstruieren Sie ein Feature
Konstruieren Sie ein Feature mithilfe des definierten Attributs:
```csharp
    Feature feature = layer.ConstructFeature();
```
### Schritt 4: Werte abrufen
Rufen Sie Attributwerte mit verschiedenen Szenarios ab:
```csharp
    int? nullValue = feature.GetValueOrDefault<int?>("attribute"); // Wert == null
    var defValue1 = feature.GetValueOrDefault<int?>("attribute", 10); // Wert == 10
    var defValue2 = feature.GetValueOrDefault("attribute", 25); // Wert == 10
    Console.WriteLine($"'{nullValue}' vs '{defValue1}' vs '{defValue2}'");
}
```
## Standardwerte festlegen
### Schritt 1: Erstellen Sie eine weitere GeoJson-Ebene
Wiederholen Sie den Vorgang mit einer anderen GeoJson-Ebene und einem doppelten Attribut:
```csharp
using (var layer = Drivers.GeoJson.CreateLayer(dataDir + "data2_out.json"))
{
    var attribute = new FeatureAttribute("attribute", AttributeDataType.Double);
    attribute.CanBeNull = false;
    attribute.CanBeUnset = false;
    attribute.DefaultValue = 100;
    layer.Attributes.Add(attribute);
```
### Schritt 2: Konstruieren Sie (erneut) ein Feature
```csharp
    Feature feature = layer.ConstructFeature();
```
### Schritt 3: Werte abrufen und festlegen
Attributwerte abrufen und festlegen und Standardwerte anzeigen:
```csharp
    double defValue1 = feature.GetValueOrDefault<double>("attribute"); // Wert == 100
    var defValue2 = feature.GetValueOrDefault("attribute"); // Wert == 100
    feature.SetValue("attribute", 50);
    var newValue = feature.GetValueOrDefault<double>("attribute"); // Wert == 50
    Console.WriteLine($"'{defValue1}' vs '{defValue2}' vs '{newValue}'");
}
```
Glückwunsch! Sie haben die Leistungsfähigkeit von Aspose.GIS für .NET beim Abrufen und Bearbeiten von Feature-Attributwerten erfolgreich genutzt.
## Abschluss
In diesem Tutorial haben wir die Nuancen des Abrufens von Feature-Attributwerten mit Aspose.GIS für .NET untersucht. Mit seiner intuitiven API und den robusten Funktionen eröffnet Aspose.GIS eine Welt voller Möglichkeiten für die GIS-Entwicklung in .NET-Umgebungen.
## Häufig gestellte Fragen
### Ist Aspose.GIS mit .NET Core kompatibel?
Ja, Aspose.GIS ist vollständig kompatibel mit .NET Core und bietet plattformübergreifende Unterstützung.
### Kann ich Aspose.GIS für kommerzielle Projekte verwenden?
Absolut! Aspose.GIS wird mit einer kommerziellen Lizenz geliefert, die Ihnen die uneingeschränkte Nutzung in Ihren kommerziellen Anwendungen ermöglicht.
### Wo finde ich zusätzliche Unterstützung und Ressourcen?
 Besuche den[Aspose.GIS-Forum](https://forum.aspose.com/c/gis/33) für Community-Unterstützung und erkunden Sie die[Dokumentation](https://reference.aspose.com/gis/net/) für ausführliche Informationen.
### Gibt es eine kostenlose Testversion?
 Ja, Sie können Aspose.GIS mit einer kostenlosen Testversion erkunden. Lade es herunter[Hier](https://releases.aspose.com/).
### Wie erhalte ich eine temporäre Lizenz zu Testzwecken?
 Für temporäre Lizenzen besuchen Sie bitte[Hier](https://purchase.aspose.com/temporary-license/).