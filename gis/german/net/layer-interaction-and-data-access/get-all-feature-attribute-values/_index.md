---
date: 2026-01-05
description: Erfahren Sie, wie Sie Shapefiles in C# mit Aspose.GIS für .NET lesen,
  alle Attributwerte von Features abrufen und Attribute effizient ausgeben.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Shapefile in C# lesen – Alle Attributwerte der Features abrufen
url: /de/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Alle Feature‑Attributwerte abrufen

## Einführung
Willkommen in der Welt der Geodaten‑Entwicklung mit Aspose.GIS für .NET! In diesem Tutorial lernen Sie **wie man Shapefile in C# liest** und für jedes Feature jeden Attributwert abruft. Egal, ob Sie eine Karten‑App bauen oder räumliche Daten stapelweise verarbeiten – das Extrahieren von Attributen ist essenziell. Lassen Sie uns eintauchen und den Code in Aktion sehen.

## Schnellantworten
- **Was macht dieser Code?** Er öffnet ein Shapefile und liest alle, mehrere oder ausgegebene Attributwerte jedes Features.  
- **Welche Bibliothek wird benötigt?** Aspose.GIS für .NET (kompatibel mit .NET Framework und .NET Core).  
- **Brauche ich eine Lizenz?** Eine temporäre Lizenz reicht für Tests; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Kann ich andere Formate lesen?** Ja – dieselbe API unterstützt GeoJSON, KML und viele weitere.  
- **Wie gebe ich Attribute aus?** Verwenden Sie `feature.GetValuesDump()`, um ein flexibles Objekt‑Array zu erhalten.

## Was bedeutet „read shapefile C#“?
Ein Shapefile in C# zu lesen bedeutet, die .shp‑Datei mit einer GIS‑Bibliothek zu öffnen, über ihre Vektor‑Features zu iterieren und die Attributdaten aus der zugehörigen .dbf‑Datei zuzugreifen. Aspose.GIS abstrahiert die low‑level Dateiverarbeitung, sodass Sie sich auf die benötigten Attributwerte konzentrieren können.

## Warum Aspose.GIS zum Lesen von Attributen verwenden?
- **Einfache API** – intuitive Methoden wie `GetValues` und `GetValuesDump`.  
- **Plattformübergreifend** – funktioniert unter Windows, Linux und macOS mit .NET Core.  
- **Umfangreiche Formatunterstützung** – verarbeitet Shapefile, GeoJSON, GML und mehr ohne zusätzliche Plugins.  
- **Leistungsoptimiert** – schnelle Iteration über große Datensätze.

## Voraussetzungen
Bevor wir diese spannende Reise beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Aspose.GIS für .NET: Laden Sie die Bibliothek von der [Aspose.GIS für .NET Download‑Seite](https://releases.aspose.com/gis/net/) herunter und installieren Sie sie.  
- Entwicklungsumgebung: Richten Sie eine .NET‑Entwicklungsumgebung ein, z. B. Visual Studio.  
- Shapefile: Haben Sie ein Beispiel‑Shapefile (z. B. „InputShapeFile.shp“) im Dokumenten‑Verzeichnis bereit.

## Namespaces importieren
Importieren Sie in Ihrem C#‑Code die notwendigen Namespaces, um die Funktionen von Aspose.GIS zu nutzen:
```csharp
using System;
using Aspose.Gis;
```

## Schritt 1: Das Dokumenten‑Verzeichnis festlegen
```csharp
string dataDir = "Your Document Directory";
```
Ersetzen Sie „Your Document Directory“ durch den tatsächlichen Pfad, in dem sich Ihr Shapefile befindet.

## Schritt 2: Den VectorLayer öffnen
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
In diesem Schritt wird das Shapefile mit Aspose.GIS geöffnet, wobei Dateipfad und Format (hier Shapefile) angegeben werden.

## Schritt 3: Alle Feature‑Attributwerte abrufen
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
Das Snippet zeigt **wie man Attribute** für jedes Feature liest, indem sie in ein festes Array geladen werden.

## Schritt 4: Mehrere Feature‑Attributwerte abrufen
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Hier demonstrieren wir **wie man bestimmte Attributwerte** liest, wenn nur ein Teil der Felder benötigt wird.

## Schritt 5: Attributwerte als Objekt‑Dump abrufen
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Dieser letzte Schritt zeigt **wie man Attribute** mit `GetValuesDump()` ausgibt, was eine flexible Sammlung zurückgibt, die Sie inspizieren oder serialisieren können.

## Häufige Probleme und Lösungen
- **Array‑Größen‑Mismatch** – Stellen Sie sicher, dass das an `GetValues` übergebene Array der erwarteten Anzahl von Attributen entspricht; sonst erhalten Sie `null`‑Einträge.  
- **Datei nicht gefunden** – Prüfen Sie, ob `dataDir` auf den richtigen Ordner zeigt und der Shapefile‑Name exakt geschrieben ist.  
- **Lizenz‑Ausnahme** – Wenn ein Lizenzfehler auftritt, wenden Sie vor dem Aufruf von API‑Methoden eine temporäre oder vollständige Lizenz an.

## Häufig gestellte Fragen
### Ist Aspose.GIS mit .NET Core kompatibel?
Ja, Aspose.GIS ist vollständig mit .NET Core kompatibel und ermöglicht die Entwicklung plattformübergreifender Anwendungen.

### Kann ich mit Aspose.GIS verschiedene GIS‑Dateiformate verwenden?
Absolut! Aspose.GIS unterstützt diverse Formate, darunter Shapefile, GeoJSON und weitere.

### Gibt es ein Community‑Forum für den Aspose.GIS‑Support?
Ja, Sie finden Hilfe und können sich mit der Aspose.GIS‑Community im [Support‑Forum](https://forum.aspose.com/c/gis/33) austauschen.

### Wie kann ich eine temporäre Lizenz für Aspose.GIS erhalten?
Eine temporäre Lizenz für Testzwecke erhalten Sie [hier](https://purchase.aspose.com/temporary-license/).

### Wo finde ich die ausführliche Dokumentation für Aspose.GIS?
Die umfassende Dokumentation steht [hier](https://reference.aspose.com/gis/net/) zur Verfügung.

### Wie rufe ich nur das Attribut „Name“ jedes Features ab?
Verwenden Sie `GetValues` mit einem Array der Größe eins und übergeben Sie den Index des Feldes „Name“ oder rufen Sie direkt `feature["Name"]` auf.

### Was ist der Unterschied zwischen `GetValues` und `GetValuesDump`?
`GetValues` füllt ein vorab zugewiesenes Array mit Rohwerten, während `GetValuesDump` ein Objekt‑Array zurückgibt, das ohne vorheriges Kenntnis des Schemas enumeriert werden kann.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-01-05  
**Getestet mit:** Aspose.GIS für .NET (neueste Version)  
**Autor:** Aspose  

---