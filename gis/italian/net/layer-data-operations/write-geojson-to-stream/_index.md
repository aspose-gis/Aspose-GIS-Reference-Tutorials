---
date: 2026-10-15
description: Scopri come creare GeoJSON da coordinate e scriverlo in uno stream usando
  Aspose.GIS per .NET. Questo tutorial mostra la conversione passo‑passo dei punti
  e la generazione di codice C# GeoJSON.
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: Scrivi GeoJSON in uno stream
og_description: Scopri come creare GeoJSON da coordinate e scriverlo in uno stream
  usando Aspose.GIS per .NET – guida passo‑passo per grandi dataset.
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: Crea GeoJSON da coordinate, scrivilo in uno stream in .NET
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: Crea GeoJSON da coordinate, scrivilo in uno stream in .NET
url: /it/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea geojson da coordinate e scrivilo su uno stream

## Introduzione
In questo tutorial imparerai **come creare geojson da coordinate** e scriverlo direttamente su uno stream usando Aspose.GIS per .NET. Passeremo in rassegna la configurazione dell'ambiente, la creazione del layer, il popolamento delle feature e lo streaming del risultato, così potrai incorporare payload geospaziali in API, funzioni cloud o servizi senza file, senza file temporanei.

## Risposte rapide
- **Quale classe scrive GeoJSON su uno stream?** `VectorLayer` together with the `GeoJsonDriver`.
- **Ho bisogno di una licenza per lo sviluppo?** A free trial works for development; a commercial license is required for production.
- **Quali versioni .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Posso convertire collezioni di punti in GeoJSON?** Yes – create a `Feature` for each point and assign a `Point` geometry.
- **Lo streaming è adatto a grandi dataset?** Absolutely – `MemoryStream` lets you write gigabyte‑scale GeoJSON without loading the whole file into memory.

## Cos'è GeoJSON?
GeoJSON è un formato aperto basato su JSON per codificare caratteristiche geografiche come punti, linee e poligoni. Consiste in una `FeatureCollection` che raggruppa oggetti `Feature` individuali, ciascuno con geometria e dati attributo. Poiché è leggero e adatto al web, GeoJSON è lo standard de‑facto per lo scambio di dati spaziali tra browser, server GIS e app mobili.

## Perché usare Aspose.GIS per la generazione di geojson?
Aspose.GIS supporta **35+ formati di file spaziali** e può streamare file più grandi di **2 GB** mantenendo l'uso di memoria sotto **50 MB**. Il suo motore di streaming ad alte prestazioni scrive GeoJSON direttamente su qualsiasi `Stream` .NET, eliminando la necessità di file temporanei intermedi e riducendo la latenza I/O fino al **70 %** negli scenari cloud tipici.

## Prerequisiti
Before you start, make sure you have:

1. **Aspose.GIS for .NET** installato. Download the **Aspose.GIS for .NET** package [here](https://releases.aspose.com/gis/net/).
2. Una cartella scrivibile nel tuo progetto dove puoi posizionare file temporanei se necessario.
3. Runtime .NET 5+ o .NET Core 3.1+ installato.

Ora, immergiamoci nell'implementazione.

## Come creare geojson da coordinate e scriverlo su uno stream?
`VectorLayer` rappresenta un dataset vettoriale in‑memoria che può essere salvato in vari formati.  
`GeoJsonDriver` è il driver che consente la lettura e scrittura di file GeoJSON.

Carica un `VectorLayer` con il `GeoJsonDriver`, aggiungi oggetti `Feature` che contengono geometria `Point` e chiama `layer.Save(stream, new GeoJsonSaveOptions())`. Questa singola chiamata serializza l'intera collezione di feature in un documento GeoJSON conforme agli standard che risiede nel `MemoryStream` fornito. Il processo gestisce automaticamente la mappatura degli attributi e la conversione delle coordinate, così ricevi un payload JSON pronto all'uso senza costruire manualmente le stringhe.

### Ancore di definizione
**VectorLayer** è l'oggetto principale di Aspose.GIS che rappresenta un dataset vettoriale modificabile in memoria.  
**GeoJsonDriver** è il driver responsabile della lettura e scrittura di file GeoJSON.

## Importa namespace
Prima di tutto, assicurati di includere i namespace necessari per accedere alle funzionalità di Aspose.GIS nel tuo codice:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Passo 1: configura la directory dei documenti
Crea un percorso di cartella dove Aspose.GIS può memorizzare file ausiliari se necessario.  
```csharp
string dataDir = "Your Document Directory";
```
Sostituisci "Your Document Directory" con il percorso reale della tua directory dei documenti.

## Passo 2: crea uno stream di memoria
Un `MemoryStream` fornisce un buffer in memoria che può essere inviato direttamente via HTTP o salvato su storage cloud.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Passo 3: crea un vector layer con driver GeoJSON
La classe `VectorLayer` rappresenta un dataset vettoriale che può essere salvato in vari formati, incluso GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Passo 4: definisci gli attributi delle feature
Definisci lo schema degli attributi per le tue feature (es., ID, Nome).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Passo 5: costruisci e aggiungi le feature
Crea oggetti `Feature`, assegna la geometria punto, imposta i valori degli attributi e aggiungili al layer.  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Passo 6: visualizza l'output GeoJSON
Dopo il salvataggio, reimposta la posizione dello stream e leggi la stringa JSON per verifica o trasmissione.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Congratulazioni! Hai creato con successo geojson da coordinate e lo hai scritto su uno stream usando Aspose.GIS per .NET.

## Problemi comuni e soluzioni
- **Stream di output vuoto:** Ensure you reset the stream position (`stream.Position = 0`) before reading.
- **Ordine delle coordinate errato:** GeoJSON expects longitude‑latitude order; verify your point values.
- **Dataset di grandi dimensioni:** Use `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` to stream features incrementally and keep memory usage low.

## Domande frequenti

**Q: Posso usare Aspose.GIS per .NET sia in ambienti Windows che Linux?**  
A: Sì, Aspose.GIS per .NET funziona su Windows, Linux e macOS con pieno supporto .NET Core.

**Q: È disponibile una versione di prova gratuita?**  
A: Assolutamente! Puoi esplorare la **free trial download page** [here](https://releases.aspose.com/).

**Q: Dove posso trovare la documentazione dettagliata?**  
A: Consulta la **Aspose.GIS .NET documentation** [here](https://reference.aspose.com/gis/net/).

**Q: Come posso ottenere una licenza temporanea?**  
A: Le licenze temporanee sono disponibili sulla **temporary license page** [here](https://purchase.aspose.com/temporary-license/).

**Q: Hai bisogno di assistenza o hai altre domande?**  
A: Visita il nostro **GIS support forum** [here](https://forum.aspose.com/c/gis/33).

**Q: Posso generare GeoJSON da una collezione di punti latitudine/longitudine?**  
A: Sì – crea una `Feature` per ogni punto, assegna una geometria `Point` e aggiungila al `VectorLayer`.

**Q: Aspose.GIS supporta la scrittura di GeoJSON compresso (gzip)?**  
A: Puoi avvolgere il `MemoryStream` in un `GZipStream` prima di salvare per produrre un payload compresso.

**Q: Qual è la dimensione massima di un file GeoJSON che Aspose.GIS può gestire?**  
A: La libreria può streamare file superiori a 2 GB; l'uso di memoria rimane basso perché i dati vengono scritti in modo incrementale.

---

**Ultimo aggiornamento:** 2026-10-15  
**Testato con:** Aspose.GIS 24.11 for .NET  
**Autore:** Aspose  

## Tutorial correlati

- [How to Read GeoJSON from Stream with Aspose.GIS for .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [How to Convert GeoJSON to TopoJSON with Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [How to Convert Shapefile to GeoJSON using Aspose.GIS for .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}