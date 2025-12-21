---
date: 2025-12-21
description: Erfahren Sie, wie Sie einen Vektor‑Layer erstellen, die Linearisationstoleranz
  festlegen und ein Feature zum Layer hinzufügen, indem Sie Aspose.GIS für .NET verwenden.
  Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung, um GeoJSON‑Dateien zu exportieren.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Vektorlayer erstellen und Linearisationstoleranz mit Aspose.GIS für .NET festlegen
url: /de/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektorlayer erstellen und Linearisationstoleranz mit Aspose.GIS für .NET festlegen

## Einführung
Wenn Sie **Vektorlayer**‑Dateien erstellen, die Kurvenpräzision steuern und das Ergebnis als GeoJSON‑Dokument exportieren möchten, macht Aspose.GIS für .NET das ganz einfach. In diesem Tutorial lernen Sie, wie Sie GeoJSON‑Optionen konfigurieren, die Linearisationstoleranz festlegen und **Feature zum Layer** hinzufügen – und das alles mit sauberem, produktionsreifem Code.

## Schnellantworten
- **Was bedeutet „Vektorlayer erstellen“?** Es erzeugt einen neuen GIS‑Vektordatensatz (z. B. eine GeoJSON‑Datei), der Geometrien und Attribute speichern kann.  
- **Wie wird die Toleranz festgelegt?** Verwenden Sie die Eigenschaft `LinearizationTolerance` von `GeoJsonOptions`.  
- **Kann ich eine GeoJSON‑Datei exportieren?** Ja – erstellen Sie einfach einen `VectorLayer` mit dem Treiber `Drivers.GeoJson`.  
- **Benötige ich eine Lizenz?** Eine gültige Aspose.GIS‑Lizenz schaltet alle Funktionen frei; eine temporäre Lizenz reicht für die Evaluierung.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Was bedeutet „Vektorlayer erstellen“?
Einen Vektorlayer zu erstellen bedeutet, einen neuen GIS‑Container (wie eine GeoJSON‑Datei) zu initialisieren, der geometrische Features wie Punkte, Linien und Polygone aufnehmen kann. Dieser Layer wird zum Ziel für jede Geometrie, die Sie erzeugen, und für alle Attribute, die Sie anhängen.

## Warum GeoJSON‑Optionen konfigurieren?
Durch das Konfigurieren der GeoJSON‑Optionen – insbesondere der **Linearisationstoleranz** – wird sichergestellt, dass gekrümmte Geometrien (z. B. `CircularString`) mit einer Genauigkeit approximiert werden, die den Anforderungen Ihrer Anwendung entspricht. Dieser Schritt ist entscheidend, wenn Sie später **GeoJSON‑Datei exportieren** möchten, um sie in Web‑Karten oder räumlichen Analysen zu verwenden.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Visual Studio** installiert (jede aktuelle Version).  
2. **Aspose.GIS‑Lizenz** (oder einen temporären Evaluierungsschlüssel).  
3. **Aspose.GIS für .NET**‑Bibliothek heruntergeladen und in Ihrem Projekt referenziert.  
4. Grundlegende Kenntnisse in **C#**.

## Namespaces importieren
Importieren Sie zuerst die erforderlichen Namespaces, damit der Compiler die GIS‑Klassen findet:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: GeoJSON‑Optionen konfigurieren (wie die Toleranz festzulegen)
Wir erstellen ein `GeoJsonOptions`‑Objekt und geben Aspose.GIS an, wie nah die linearisierten Geometrien an die Originalkurve herankommen sollen.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Schritt 2: Ausgabepfad festlegen (wie GeoJSON exportieren)
Geben Sie an, wo die resultierende Datei gespeichert werden soll. Ersetzen Sie den Platzhalter durch Ihren tatsächlichen Ordner.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Schritt 3: **Vektorlayer erstellen** mit den konfigurierten Optionen
Jetzt **erstellen wir den Vektorlayer** mithilfe der Methode `VectorLayer.Create`. Der `using`‑Block sorgt für die ordnungsgemäße Freigabe der Ressourcen.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Schritt 4: Geometrie konstruieren (z. B. einen CircularString)
Hier bauen wir eine Beispielgeometrie – einen `CircularString`. Sie können dies durch jede gültige WKT‑Geometrie ersetzen.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Schritt 5: **Feature zum Layer hinzufügen** und speichern
Abschließend erstellen wir ein Feature, weisen die Geometrie zu und fügen es dem Layer hinzu. Dies ist der Kern der **add feature to layer**‑Operation.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Wenn der `using`‑Block endet, wird der Layer automatisch in die in `path` definierte Datei geschrieben, sodass Sie eine sofort einsetzbare GeoJSON‑Datei erhalten.

## Häufige Probleme & Tipps
- **Falscher Pfad** – Stellen Sie sicher, dass das Verzeichnis existiert und Sie Schreibrechte haben.  
- **Toleranz zu niedrig** – Eine sehr kleine `LinearizationTolerance` kann die Dateigröße dramatisch erhöhen. Passen Sie sie an Ihre Genauigkeitsanforderungen an.  
- **Lizenzfehler** – Wenn Lizenzwarnungen erscheinen, prüfen Sie, ob die Lizenzdatei vor irgendeinem Aufruf von Aspose.GIS korrekt geladen wurde.

## Häufig gestellte Fragen

**F: Ist Aspose.GIS für .NET mit anderen .NET‑Frameworks kompatibel?**  
A: Ja, es funktioniert mit .NET Framework, .NET Core und .NET 5/6/7.

**F: Kann ich Aspose.GIS in kommerziellen Projekten einsetzen?**  
A: Absolut. Eine kommerzielle Lizenz entfernt alle Evaluierungsbeschränkungen.

**F: Unterstützt Aspose.GIS neben GeoJSON noch weitere GIS‑Formate?**  
A: Ja, es unterstützt Shapefile, KML, GML und viele weitere.

**F: Gibt es eine Testversion?**  
A: Sie können eine kostenlose Testversion von der Aspose‑Website herunterladen.

**F: Wo bekomme ich Support?**  
A: Nutzen Sie die Aspose‑Foren oder den Support‑Link im Ressourcen‑Abschnitt.

## Fazit
Durch Befolgen dieser Schritte wissen Sie jetzt, wie Sie **Vektorlayer erstellen**, die Linearisationstoleranz konfigurieren und **Feature zum Layer hinzufügen** können, um nahtlos **GeoJSON‑Dateien exportieren** zu können. Erkunden Sie weitere Geometrietypen und die Handhabung von Attributen, um das volle Potenzial von Aspose.GIS in Ihren .NET‑GIS‑Projekten auszuschöpfen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

---