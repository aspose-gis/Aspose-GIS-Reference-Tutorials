---
date: 2026-10-05
description: Scopri come leggere geojson da uno stream utilizzando Aspose.GIS per
  .NET. Questa guida passo‑passo ti mostra come caricare lo stream geojson, analizzarlo
  e estrarre le proprietà in C#.
keywords:
- how to read geojson
- load geojson stream
- parse geojson c#
- open geojson layer
- extract geojson properties
lastmod: 2026-10-05
linktitle: Leggi GeoJSON da Stream
og_description: Scopri come leggere geojson da uno stream utilizzando Aspose.GIS per
  .NET, inclusa l'analisi, l'apertura di un layer geojson e l'estrazione delle proprietà
  in C#.
og_image_alt: Tutorial guide showing how to read geojson from a stream with Aspose.GIS
  in C#
og_title: Come leggere geojson da uno stream con Aspose.GIS per .NET
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  headline: How to read geojson from a stream with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  name: How to read geojson from a stream with Aspose.GIS for .NET
  steps:
  - name: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
    text: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
  - name: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
    text: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET – it handles 30+ GIS formats out of the box.
    question: What library should I use?
  - answer: Yes – call `VectorLayer.Open` with `AbstractPath.FromStream`.
    question: Can I read GeoJSON directly from a stream?
  - answer: A free trial works for testing; a full license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Which .NET versions are supported?
  - answer: Absolutely – use `GetValue<T>(columnName)` on a feature.
    question: Is extracting properties simple?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET GIS
- C# geospatial
title: Come leggere geojson da uno stream con Aspose.GIS per .NET
url: /it/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere geojson da uno stream con Aspose.GIS per .NET

## Introduzione
Se ti chiedi **come leggere geojson** in un'applicazione .NET, sei nel posto giusto. In questo tutorial percorreremo un **esempio C# GeoJSON** completo che mostra come convertire una stringa GeoJSON, **caricare lo stream geojson** in un memory stream, aprire un layer GeoJSON ed estrarre le proprietà GeoJSON usando Aspose.GIS. Alla fine avrai un modello riutilizzabile da inserire in qualsiasi progetto che necessita di lavorare con dati geospaziali.

## Risposte rapide
- **Quale libreria dovrei usare?** Aspose.GIS per .NET – gestisce oltre 30 formati GIS subito pronto all'uso.  
- **Posso leggere GeoJSON direttamente da uno stream?** Sì – chiama `VectorLayer.Open` con `AbstractPath.FromStream`.  
- **Ho bisogno di una licenza per lo sviluppo?** Una prova gratuita funziona per i test; è necessaria una licenza completa per la produzione.  
- **Quali versioni .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **L'estrazione delle proprietà è semplice?** Assolutamente – usa `GetValue<T>(columnName)` su una feature.

**VectorLayer.Open** apre un layer GIS da una sorgente dati come un file o uno stream. **AbstractPath.FromStream** crea un oggetto percorso astratto che rappresenta lo stream fornito per il driver GIS. **GetValue<T>(columnName)** legge il valore dell'attributo specificato da una feature e lo restituisce come tipo T.

## Che cos'è leggere geojson?
Leggere geojson è il processo di conversione di una stringa o stream formattato GeoJSON in oggetti geografici in memoria. Questo formato codifica punti, linee e poligoni usando JSON, facilitando lo scambio di dati spaziali tra servizi web, database e applicazioni client. Una volta analizzato, puoi interrogare, modificare o visualizzare le feature con qualsiasi libreria .NET consapevole di GIS, come Aspose.GIS.

## Perché usare Aspose.GIS per aprire un layer geojson?
Aspose.GIS ti consente di aprire un layer GeoJSON direttamente da uno stream, eliminando la necessità di file temporanei e riducendo l'overhead I/O. La libreria supporta oltre 30 formati GIS e può elaborare file fino a 2 GB senza caricare l'intero documento in memoria, ideale per dataset di grandi dimensioni. Normalizza inoltre i sistemi di riferimento delle coordinate automaticamente, così puoi concentrarti sulla logica di business invece che sul parsing a basso livello.

## Quando caricheresti uno stream geojson?
Caricheresti uno stream GeoJSON quando ricevi dati spaziali da un'API, devi gestire file caricati dagli utenti senza salvarli su disco, o generi GeoJSON al volo da una query di database. Lo streaming evita scritture su disco non necessarie, migliora le prestazioni in scenari ad alto throughput e mantiene la tua applicazione senza stato, particolarmente utile nei microservizi cloud‑native.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Conoscenza di base di C#** – dovresti sentirti a tuo agio con la sintassi .NET e l'IDE Visual Studio.  
2. **Aspose.GIS installato** – scarica la libreria dalla [pagina di download Aspose.GIS .NET](https://releases.aspose.com/gis/net/).  
3. **Un ambiente di sviluppo** – Visual Studio, Visual Studio Code o JetBrains Rider andranno benissimo.  

## Importare i namespace
Il namespace `Aspose.GIS` fornisce le classi GIS core. `System.IO` ti dà `MemoryStream`, e `System.Text` fornisce le utility di codifica UTF‑8. Importare questi namespace rende il codice successivo conciso e leggibile.

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Passo 1: convertire la stringa geojson – un esempio GeoJSON in C#
Per prima cosa creiamo una stringa JSON che rappresenta una semplice `FeatureCollection`. Questa è la parte **convertire la stringa geojson** del flusso di lavoro.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Passo 2: caricare lo stream geojson ed estrarre le proprietà geojson
Ora inseriamo la stringa in un `MemoryStream`, la apriamo come layer GIS e dimostriamo come leggere i valori degli attributi (la fase **estrarre le proprietà geojson**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Suggerimento:** `VectorLayer.Open` rileva automaticamente il formato GeoJSON quando passi `Drivers.GeoJson`. Puoi anche aprire file direttamente fornendo un percorso file invece di uno stream.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Formato JSON non valido** | Verifica che la stringa GeoJSON sia ben formata; usa un validatore JSON. |
| **Problemi di codifica** | Assicurati che lo stream utilizzi UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Proprietà mancanti** | Verifica che il nome della proprietà sia scritto correttamente (`"name"` nell'esempio). |
| **Eccezione di licenza** | Usa una licenza di prova per i test; applica una licenza permanente per la produzione. |

## Domande frequenti
### Aspose.GIS è compatibile con altri formati GIS?
Sì, Aspose.GIS supporta GeoJSON, Shapefile, KML, GML e oltre 20 formati aggiuntivi, consentendoti di passare da una sorgente dati all'altra senza modificare il codice.

### Posso provare Aspose.GIS prima di acquistarlo?
Puoi scaricare una versione di prova gratuita di Aspose.GIS dalla [pagina di download della prova gratuita Aspose.GIS](https://releases.aspose.com/).

### Dove posso trovare la documentazione per Aspose.GIS?
Puoi trovare la documentazione per Aspose.GIS nella [riferimento API .NET Aspose.GIS](https://reference.aspose.com/gis/net/).

### Come posso ottenere supporto per Aspose.GIS?
Puoi ottenere supporto per Aspose.GIS sul forum Aspose GIS [Aspose GIS forum](https://forum.aspose.com/c/gis/33).

### Ho bisogno di una licenza temporanea per usare Aspose.GIS?
Puoi ottenere una licenza temporanea per Aspose.GIS dalla [pagina di richiesta licenza temporanea](https://purchase.aspose.com/temporary-license/).

## Conclusione
In questa guida abbiamo coperto **come leggere geojson** da un memory stream usando Aspose.GIS per .NET, dimostrato un flusso di lavoro **C# read geojson**, e mostrato come **estrarre le proprietà geojson** dal layer aperto. Con questi passaggi puoi integrare senza sforzo la gestione dei dati geospaziali in qualsiasi applicazione .NET.

---

**Last Updated:** 2026-10-05  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Tutorial correlati

- [Come scrivere GeoJSON su stream con Aspose.GIS per .NET](/gis/net/layer-data-operations/write-geojson-to-stream/)
- [Come convertire GeoJSON in GDB usando Aspose.GIS per .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Convertire Shapefile in GeoJSON con Aspose.GIS per .NET](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}