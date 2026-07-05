---
date: 2026-07-05
description: Impara come convertire shapefile in geojson usando Aspose.GIS per .NET.
  La guida copre anche la copia di attributi tra layer e la generazione di file geojson
  con c#.
keywords:
- convert shapefile to geojson
- export shapefile as geojson
- aspose gis conversion
- read shapefile c#
- write geojson c#
linktitle: Estrai le feature in GeoJSON
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  headline: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert shapefile to geojson using Aspose.GIS for .NET.
    The guide also covers copy attributes between layers and c# generate geojson file.
  name: Convert Shapefile to GeoJSON with Aspose.GIS for .NET
  steps:
  - name: Open Input Shapefile
    text: The `VectorLayer.Open` method reads a Shapefile and returns an enumerable
      collection of `Feature` objects that you can iterate over.
  - name: Create Output GeoJSON
    text: '`VectorLayer.Create` with the `Drivers.GeoJson` driver creates an empty
      GeoJSON file ready to receive features.'
  - name: Copy Attributes Between Layers
    text: '`CopyAttributes` copies the attribute schema (field names and data types)
      from the source Shapefile to the new GeoJSON layer in a single call.'
  - name: Process Features
    text: Iterate through each feature in the Shapefile so you can apply any custom
      logic before writing it out.
  - name: Filter Features by Date
    text: In this example we skip records whose `dob` (date of birth) field is missing
      or earlier than 1 Jan 1982. Adjust the filter to match your own data requirements.
  - name: Construct a New Feature (C# Generate GeoJSON File)
    text: A `Feature` represents a single spatial element containing geometry and
      attribute data. Here we build a new `Feature` for the GeoJSON layer, copy the
      geometry and attribute values, and add it to the output. This is the core of
      *c# generate geojson file*. Congratulations! You’ve successfully **conver
  type: HowTo
- questions:
  - answer: Visit the [Aspose.GIS documentation](https://reference.aspose.com/gis/net/)
      for in‑depth information.
    question: Where can I find more documentation?
  - answer: You can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license?
  - answer: Join the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I seek support?
  - answer: Yes, you can find the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can buy the product [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Converti Shapefile in GeoJSON con Aspose.GIS per .NET
url: /it/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti Shapefile in GeoJSON con Aspose.GIS per .NET

## Introduzione
In questo tutorial completo, passo‑per‑passo, imparerai **come convertire shapefile in geojson** utilizzando la potente libreria Aspose.GIS per .NET. Che tu stia creando un servizio web di mappatura, preparando dati per un'app GIS mobile, o semplicemente abbia bisogno di scambiare dati tra formati, questa guida ti mostra esattamente cosa fare, perché ogni passaggio è importante e come evitare gli errori più comuni.

## Risposte rapide
- **Qual è l'argomento di questo tutorial?** Conversione di un Shapefile in un file GeoJSON, copia degli attributi tra layer e generazione dell'output con C#.
- **Quale libreria è necessaria?** Aspose.GIS per .NET.
- **È necessaria una licenza?** È richiesta una licenza temporanea o completa per la produzione; una versione di prova gratuita è sufficiente per la valutazione.
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per una conversione di base.
- **Posso eseguirlo su .NET Core/.NET 6?** Sì – il codice funziona su tutte le versioni .NET supportate.

## Cos'è la conversione di shapefile in GeoJSON?
Convertire un Shapefile in GeoJSON significa leggere le feature vettoriali dal classico formato ESRI Shapefile e scriverle in un documento GeoJSON moderno e adatto al web. Questa trasformazione ti consente di inserire i dati GIS direttamente nelle librerie JavaScript di mappatura come Leaflet o Mapbox GL, e semplifica lo scambio di dati tra strumenti GIS desktop e API web.

## Perché utilizzare Aspose.GIS per questa conversione?
Aspose.GIS astrae l'analisi binaria di basso livello, supporta oltre 50 formati di input e output, e può elaborare dataset di centinaia di pagine senza caricare l'intero file in memoria. La libreria fornisce inoltre un'API pulita e orientata agli oggetti che funziona su .NET Framework, .NET Core e .NET 5/6, così puoi dedicare tempo alla logica di business invece che alle particolarità dei formati.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Aspose.GIS per .NET: assicurati di avere la libreria installata. In caso contrario, puoi scaricarla dalla [pagina Aspose.GIS per .NET](https://releases.aspose.com/gis/net/).
- Dati Shapefile: disponi di uno Shapefile pronto per l'input. Se ti servono dati di esempio, li trovi nella [documentazione Aspose.GIS](https://reference.aspose.com/gis/net/).
- Ambiente .NET: configura un ambiente .NET per eseguire il codice fornito.
- Directory dei documenti: definisci il percorso della tua directory dei documenti nello snippet di codice.

Ora che hai tutto pronto, iniziamo a convertire lo shapefile in geojson!

## Come convertire Shapefile in GeoJSON
Carica lo Shapefile di origine, crea un layer GeoJSON di destinazione, copia lo schema degli attributi, filtra i record e scrivi i risultati—tutto in pochi passaggi concisi. Il flusso di lavoro completo si adatta comodamente in un unico blocco `using`, garantendo il rilascio automatico delle risorse.

### Passo 1: Apri lo Shapefile di input
Il metodo `VectorLayer.Open` legge uno Shapefile e restituisce una collezione enumerabile di oggetti `Feature` che puoi iterare.

```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```

### Passo 2: Crea il GeoJSON di output
`VectorLayer.Create` con il driver `Drivers.GeoJson` crea un file GeoJSON vuoto pronto a ricevere le feature.

```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```

### Passo 3: Copia gli attributi tra i layer
`CopyAttributes` copia lo schema degli attributi (nomi dei campi e tipi di dati) dallo Shapefile di origine al nuovo layer GeoJSON in una singola chiamata.

```csharp
outputLayer.CopyAttributes(inputLayer);
```

### Passo 4: Elabora le feature
Itera su ogni feature nello Shapefile in modo da poter applicare logiche personalizzate prima di scriverla.

```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```

### Passo 5: Filtra le feature per data
In questo esempio ignoriamo i record il cui campo `dob` (data di nascita) è mancante o precedente al 1 gen 1982. Regola il filtro per adattarlo ai requisiti dei tuoi dati.

```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```

### Passo 6: Costruisci una nuova Feature (C# genera file GeoJSON)
Una `Feature` rappresenta un singolo elemento spaziale contenente geometria e dati attributo.  
Qui creiamo una nuova `Feature` per il layer GeoJSON, copiamo la geometria e i valori degli attributi, e la aggiungiamo all'output. Questo è il nucleo di *c# generate geojson file*.

```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```

Congratulazioni! Hai convertito con successo **shapefile in geojson** e hai imparato come **copiare gli attributi tra i layer** lungo il percorso.

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| Il file di output è vuoto | `CopyAttributes` chiamato dopo che il layer di output è stato chiuso | Assicurati che il blocco `using` per `outputLayer` rimanga aperto fino a dopo l'aggiunta di tutte le feature. |
| Il filtro data rimuove tutti i record | Nome campo errato o formato data inatteso | Verifica il nome dell'attributo (`dob`) e usa `GetValue<string>` se le date sono memorizzate come stringhe. |
| Eccezione di licenza | Esecuzione senza una licenza Aspose.GIS valida in produzione | Applica una licenza temporanea o completa come descritto nella documentazione Aspose. |

## Domande frequenti
**D: Dove posso trovare ulteriore documentazione?**  
A: Visita la [documentazione Aspose.GIS](https://reference.aspose.com/gis/net/) per informazioni dettagliate.

**D: Come posso ottenere una licenza temporanea?**  
A: Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

**D: Dove posso trovare supporto?**  
A: Unisciti al [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per supporto della community e discussioni.

**D: È disponibile una versione di prova gratuita?**  
A: Sì, puoi trovare la versione di prova gratuita [qui](https://releases.aspose.com/).

**D: Dove posso acquistare Aspose.GIS per .NET?**  
A: Puoi acquistare il prodotto [qui](https://purchase.aspose.com/buy).

## Conclusione
In questo tutorial abbiamo esplorato l'intero processo di **convertire shapefile in geojson** usando Aspose.GIS per .NET, dimostrato come **copiare gli attributi tra i layer**, e mostrato un modo pulito per *c# generate geojson file*. Sperimenta con filtri diversi, dataset più grandi o trasformazioni geometriche aggiuntive per sfruttare appieno le capacità della libreria.

---

**Ultimo aggiornamento:** 2026-07-05  
**Testato con:** Aspose.GIS per .NET (ultima versione stabile)  
**Autore:** Aspose

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Tutorial correlati

- [Come convertire GeoJSON in File GDB usando Aspose.GIS per .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Come leggere GeoJSON dallo stream con Aspose.GIS per .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Come convertire GeoJSON in TopoJSON con Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}