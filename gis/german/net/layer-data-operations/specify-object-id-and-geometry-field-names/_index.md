---
date: 2026-01-02
description: Erfahren Sie, wie Sie ein Punkt-Feature hinzufügen, Feldnamen festlegen
  und die Objekt-ID mit Aspose.GIS für .NET auslesen. Schritt‑für‑Schritt‑Anleitung
  für Entwickler.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: Punkt-Feature hinzufügen und Objekt-ID‑ und Geometriefeldnamen angeben
url: /de/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Punkt-Feature hinzufügen und Objekt-ID- und Geometriefeldnamen festlegen

## Einführung
Eine Reise in das Reich der Geoinformationssysteme (GIS) mit Aspose.GIS für .NET eröffnet Entwicklern und Enthusiasten eine Welt voller Möglichkeiten. In diesem Tutorial **lernen Sie, wie man ein Punkt-Feature hinzufügt** und gleichzeitig **Feldnamen festlegt** sowie **Objekt‑ID‑Werte liest**, was Ihnen die vollständige Kontrolle über Ihre räumlichen Daten gibt.

## Schnelle Antworten
- **Was ist der Hauptzweck dieses Leitfadens?** Zu zeigen, wie man ein Punkt-Feature hinzufügt und Objekt‑ID‑ und Geometriefeldnamen konfiguriert.  
- **Welche Bibliothek wird verwendet?** Aspose.GIS für .NET.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar; für die Produktion ist eine Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Kann ich die Objekt‑ID nach dem Einfügen lesen?** Ja – das Tutorial zeigt, wie man die Objekt‑ID aus dem Layer liest.

## Voraussetzungen
Bevor Sie in das Tutorial eintauchen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
- Aspose.GIS für .NET: Laden Sie die Bibliothek von [hier](https://releases.aspose.com/gis/net/) herunter und installieren Sie sie.
- Dokumentenverzeichnis: Richten Sie ein Verzeichnis für Ihre Dokumente ein, um die Geodatenbanken zu speichern.
- .NET‑Umgebung: Stellen Sie sicher, dass Sie eine funktionierende .NET‑Umgebung haben.

## Namespaces importieren
Um loszulegen, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Diese Namespaces stellen die wesentlichen Klassen und Methoden für die Interaktion mit Aspose.GIS für .NET bereit.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Schritt 1: Punkt-Feature hinzufügen und Objekt-ID- und Geometriefeldnamen festlegen
In diesem Schritt lernen Sie, wie Sie die Objekt‑ID‑ und Geometriefeldnamen für Ihre GIS‑Daten festlegen. Dies ist entscheidend für eine effiziente Datenverwaltung und dafür, später **die Objekt‑ID lesen** zu können.

### Schritt 1.1: Dokumentverzeichnis festlegen
Starten Sie, indem Sie den Pfad zu Ihrem Dokumentverzeichnis definieren:

```csharp
string dataDir = "Your Document Directory";
```

### Schritt 1.2: GeoDatabase erstellen und Optionen definieren
Erstellen Sie eine GeoDatabase mit den gewünschten **set field names** für Objekt‑ID und Geometrie:

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### Schritt 1.3: Einen Layer erstellen und hinzufügen
Erstellen Sie einen Layer innerhalb der GeoDatabase und fügen Sie ein Feature hinzu, das eine Punktgeometrie darstellt:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Schritt 1.4: Layer öffnen und Daten abrufen
Öffnen Sie den Layer und rufen Sie das Feature ab, das Sie gerade hinzugefügt haben. Dies demonstriert, wie man **die Objekt‑ID** aus dem Datensatz liest:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Warum benutzerdefinierte Feldnamen festlegen?
Die Anpassung der Objekt‑ID‑ und Geometriefeldnamen bietet Ihnen Flexibilität bei der Integration in bestehende Datenbanken oder bei der Einhaltung von Namenskonventionen, die von nachgelagerten Anwendungen gefordert werden. Außerdem wird die Daten selbstbeschreibender, was Wartung und Zusammenarbeit vereinfacht.

## Häufige Fallstricke und Fehlersuche
- **Fehlendes Verzeichnis** – Stellen Sie sicher, dass `dataDir` auf einen vorhandenen Ordner zeigt; andernfalls wirft `Dataset.Create` eine Ausnahme.
- **Konflikte bei Feldnamen** – Wenn ein Feld mit demselben Namen bereits in der Geodatenbank existiert, schlägt die Erstellung fehl. Wählen Sie eindeutige Namen.
- **Unstimmigkeit des räumlichen Referenzsystems** – Stimmen Sie das räumliche Referenzsystem (z. B. WGS84) immer mit den Daten ab, die Sie speichern möchten.

## Fazit
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie man mit Aspose.GIS für .NET **ein Punkt-Feature hinzufügt**, **Feldnamen festlegt** und **die Objekt‑ID liest**. Dieses Fundament befähigt Sie, robuste GIS-Anwendungen zu erstellen und räumliche Daten mit Zuversicht zu verwalten.

## Häufig gestellte Fragen
### Q: Kann ich Aspose.GIS für .NET in meinen Webanwendungen verwenden?
A: Ja, Aspose.GIS für .NET ist sowohl für Desktop‑ als auch für Webanwendungen geeignet und bietet vielseitige geospatiale Fähigkeiten.

### Q: Gibt es eine Testversion vor dem Kauf?
A: Ja, Sie können die Funktionen von Aspose.GIS für .NET mit einer kostenlosen Testversion [hier](https://releases.aspose.com/) erkunden.

### Q: Wie kann ich eine temporäre Lizenz für Aspose.GIS für .NET erhalten?
A: Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) für Evaluierungszwecke erhalten.

### Q: Welche räumlichen Referenzsysteme unterstützt Aspose.GIS für .NET?
A: Aspose.GIS für .NET unterstützt verschiedene räumliche Referenzsysteme und bietet Flexibilität für unterschiedliche geografische Datensätze.

### Q: Wo kann ich Hilfe erhalten oder Aspose.GIS‑bezogene Fragen diskutieren?
A: Besuchen Sie das Aspose.GIS‑Forum [hier](https://forum.aspose.com/c/gis/33) für Support und Diskussionen.

## Additional Frequently Asked Questions

**Frage: Kann ich das Objekt‑ID‑Feld ändern, nachdem der Layer erstellt wurde?**  
A: Nein. Der Feldname wird beim Erstellen des Layers definiert; Sie müssen den Layer mit einem neuen `FileGdbOptions`‑Objekt neu erstellen, um ihn zu ändern.

**Frage: Wie kann ich andere Attributwerte neben der Objekt‑ID abrufen?**  
A: Verwenden Sie `feature.GetValue<T>("FieldName")`, wobei `FieldName` der Name des Attributs ist, das Sie lesen möchten.

**Frage: Ist es möglich, mehrere Punkt-Features in einem Batch hinzuzufügen?**  
A: Ja. Durchlaufen Sie Ihre Daten, erstellen Sie für jeden Punkt ein Feature, setzen Sie dessen Geometrie und rufen Sie `layer.Add(feature)` innerhalb desselben `using`‑Blocks auf.

**Frage: Unterstützt Aspose.GIS andere Geometrietypen?**  
A: Absolut. Sie können mit `LineString`, `Polygon`, `MultiPoint` und mehr arbeiten, indem Sie die entsprechenden Geometrieobjekte erstellen.

**Frage: Was passiert, wenn ich versuche, eine nicht vorhandene Objekt‑ID zu lesen?**  
A: Der Zugriff auf einen Index außerhalb des Bereichs (z. B. `layer[10]`, wenn nur ein Feature existiert) löst eine `IndexOutOfRangeException` aus. Prüfen Sie stets zuerst `layer.Count`.

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}