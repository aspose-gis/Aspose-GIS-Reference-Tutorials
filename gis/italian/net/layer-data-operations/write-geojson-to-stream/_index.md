---
date: 2026-05-21
description: Scopri come scrivere GeoJSON su stream usando Aspose.GIS per .NET. Questo
  tutorial GeoJSON .NET mostra la conversione passo‑passo dei punti e la generazione
  del codice GeoJSON C#.
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: Scrivi GeoJSON su stream
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Come scrivere GeoJSON su stream con Aspose.GIS per .NET
url: /it/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Scrivi GeoJSON su Stream

## Introduzione
In questo tutorial imparerai **come scrivere GeoJSON su uno stream** in un'applicazione .NET usando Aspose.GIS. Ti guideremo passo passo, dalla configurazione dell'ambiente alla generazione di un documento GeoJSON valido, così potrai integrare i dati geospaziali senza problemi nei tuoi servizi.

## Risposte Rapide
- **Qual è la classe principale per l'output GeoJSON?** `VectorLayer` con il `GeoJsonDriver`.
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita funziona per lo sviluppo; è richiesta una licenza commerciale per la produzione.
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Posso convertire collezioni di punti in GeoJSON?** Sì – usa la classe `Feature` e definisci la geometria del punto.
- **Lo streaming è supportato per grandi dataset?** Assolutamente; `MemoryStream` ti consente di scrivere senza file intermedi.

## Cos'è GeoJSON?
GeoJSON è un formato standard aperto per codificare una varietà di strutture di dati geografici usando JSON. Definisce oggetti come FeatureCollection, Feature e tipi di geometria (Point, LineString, Polygon). Questa rappresentazione leggera e adatta al web consente uno scambio e una visualizzazione facili dei dati spaziali su molte piattaforme e linguaggi di programmazione.

## Perché usare Aspose.GIS per la generazione di GeoJSON?
Aspose.GIS supporta più di 30 formati di file spaziali e può elaborare file più grandi di 2 GB senza caricare l'intero documento in memoria. Il suo motore di streaming ad alte prestazioni scrive GeoJSON direttamente su stream, riducendo il sovraccarico I/O. Questo lo rende ideale per carichi di lavoro geospaziali su scala aziendale, servizi cloud e applicazioni in tempo reale.

## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere i seguenti prerequisiti:
1. Libreria Aspose.GIS per .NET: Verifica di aver installato la libreria Aspose.GIS per .NET. Puoi scaricarla [qui](https://releases.aspose.com/gis/net/).
2. Directory dei Documenti: Crea una directory dei documenti nel tuo progetto e annota il suo percorso.

Ora, iniziamo il tutorial!

## Come scrivere GeoJSON su uno stream?
VectorLayer rappresenta un dataset vettoriale che può essere salvato in vari formati, incluso GeoJSON.  
GeoJsonDriver è il driver utilizzato da Aspose.GIS per leggere e scrivere file GeoJSON.  
`layer.Save` scrive il contenuto del layer nello stream fornito usando le opzioni di salvataggio specificate.  

Carica un `VectorLayer` con il `GeoJsonDriver`, aggiungi feature che contengono geometria di punto, e poi chiama `layer.Save(stream, new GeoJsonSaveOptions())`. Questo scrive un documento GeoJSON completo e conforme agli standard direttamente nello `MemoryStream` fornito in poche righe di codice. Il metodo serializza la collezione di feature, gestendo automaticamente i dati attributo e la conversione della geometria, così ottieni un payload JSON pronto all'uso senza manipolazioni manuali di stringhe.

## Importa Namespace
Prima di tutto, assicurati di includere i namespace necessari per accedere alle funzionalità di Aspose.GIS nel tuo codice:
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Passo 1: Configura la Directory dei Documenti
Sostituisci "Your Document Directory" con il percorso reale della tua directory dei documenti.
```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Crea uno Stream di Memoria
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Passo 3: Crea un Vector Layer con il Driver GeoJSON
La classe `VectorLayer` rappresenta un dataset vettoriale che può essere salvato in vari formati, incluso GeoJSON.
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Passo 4: Definisci gli Attributi delle Feature
Definisci lo schema degli attributi per le tue feature (ad es., ID, Nome).
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Passo 5: Costruisci e Aggiungi le Feature
Crea oggetti `Feature`, assegna la geometria di punto, imposta i valori degli attributi e aggiungili al layer.
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

## Passo 6: Visualizza l'Output GeoJSON
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Congratulazioni! Hai scritto con successo GeoJSON su uno stream usando Aspose.GIS per .NET.

## Problemi Comuni e Soluzioni
- **Stream di output vuoto:** Assicurati di ripristinare la posizione dello stream (`stream.Position = 0`) prima della lettura.
- **Ordine delle coordinate errato:** GeoJSON si aspetta l'ordine longitudine‑latitudine; verifica i valori dei tuoi punti.
- **Dataset di grandi dimensioni:** Usa `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` per streammare le feature in modo incrementale.

## Domande Frequenti
### Posso usare Aspose.GIS per .NET sia in ambienti Windows che Linux?
Sì, Aspose.GIS per .NET è compatibile sia con sistemi Windows che Linux.

### È disponibile una prova gratuita?
Assolutamente! Puoi provare la versione gratuita [qui](https://releases.aspose.com/).

### Dove posso trovare la documentazione dettagliata?
Consulta la documentazione [qui](https://reference.aspose.com/gis/net/).

### Come posso ottenere una licenza temporanea?
Le licenze temporanee sono disponibili [qui](https://purchase.aspose.com/temporary-license/).

### Hai bisogno di assistenza o hai altre domande?
Visita il nostro forum di supporto [qui](https://forum.aspose.com/c/gis/33).

**Q: Posso generare GeoJSON da una collezione di punti latitudine/longitudine?**  
A: Sì – crea una `Feature` per ogni punto, assegna una geometria `Point` e aggiungila al `VectorLayer`.  

**Q: Aspose.GIS supporta la scrittura di GeoJSON compresso (gzip)?**  
A: Puoi avvolgere il `MemoryStream` in un `GZipStream` prima del salvataggio per produrre un payload compresso.  

**Q: Qual è la dimensione massima di un file GeoJSON che Aspose.GIS può gestire?**  
A: La libreria può streammare file superiori a 2 GB; l'uso della memoria rimane basso perché i dati vengono scritti in modo incrementale.  

---

**Ultimo aggiornamento:** 2026-05-21  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Correlati

- [Come leggere GeoJSON da uno stream con Aspose.GIS per .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Come convertire GeoJSON in TopoJSON con Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Come convertire Shapefile in GeoJSON usando Aspose.GIS per .NET](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}