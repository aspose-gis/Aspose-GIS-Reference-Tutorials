---
date: 2026-01-15
description: Scopri come etichettare le caratteristiche della mappa usando Aspose.GIS
  per .NET, con opzioni di stile di etichetta personalizzate per l'etichettatura di
  grandi dataset.
linktitle: Label Features on Map
second_title: Aspose.GIS .NET API
title: Etichetta le funzionalità della mappa con Aspose.GIS per .NET
url: /it/net/map-rendering/label-features-on-map/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Etichettare le funzionalità della mappa con Aspose.GIS per .NET

## Introduzione
Etichettare le funzionalità della mappa è essenziale per trasformare i dati geospaziali grezzi in visualizzazioni chiare e facili da usare. In questo tutorial scoprirai **how to label map features** (la parola chiave principale) utilizzando Aspose.GIS per .NET, esplorerai stili di etichetta personalizzati e vedrai tecniche che funzionano anche con grandi dataset. Alla fine sarai in grado di aggiungere testo informativo direttamente sulle tue mappe, rendendole più utili per analisti e utenti finali.

## Risposte rapide
- **Qual è la classe principale per il rendering?** `Map` (Aspose.Gis.Rendering)
- **Quale classe di etichettatura aggiunge testo semplice?** `SimpleLabeling`
- **Posso stilizzare le etichette (alone, font, rotazione)?** Sì – tramite proprietà come `HaloSize`, `FontStyle` e `Placement`
- **Come gestire grandi dataset?** Usa `FeatureBasedConfiguration` per dare priorità alle etichette in base ai valori degli attributi
- **È necessaria una licenza?** Una versione di prova funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione

## Che cosa sono le etichette delle funzionalità della mappa?
`label map features` indica l'attaccamento di testo leggibile (come nomi di città, dati di popolazione o identificatori personalizzati) a oggetti geometrici—punti, linee o poligoni—così che la mappa trasmetta sia informazioni spaziali sia attributi a colpo d'occhio.

## Perché utilizzare Aspose.GIS per le etichette delle funzionalità della mappa?
- **Zero dipendenze esterne** – libreria .NET pura, non richiede binari GIS nativi.  
- **Opzioni di styling ricche** – alone, font personalizzati, rotazione e punti di ancoraggio ti consentono di perfezionare l'aspetto.  
- **Ottimizzata per le prestazioni** – l'etichettatura basata su feature integrata ti permette di dare priorità alle etichette più importanti durante il rendering di grandi dataset.  
- **Molteplici formati di output** – SVG, PNG, PDF, ecc., con risultati di etichettatura coerenti.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Una buona conoscenza di C# e del framework .NET.  
- Aspose.GIS per .NET installato. Puoi scaricarlo **[qui](https://releases.aspose.com/gis/net/)**.  
- Un file GeoJSON contenente dati puntuali (o qualsiasi formato vettoriale supportato).  

## Importare gli spazi dei nomi
Nel tuo codice C#, importa gli spazi dei nomi richiesti:

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

Ora vedremo diversi scenari di etichettatura, ognuno basato sul precedente.

## Etichettatura dei punti – Come etichettare i punti
### Passo 1: Imposta il percorso della tua directory dei documenti
```csharp
string dataDir = "Your Document Directory";
```

### Passo 2: Crea una mappa con un simbolo marker semplice
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Add a vector layer and apply labeling
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Render the map to an SVG file
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```

In questo esempio base utilizziamo **how to label points** usando l'attributo `name` del file GeoJSON.

## Etichettatura dei punti con stile – Stile di etichetta personalizzato
Segui i passi 1 e 2 dell'esempio precedente, poi personalizza lo stile di etichettatura:

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Rest of the steps remain the same
```

L'alone aggiunto e il font in corsivo conferiscono alle etichette uno **custom label style** che risalta su sfondi affollati.

## Etichettatura dei punti posizionata – Opzioni avanzate di posizionamento
Ancora una volta inizia con i passi 1 e 2 del primo esempio, poi regola il posizionamento:

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
// Rest of the steps remain the same
```

Qui controlliamo i punti di ancoraggio, gli offset e la rotazione, offrendoti un controllo dettagliato su **how to label points** nelle aree di mappa affollate.

## Etichettatura dei punti basata su feature – Etichettatura di grandi dataset
Quando si gestiscono molti punti, potresti voler dare priorità alle etichette in base a un attributo come la popolazione. Segui i passi 1 e 2 del primo esempio, poi implementa l'etichettatura basata su feature:

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
        // Retrieve population from the feature.
        var population = feature.GetValue<int>("population");
        // Font size is computed and is based on the population.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Priority of the label is also based on the population.
        // The greater the priority is, the more likely label will appear on the output image.
        labeling.Priority = population;
    }
};
// Rest of the steps remain the same
```

Questa strategia di **large dataset labeling** garantisce che le città più importanti (per popolazione) vengano mostrate per prime, mentre i punti meno critici possono essere omessi quando lo spazio è limitato.

## Conclusione
Congratulazioni! Ora conosci diversi modi per **label map features** con Aspose.GIS per .NET—dall'etichettatura semplice dei punti a uno styling sofisticato, basato su feature, per grandi dataset. Sperimenta con alone, rotazioni e regole di priorità per creare mappe che comunicano esattamente ciò che il tuo pubblico deve vedere.

## Domande frequenti

**Q: Posso etichettare le feature usando font personalizzati?**  
A: Sì. Imposta `FontFamily` e `FontStyle` nella configurazione `SimpleLabeling` per utilizzare qualsiasi font installato.

**Q: Aspose.GIS è compatibile con altri formati di dati GIS?**  
A: Assolutamente. Supporta GeoJSON, Shapefile, KML, GML e molti altri formati.

**Q: Come posso gestire grandi dataset per l'etichettatura?**  
A: Usa `FeatureBasedConfiguration` per assegnare priorità e regolare dinamicamente le dimensioni del font in base ai valori degli attributi, come mostrato nell'esempio basato su feature.

**Q: Sono disponibili opzioni avanzate di posizionamento delle etichette?**  
A: Sì. Puoi perfezionare il posizionamento con `PointLabelPlacement`, regolando punti di ancoraggio, offset e rotazione.

**Q: Posso automatizzare la generazione delle etichette in un processo batch?**  
A: Certamente. Avvolgi il codice di rendering della mappa in un ciclo o in un servizio in background per elaborare più livelli o file automaticamente.

---

**Ultimo aggiornamento:** 2026-01-15  
**Testato con:** Aspose.GIS 24.11 for .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}