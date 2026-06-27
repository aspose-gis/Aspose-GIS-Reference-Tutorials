---
date: 2026-04-24
description: Impara **come leggere geojson** da uno stream usando Aspose.GIS per .NET.
  Questa guida passo‑passo ti mostra come **caricare lo stream geojson**, analizzarlo
  ed estrarre le proprietà in C#.
keywords:
- how to read geojson
- load geojson stream
- Aspose GIS GeoJSON
linktitle: Leggi GeoJSON dallo stream
second_title: Aspose.GIS .NET API
title: Come leggere GeoJSON dallo stream con Aspose.GIS per .NET
url: /it/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere GeoJSON dallo stream con Aspose.GIS per .NET

## Introduzione
Se ti stai chiedendo **come leggere geojson** in un'applicazione .NET, sei nel posto giusto. In questo tutorial percorreremo un **esempio C# GeoJSON** completo che mostra come convertire una stringa GeoJSON, **caricare lo stream geojson** in un memory stream, aprire un layer GeoJSON e estrarre le proprietà GeoJSON usando Aspose.GIS. Alla fine avrai un modello riutilizzabile da inserire in qualsiasi progetto che necessita di lavorare con dati geospaziali.

## Risposte rapide
- **Quale libreria dovrei usare?** Aspose.GIS per .NET – gestisce molti formati GIS subito pronto all'uso.  
- **Posso leggere GeoJSON direttamente da uno stream?** Sì – usa `VectorLayer.Open` con `AbstractPath.FromStream`.  
- **Ho bisogno di una licenza per lo sviluppo?** Una versione di prova gratuita funziona per i test; è necessaria una licenza completa per la produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **L'estrazione delle proprietà è semplice?** Assolutamente – chiama `GetValue<T>(columnName)` su una feature.

## Cos'è “come leggere geojson”?
Leggere GeoJSON significa analizzare il formato basato su JSON che descrive le caratteristiche geografiche (punti, linee, poligoni) e trasformare tali caratteristiche in oggetti che puoi interrogare, modificare o visualizzare nella tua applicazione.

## Perché usare Aspose.GIS per **aprire un layer geojson**?
Aspose.GIS astrae i dettagli di parsing a basso livello e ti fornisce un'API coerente per molti formati GIS. Ti consente di **aprire un layer geojson** direttamente da uno stream, gestire file di grandi dimensioni in modo efficiente e accedere agli attributi delle feature senza scrivere parser JSON personalizzati.

## Quando dovresti **caricare lo stream geojson**?
- Importare dati da un servizio web che restituisce GeoJSON nel corpo della risposta.  
- Elaborare file GeoJSON caricati dagli utenti senza scriverli prima su disco.  
- Lavorare con dati in memoria generati al volo (ad esempio, da un database o da un'altra API).  

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Conoscenza di base di C#** – dovresti sentirti a tuo agio con la sintassi .NET e l'IDE Visual Studio.  
2. **Aspose.GIS installato** – scarica la libreria da [qui](https://releases.aspose.com/gis/net/).  
3. **Un ambiente di sviluppo** – Visual Studio, Visual Studio Code o JetBrains Rider andranno bene.  

## Importa gli spazi dei nomi
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Passo 1: **Converti stringa GeoJSON** – un **esempio C# GeoJSON**
Per prima cosa creiamo una stringa JSON che rappresenta una semplice `FeatureCollection`. Questa è la parte **converti stringa geojson** del flusso di lavoro.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Passo 2: **Carica lo stream GeoJSON** e **estrai le proprietà geojson**
Ora inseriamo la stringa in un `MemoryStream`, la apriamo come layer GIS e dimostriamo come leggere i valori degli attributi (la fase **estrai le proprietà geojson**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Suggerimento professionale:** `VectorLayer.Open` rileva automaticamente il formato GeoJSON quando passi `Drivers.GeoJson`. Puoi anche aprire file direttamente fornendo un percorso file invece di uno stream.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Formato JSON non valido** | Verifica che la stringa GeoJSON sia ben formata; usa un validatore JSON. |
| **Problemi di codifica** | Assicurati che lo stream utilizzi UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Proprietà mancanti** | Controlla che il nome della proprietà sia scritto correttamente (`"name"` nell'esempio). |
| **Eccezione di licenza** | Usa una licenza di prova per i test; applica una licenza permanente per la produzione. |

## Domande frequenti
### Aspose.GIS è compatibile con altri formati GIS?
Sì, Aspose.GIS supporta GeoJSON, Shapefile, KML, GML e molti altri formati.

### Posso provare Aspose.GIS prima di acquistarlo?
Sì, puoi scaricare una versione di prova gratuita di Aspose.GIS da [qui](https://releases.aspose.com/).

### Dove posso trovare la documentazione per Aspose.GIS?
Puoi trovare la documentazione per Aspose.GIS [qui](https://reference.aspose.com/gis/net/).

### Come posso ottenere supporto per Aspose.GIS?
Puoi ottenere supporto per Aspose.GIS nei forum Aspose [qui](https://forum.aspose.com/c/gis/33).

### Ho bisogno di una licenza temporanea per usare Aspose.GIS?
Puoi ottenere una licenza temporanea per Aspose.GIS da [qui](https://purchase.aspose.com/temporary-license/).

## Conclusione
In questa guida abbiamo coperto **come leggere geojson** da un memory stream usando Aspose.GIS per .NET, dimostrato un flusso di lavoro **C# per leggere geojson** e mostrato come **estrarre le proprietà geojson** dal layer aperto. Con questi passaggi puoi integrare senza problemi la gestione dei dati geospaziali in qualsiasi applicazione .NET.

---

**Ultimo aggiornamento:** 2026-04-24  
**Testato con:** Aspose.GIS 24.11 for .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}