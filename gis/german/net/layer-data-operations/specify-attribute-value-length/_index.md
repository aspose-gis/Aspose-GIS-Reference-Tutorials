---
date: 2026-05-16
description: Vektor-Layer-Beispiel, das zeigt, wie man field width festlegt, attribute
  width definiert und attribute length in Aspose.GIS für .NET hinzufügt – ein vollständiger
  Schritt‑für‑Schritt‑Leitfaden.
keywords:
- vector layer example
- how to set width
- set field width
- define attribute width
- add attribute length
linktitle: Wie man field width festlegt
schemas:
- author: Aspose
  dateModified: '2026-05-16'
  description: Vector layer example showing how to set field width, define attribute
    width, and add attribute length in Aspose.GIS for .NET – a complete step‑by‑step
    guide.
  headline: Vector Layer Example – How to Set Field Width in Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for peer‑to‑peer
      help and official responses.
    question: Where can I find community support for Aspose.GIS for .NET?
  - answer: Yes, explore the [free trial](https://releases.aspose.com/) to experience
      the full feature set without cost.
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Purchase your license [here](https://purchase.aspose.com/buy).
    question: How do I purchase a license for Aspose.GIS for .NET?
  - answer: Refer to the [documentation](https://reference.aspose.com/gis/net/) for
      comprehensive API details.
    question: Where can I access the documentation for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Vektor-Layer-Beispiel – Wie man field width in Aspose.GIS für .NET festlegt
url: /de/net/layer-data-operations/specify-attribute-value-length/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vektor-Layer-Beispiel – Wie man die Feldbreite in Aspose.GIS für .NET festlegt

In diesem **Vektor-Layer-Beispiel** lernen Sie, wie man die Feldbreite für ein Attribut beim Erstellen einer Shapefile mit Aspose.GIS für .NET festlegt. Wir gehen jeden Schritt durch, vom Importieren von Namespaces bis zum Hinzufügen eines Features, und erklären, warum die Kontrolle der Attributlänge für Datenintegrität und Interoperabilität mit anderen GIS‑Tools wichtig ist.

## Schnelle Antworten
- **Was ist der Hauptzweck dieses Leitfadens?** Ihnen zu zeigen, wie man die Feldbreite für ein Attribut in einer Shapefile mithilfe von Aspose.GIS für .NET festlegt.  
- **Welche Klasse definiert die Feldbreite?** `FeatureAttribute.Width`.  
- **Benötige ich eine Lizenz, um den Code auszuführen?** Eine temporäre Lizenz funktioniert für die Evaluierung; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  
- **Welches Dateiformat wird im Beispiel verwendet?** ESRI Shapefile (`.shp`).  
- **Kann ich die Breite ändern, nachdem der Layer erstellt wurde?** Nein – die Breite muss definiert werden, bevor Features hinzugefügt werden.

## Was ist Feldbreite und warum ist sie wichtig?
Die Feldbreite (auch Attributlänge genannt) ist die maximale Anzahl von Zeichen, die ein Zeichenkettenfeld in der DBF‑Komponente einer Shapefile speichern kann. Das Festlegen der korrekten Breite verhindert stillschweigende Kürzungen, stellt sicher, dass andere GIS‑Anwendungen die Daten exakt so lesen, wie Sie sie eingegeben haben, und hält die Dateigröße vorhersehbar – jedes zusätzliche Zeichen fügt pro Datensatz ein Byte hinzu.

## Voraussetzungen
- **Aspose.GIS für .NET Bibliothek** – herunterladen über den [download link](https://releases.aspose.com/gis/net/).  
- **Entwicklungsumgebung** – Visual Studio 2022, Visual Studio Code oder jede IDE, die .NET 6+ unterstützt.  
- **Schreibzugriff** – ein Ordner auf dem Datenträger, in dem die erzeugte Shapefile gespeichert wird.

## Warum ein Vektor‑Layer‑Beispiel mit definierter Breite verwenden?
Aspose.GIS unterstützt **mehr als 30 GIS‑Dateiformate**, darunter Shapefile, GeoJSON, KML und GML. Wenn Sie die Feldbreite explizit festlegen, vermeiden Sie das Standard‑Limit von 255 Zeichen, das die `.dbf`‑Datei unnötig um bis zu 255 × AnzahlDerDatensätze Bytes aufblähen kann. Bei großen Datensätzen führt das zu spürbaren Speicherersparnissen.

## Wie legt man die Feldbreite für ein Attribut fest?
In diesem Abschnitt laden oder erstellen wir ein `VectorLayer`, das auf die Ziel‑`.shp`‑Datei verweist, definieren ein Zeichenketten‑Attribut mit einer genauen Breite und fügen anschließend Features hinzu – alles in wenigen prägnanten Anweisungen. `VectorLayer` repräsentiert ein Vektor‑Datenset wie eine Shapefile und bietet Zugriff auf Geometrie und Attributtabelle. Nachfolgend das direkte, umsetzbare Rezept, dem Sie Schritt für Schritt folgen können:

Laden oder erstellen Sie ein `VectorLayer`, das auf die Ziel‑`.shp`‑Datei verweist, deklarieren Sie ein Zeichenketten‑Attribut namens **wide** mit `Width = 120` und fügen dann ein Feature hinzu, dessen Wert das 120‑Zeichen‑Limit einhält. Aspose.GIS kürzt automatisch jede längere Zeichenkette auf die definierte Breite und bewahrt so die Datenkonsistenz, ohne Ausnahmen zu werfen.

### Namespaces importieren
`FeatureAttribute`, `VectorLayer` und verwandte Typen befinden sich im Namespace `Aspose.Gis`. Importieren Sie sie am Anfang Ihrer Datei:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### VectorLayer erstellen
Die Klasse `VectorLayer` repräsentiert eine Vektor‑Datenquelle (z. B. eine Shapefile). Sie ist der Container, der Features und deren Attribute enthält.

Die Klasse `VectorLayer` ist Aspose.GIS' Darstellung eines Vektor‑Datensets, das Geometrie und Attributtabellen im Speicher verwaltet. Erstellen Sie eine Instanz, die auf eine neue oder bestehende `.shp`‑Datei verweist.

```csharp
string dataDir = "Your Document Directory";
using (VectorLayer layer = VectorLayer.Create(dataDir + "SpecifyAttributeValueLength_out.shp", Drivers.Shapefile))
{
    // Your code for the next steps will go here.
}
```

### Attribut mit spezifischer Länge hinzufügen
Definieren Sie ein Zeichenketten‑Attribut namens **wide** und setzen Sie dessen `Width`‑Eigenschaft auf 120 Zeichen. Dies ist der zentrale Schritt des **Vektor‑Layer‑Beispiels**.

Das Objekt `FeatureAttribute` beschreibt eine Spalte in der Attributtabelle; das Setzen von `Width = 120` weist den Shapefile‑Writer an, genau 120 Bytes für jeden Datensatz dieses Feldes zu reservieren.

```csharp
FeatureAttribute attribute = new FeatureAttribute("wide", AttributeDataType.String);
attribute.Width = 120;
layer.Attributes.Add(attribute);
```

> **Profi‑Tipp:** Die `Width`‑Eigenschaft gilt nur für Zeichenketten‑Attribute. Numerische, Datums‑ oder Boolesche Felder ignorieren `Width`, da ihre Größe durch den Datentyp festgelegt ist.

### Feature erstellen und hinzufügen
Erstellen Sie ein `Feature`, weisen Sie ihm einen Wert zu, der innerhalb des 120‑Zeichen‑Limits liegt, und fügen Sie es dem Layer hinzu. Überschreitet die Zeichenkette das Limit, kürzt Aspose.GIS sie stillschweigend auf die definierte Breite, wodurch die Datenintegrität erhalten bleibt.

Die Klasse `Feature` kapselt Geometrie‑ und Attributwerte; nach dem Setzen des Attributs schreibt der Aufruf `layer.Add(feature)` den Datensatz in die Shapefile.

```csharp
Feature feature = layer.ConstructFeature();
feature.SetValue("wide", "this string can be up to 120 characters long now.");
layer.Add(feature);
```

Wenn Sie versuchen, eine längere Zeichenkette zuzuweisen, wird Aspose.GIS sie auf die definierte Breite kürzen und die Datenintegrität bewahren.

## Häufige Fallstricke & Fehlerbehebung
- **Haben Sie vergessen, `Width` vor dem Hinzufügen des Attributs zu setzen?** Die Standardbreite beträgt 255 Zeichen; eine spätere Änderung wirkt sich nicht auf bereits erstellte Felder aus. Definieren Sie die Breite immer zuerst.  
- **Verwenden Sie einen Nicht‑String‑Datentyp?** `Width` wird für numerische oder Datumsfelder ignoriert; stellen Sie sicher, dass der `AttributeDataType` des Attributs `String` ist.  
- **Fehler „Feld nicht gefunden“?** Attributnamen sind case‑sensitive. Vergewissern Sie sich, dass der in `SetValue` verwendete Name exakt dem im Schema definierten Namen entspricht.  
- **Unerwartete Zunahme der Dateigröße?** Größere Breiten erhöhen die `.dbf`‑Größe linear. Bei 10 000 Datensätzen fügt eine Breitensteigerung von 50 auf 120 etwa 700 KB hinzu.

## Häufig gestellte Fragen
**Q: Wie kann ich eine temporäre Lizenz für Aspose.GIS für .NET erhalten?**  
A: Sie können eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/) erwerben.

**Q: Wo finde ich Community‑Support für Aspose.GIS für .NET?**  
A: Besuchen Sie das [Aspose.GIS‑Forum](https://forum.aspose.com/c/gis/33) für Peer‑to‑Peer‑Hilfe und offizielle Antworten.

**Q: Gibt es eine kostenlose Testversion für Aspose.GIS für .NET?**  
A: Ja, testen Sie die [kostenlose Testversion](https://releases.aspose.com/), um den vollen Funktionsumfang ohne Kosten zu erleben.

**Q: Wie kaufe ich eine Lizenz für Aspose.GIS für .NET?**  
A: Kaufen Sie Ihre Lizenz [hier](https://purchase.aspose.com/buy).

**Q: Wo finde ich die Dokumentation für Aspose.GIS für .NET?**  
A: Siehe die [Dokumentation](https://reference.aspose.com/gis/net/) für umfassende API‑Details.

**Q: Kann ich die Feldbreite ändern, nachdem der Layer erstellt wurde?**  
A: Nein. Die Feldbreite muss definiert werden, bevor das Attribut hinzugefügt wird; um sie zu ändern, müssen Sie den Layer mit dem neuen Schema neu erstellen.

**Q: Wirkt sich das Setzen einer größeren Breite auf die Dateigröße aus?**  
A: Shapefiles speichern Zeichenkettenfelder mit fester Länge, sodass eine Erhöhung der Breite die `.dbf`‑Dateigröße proportional zur Anzahl der Datensätze direkt erhöht.

## Fazit
Dieses **Vektor‑Layer‑Beispiel** zeigte, wie man die Feldbreite für ein Attribut in einer Shapefile mit Aspose.GIS für .NET festlegt und wie man ein Attribut mit einer spezifischen Länge effizient hinzufügt. Durch die Kontrolle der Attributbreite vermeiden Sie Datenkürzungen, halten die Dateigrößen optimal und gewährleisten nahtlose Interoperabilität mit anderen GIS‑Plattformen. Experimentieren Sie mit unterschiedlichen Breiten, erkunden Sie die [Dokumentation](https://reference.aspose.com/gis/net/) und erschließen Sie das volle Potenzial der geospatiale Entwicklung mit Aspose.GIS.

---

**Zuletzt aktualisiert:** 2026-05-16  
**Getestet mit:** Aspose.GIS 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [Layer-Attribute abrufen – Layer-Attributinformationen mit Aspose.GIS für .NET erhalten](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Wie man Attributwert (Standard) mit Aspose.GIS für .NET erhält](/gis/net/layer-interaction-and-data-access/get-feature-attribute-value-default/)
- [Vector Layer in File GDB erstellen – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}