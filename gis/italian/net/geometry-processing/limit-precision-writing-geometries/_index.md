---
date: 2026-05-31
description: Scopri come limitare la precisione durante la scrittura di geometrie
  con Aspose.GIS per .NET, riducendo le dimensioni del GeoJSON e mantenendo il controllo
  delle coordinate.
keywords:
- how to limit precision
- reduce geojson size
- Aspose.GIS precision control
linktitle: Limita la precisione nella scrittura di geometrie
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  headline: How to Limit Precision Writing Geometries with Aspose.GIS
  type: TechArticle
- description: Learn how to limit precision when writing geometries with Aspose.GIS
    for .NET, reducing GeoJSON size and keeping coordinate control.
  name: How to Limit Precision Writing Geometries with Aspose.GIS
  steps:
  - name: Define Precision Options
    text: The `GeoJsonOptions` class lets you specify how many fractional digits to
      keep for X/Y and Z coordinates. `PrecisionModel` defines how coordinate values
      are rounded or kept exact during writing.
  - name: Set Output Path
    text: Specify where the resulting GeoJSON file will be saved. `VectorLayer` is
      Aspose.GIS's container for a collection of features that share the same schema;
      it writes to the path you provide using the options set earlier.
  - name: Create and Populate Geometry
    text: Open a new `VectorLayer` with the options defined above, construct a `Point`
      geometry, and add it to the layer. `Point` represents a single coordinate (X,
      Y, optional Z) in a spatial reference system. It is the simplest geometry type
      and is used here to demonstrate precision rounding.
  - name: Read and Verify Precision
    text: Open the file you just created and print the coordinates. You should see
      the X/Y values rounded to three decimal places while the Z value remains exact.
      When you read the file back, Aspose.GIS parses the rounded values directly,
      so the in‑memory `Point` reflects the precision you defined during writ
  type: HowTo
- questions:
  - answer: Yes, it supports **50+** formats—including Shapefile, GeoJSON, KML, GML,
      and CSV—allowing seamless conversion between them.
    question: Is Aspose.GIS for .NET compatible with other GIS formats?
  - answer: Absolutely. A free trial is available from the download page, giving you
      full access to all features for evaluation.
    question: Can I try Aspose.GIS for .NET before purchasing?
  - answer: Temporary evaluation licenses can be generated via the Aspose license
      portal; they are valid for 30 days.
    question: How do I obtain a temporary license for testing?
  - answer: The Aspose.GIS forum and Stack Overflow tag `aspose-gis` are great places
      to ask questions and find community solutions.
    question: Where can I get help if I run into issues?
  - answer: Yes, Aspose.GIS is designed to handle everything from quick prototypes
      to high‑throughput server workloads, processing multi‑gigabyte datasets with
      low memory overhead.
    question: Does the library work for both small scripts and enterprise‑scale applications?
  type: FAQPage
second_title: Aspise.GIS .NET API
title: Come limitare la precisione nella scrittura di geometrie con Aspose.GIS
url: /it/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come limitare la precisione nella scrittura di geometrie con Aspose.GIS

Se ti chiedi **come limitare la precisione** quando scrivi geometrie in un'applicazione GIS .NET, Aspose.GIS per .NET offre un modo semplice e ad alte prestazioni per controllare l'arrotondamento delle coordinate. In questo tutorial percorreremo l'intero processo—dalla configurazione dell'ambiente alla verifica che l'output rispetti le regole di precisione che hai definito.

## Risposte rapide
- **Cosa significa “limit precision”?** Arrotonda i valori delle coordinate a un numero definito di cifre frazionarie durante la scrittura di un file spaziale.  
- **Quale formato è usato nell'esempio?** GeoJSON, ma le stesse opzioni si applicano ad altri formati supportati.  
- **Ho bisogno di una licenza per provare questo?** Una versione di prova gratuita funziona per sviluppo e test; è necessaria una licenza commerciale per la produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso controllare la precisione della coordinata Z separatamente?** Sì—usa `ZPrecisionModel` per impostare valori esatti o arrotondati.

## Come limitare la precisione nella scrittura di geometrie

Carica il tuo writer GeoJSON con un oggetto `GeoJsonOptions` che specifica la precisione desiderata per le coordinate X/Y e Z, quindi scrivi la geometria e leggila nuovamente—questo intero flusso di lavoro si completa in meno di dieci righe di codice e garantisce che tutte le coordinate siano arrotondate esattamente come hai definito.

Limitare la precisione è essenziale quando hai bisogno di una rappresentazione coerente delle coordinate tra diversi strumenti GIS, ridurre le dimensioni del file o rispettare gli standard di scambio dati. Di seguito definiremo le opzioni di precisione, scriveremo una geometria e poi la leggeremo nuovamente per confermare l'arrotondamento.

## Cos'è il limitare la precisione?

Il limitare la precisione è il processo di arrotondare la parte frazionaria dei valori delle coordinate a un numero fisso di cifre prima di persistere la geometria in un formato di file. Questo garantisce che ogni consumatore del file veda gli stessi valori numerici, il che aiuta a evitare piccole discrepanze che possono causare errori di topologia.

## Perché usare Aspose.GIS per il controllo della precisione?

Aspose.GIS supporta **50+** formati di input e output—including GeoJSON, Shapefile, KML e GML—e può elaborare file con **centinaia di migliaia di feature** senza caricare l'intero set di dati in memoria. I suoi modelli di precisione integrati ti consentono di arrotondare le coordinate in una singola chiamata, eliminando la necessità di script di post‑processing manuali.

## Prerequisiti

### 1. Download e installazione
Scarica l'ultimo pacchetto Aspose.GIS per .NET dal sito ufficiale: [download link](https://releases.aspose.com/gis/net/). Segui la guida di installazione per aggiungere il pacchetto NuGet al tuo progetto.

### 2. Importazione dei namespace
Aggiungi i namespace richiesti così potrai accedere alle classi GIS e alle utility di supporto.

## Guida passo‑passo

### Passo 1: Definire le opzioni di precisione
La classe `GeoJsonOptions` ti consente di specificare quante cifre frazionarie mantenere per le coordinate X/Y e Z.  
`PrecisionModel` definisce come i valori delle coordinate vengono arrotondati o mantenuti esatti durante la scrittura.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Passo 2: Impostare il percorso di output
Specifica dove verrà salvato il file GeoJSON risultante.  
`VectorLayer` è il contenitore di Aspose.GIS per una collezione di feature che condividono lo stesso schema; scrive nel percorso che fornisci utilizzando le opzioni impostate in precedenza.  

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Passo 3: Creare e popolare la geometria
Apri un nuovo `VectorLayer` con le opzioni definite sopra, costruisci una geometria `Point` e aggiungila al layer.  
`Point` rappresenta una singola coordinata (X, Y, opzionale Z) in un sistema di riferimento spaziale. È il tipo di geometria più semplice ed è usato qui per dimostrare l'arrotondamento della precisione.  

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Passo 4: Leggere e verificare la precisione
Apri il file appena creato e stampa le coordinate. Dovresti vedere i valori X/Y arrotondati a tre cifre decimali mentre il valore Z rimane esatto.  
Quando leggi nuovamente il file, Aspose.GIS analizza direttamente i valori arrotondati, quindi il `Point` in memoria riflette la precisione che hai definito durante la scrittura.  

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    var point = new Point();
    point.X = 1.8888888;
    point.Y = 1.00123;
    point.Z = 1.123456789;

    Feature feature = layer.ConstructFeature();
    feature.Geometry = point;
    layer.Add(feature);
}
```

## Problemi comuni e suggerimenti

- **Errori di percorso:** Assicurati che la directory in `path` esista o usa `Path.Combine` con `Environment.CurrentDirectory` per costruire un percorso file sicuro.  
- **Precisione non applicata:** Verifica di passare l'oggetto `GeoJsonOptions` quando crei il layer; altrimenti viene usata la precisione predefinita (double completo).  
- **Set di dati di grandi dimensioni:** Per operazioni in batch, considera di riutilizzare una singola istanza di `VectorLayer` e aggiungere le feature in blocco per migliorare le prestazioni.

## Domande frequenti

**Q: Aspose.GIS per .NET è compatibile con altri formati GIS?**  
A: Sì, supporta **50+** formati—including Shapefile, GeoJSON, KML, GML e CSV—consentendo conversioni fluide tra di essi.

**Q: Posso provare Aspose.GIS per .NET prima di acquistarlo?**  
A: Assolutamente. Una versione di prova gratuita è disponibile dalla pagina di download, offrendoti pieno accesso a tutte le funzionalità per la valutazione.

**Q: Come posso ottenere una licenza temporanea per i test?**  
A: Le licenze di valutazione temporanee possono essere generate tramite il portale licenze Aspose; sono valide per 30 giorni.

**Q: Dove posso trovare aiuto se incontro problemi?**  
A: Il forum Aspose.GIS e il tag Stack Overflow `aspose-gis` sono ottimi posti per porre domande e trovare soluzioni della community.

**Q: La libreria funziona sia per piccoli script che per applicazioni su scala enterprise?**  
A: Sì, Aspose.GIS è progettato per gestire tutto, dai prototipi rapidi a carichi di lavoro server ad alta velocità, elaborando set di dati multi‑gigabyte con un basso consumo di memoria.

---

**Ultimo aggiornamento:** 2026-05-31  
**Testato con:** Aspose.GIS 24.11 for .NET  
**Autore:** Aspose

## Tutorial correlati

- [Creare un Vector Layer, limitare la precisione con Aspose.GIS per .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Come convertire GeoJSON – Aspose.GIS per .NET](/gis/net/geo-data-conversion/)
- [Come verificare la geometria con Aspose.GIS per .NET](/gis/net/geometry-analysis/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

{{< /blocks/products/pf/main-wrap-class >}}