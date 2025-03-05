---
title: Padroneggiare l'etichettatura delle funzionalità con Aspose.GIS per .NET
linktitle: Etichetta caratteristiche sulla mappa
second_title: API Aspose.GIS .NET
description: Esplora Aspose.GIS per .NET e padroneggia l'arte dell'etichettatura delle caratteristiche sulle mappe. Migliora le tue visualizzazioni geospaziali senza sforzo. #Aspose #GIS
type: docs
weight: 11
url: /it/net/map-rendering/label-features-on-map/
---
## introduzione
Nel mondo della visualizzazione dei dati geospaziali, l'etichettatura delle caratteristiche su una mappa gioca un ruolo cruciale nel trasmettere le informazioni in modo efficace. Aspose.GIS per .NET fornisce un potente toolkit per raggiungere questo obiettivo senza problemi. In questo tutorial esploreremo vari metodi per etichettare i punti su una mappa utilizzando Aspose.GIS, migliorando le visualizzazioni della mappa con etichette informative.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Una conoscenza pratica di C# e del framework .NET.
-  Aspose.GIS per .NET installato. Puoi scaricarlo[Qui](https://releases.aspose.com/gis/net/).
- Un file GeoJSON contenente dati di punti. Se non ne hai uno, puoi utilizzare un file di esempio per testare.
## Importa spazi dei nomi
Nel tuo codice C#, assicurati di importare gli spazi dei nomi necessari per lavorare con Aspose.GIS:
```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```
Ora suddividiamo ciascun esempio in più passaggi in un formato di guida passo passo.
##  Etichettatura dei punti

### Passaggio 1: imposta il percorso della directory dei documenti:
```csharp
string dataDir = "Your Document Directory";
```
### Passaggio 2: crea una mappa con un semplice simbolo indicatore:
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Aggiungi un livello vettoriale e applica l'etichettatura
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Renderizza la mappa in un file SVG
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Etichettatura dei punti con stile

Seguire i passaggi 1 e 2 dell'esempio precedente.

### Passaggio 1: personalizza lo stile di etichettatura:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Il resto dei passaggi rimane lo stesso
```
## Etichettatura dei punti posizionata

Seguire i passaggi 1 e 2 del primo esempio.
### Passaggio 2: personalizza il posizionamento dell'etichetta:
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// Il resto dei passaggi rimane lo stesso
```
## Etichettatura dei punti basata su funzionalità

Seguire i passaggi 1 e 2 del primo esempio.

### Passaggio 1: implementare l'etichettatura basata sulle funzionalità:
```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // Recupera la popolazione dalla funzionalità.
        var population = feature.GetValue<int>("population");
        // La dimensione del carattere viene calcolata e si basa sulla popolazione.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // La priorità dell'etichetta si basa anche sulla popolazione.
        // Maggiore è la priorità, maggiore è la probabilità che l'etichetta venga visualizzata sull'immagine di output.
        labeling.Priority = population;
    }
};
// Il resto dei passaggi rimane lo stesso
```
## Conclusione
Congratulazioni! Hai imparato come migliorare le visualizzazioni della mappa etichettando le funzionalità utilizzando Aspose.GIS per .NET. Sperimenta stili e posizionamenti diversi per creare mappe accattivanti su misura per i tuoi dati.
## Domande frequenti
### Posso etichettare gli elementi utilizzando caratteri personalizzati?
Sì, puoi personalizzare lo stile e la dimensione del carattere nella configurazione dell'etichettatura.
### Aspose.GIS è compatibile con altri formati di dati GIS?
Aspose.GIS supporta vari formati geospaziali, tra cui GeoJSON, Shapefile e altri.
### Come posso gestire set di dati di grandi dimensioni per l'etichettatura?
Aspose.GIS è ottimizzato per le prestazioni, ma considera l'utilizzo di configurazioni basate su funzionalità per dare priorità alle etichette in base agli attributi dei dati.
### Sono disponibili opzioni avanzate di posizionamento delle etichette?
Sì, puoi ottimizzare il posizionamento delle etichette utilizzando opzioni come rotazione, punti di ancoraggio e offset.
### Posso automatizzare la generazione di etichette in un processo batch?
Assolutamente, puoi integrare Aspose.GIS nei tuoi flussi di lavoro automatizzati per la generazione di etichette batch.