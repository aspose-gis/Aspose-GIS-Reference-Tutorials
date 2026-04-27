---
date: 2026-01-13
description: Scopri come convertire shapefile in geojson usando Aspose.GIS per .NET.
  La guida copre anche come copiare gli attributi tra i layer e generare un file geojson
  con C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Come convertire Shapefile in GeoJSON usando Aspose.GIS per .NET
url: /it/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti Shapefile in GeoJSON con Aspose.GIS per .NET

## Introduzione
In questo tutorial completo, passo per passo, imparerai **come convertire shapefile in geojson** utilizzando la potente libreria Aspose.GIS per .NET. Che tu stia creando un servizio di mapping web, preparando dati per un'app GIS mobile, o semplicemente abbia bisogno di scambiare dati tra formati, questa guida ti mostra esattamente cosa fare, perché ogni passaggio è importante e come evitare gli errori più comuni.

## Risposte rapide
- **Cosa copre questo tutorial?** Conversione di un Shapefile in un file GeoJSON, copia degli attributi tra i layer e generazione dell'output con C#.
- **Quale libreria è necessaria?** Aspose.GIS per .NET.
- **È necessaria una licenza?** È richiesta una licenza temporanea o completa per la produzione; una versione di prova gratuita è sufficiente per la valutazione.
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per una conversione di base.
- **Posso eseguirlo su .NET Core/.NET 6?** Sì – il codice funziona su tutte le versioni .NET supportate.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- Aspose.GIS per .NET: Verifica di aver installato la libreria. In caso contrario, puoi scaricarla dalla [pagina Aspose.GIS per .NET](https://releases.aspose.com/gis/net/).
- Dati Shapefile: Disponi di uno Shapefile pronto per l'input. Se ti servono dati di esempio, li trovi nella [documentazione Aspose.GIS](https://reference.aspose.com/gis/net/).
- Ambiente .NET: Configura un ambiente .NET per eseguire il codice fornito.
- Directory dei documenti: Definisci il percorso della tua directory dei documenti nello snippet di codice.

Ora che hai tutto pronto, iniziamo a convertire shapefile in geojson!

## Che cosa significa “convert shapefile to geojson”?
Convertire un Shapefile in GeoJSON significa leggere le feature vettoriali dal classico formato ESRI Shapefile e scriverle in un documento GeoJSON moderno e adatto al web. GeoJSON è ampiamente usato nelle librerie di mapping JavaScript (Leaflet, Mapbox GL) e nelle API, rendendo la conversione un'operazione frequente nello sviluppo GIS.

## Perché usare Aspose.GIS per questa conversione?
Aspose.GIS astrae i dettagli a basso livello dei formati di file, consente di copiare le tabelle degli attributi senza sforzo e fornisce un'API pulita e orientata agli oggetti che funziona su .NET Framework, .NET Core e .NET 5/6. Questo ti permette di concentrarti sulla logica di business invece di dover analizzare file binari.

## Importa gli spazi dei nomi
Per prima cosa, includi gli spazi dei nomi necessari nel tuo codice:

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Questi spazi dei nomi sono essenziali per lavorare con le funzionalità di Aspose.GIS.

## Come convertire Shapefile in GeoJSON
Di seguito trovi l’intero flusso di lavoro suddiviso in passaggi chiari. Ogni passaggio include una breve spiegazione seguita dal blocco di codice da copiare nel tuo progetto.

### Passo 1: Apri lo Shapefile di input
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
Apri lo Shapefile di input usando il metodo `VectorLayer.Open`. Questo ti restituisce una collezione enumerabile di oggetti `Feature`.

### Passo 2: Crea il GeoJSON di output
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
Crea il file di output con il metodo `VectorLayer.Create`, specificando il driver `Drivers.GeoJson`.

### Passo 3: Copia gli attributi tra i layer
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Questa singola riga copia lo schema degli attributi (nomi dei campi, tipi) dallo Shapefile sorgente al nuovo layer GeoJSON — esattamente ciò che descrive la keyword secondaria *copy attributes between layers*.

### Passo 4: Elabora le feature
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Itera su ogni feature nello Shapefile così da poter applicare logiche personalizzate prima di scriverla.

### Passo 5: Filtra le feature per data
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
In questo esempio ignoriamo i record il cui campo `dob` (date of birth) è mancante o precedente al 1 gen 1982. Sentiti libero di modificare il filtro per adattarlo ai tuoi requisiti.

### Passo 6: Costruisci una nuova feature (C# Generate GeoJSON File)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Qui creiamo una nuova `Feature` per il layer GeoJSON, copiamo la geometria e i valori degli attributi, e la aggiungiamo all'output. Questo è il cuore di *c# generate geojson file*.

Congratulazioni! Hai **convertito shapefile in geojson** con successo e hai imparato come copiare gli attributi tra i layer lungo il percorso.

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|---------------|-----------|
| Il file di output è vuoto | `CopyAttributes` chiamato dopo la chiusura del layer di output | Assicurati che il blocco `using` per `outputLayer` rimanga aperto fino a dopo l'aggiunta di tutte le feature. |
| Il filtro data rimuove tutti i record | Nome campo errato o formato data inatteso | Verifica il nome dell'attributo (`dob`) e usa `GetValue<string>` se le date sono memorizzate come stringhe. |
| Eccezione di licenza | Esecuzione senza licenza valida di Aspose.GIS in produzione | Applica una licenza temporanea o completa come descritto nella documentazione di Aspose. |

## Domande frequenti
**D: Dove posso trovare altra documentazione?**  
R: Visita la [documentazione Aspose.GIS](https://reference.aspose.com/gis/net/) per informazioni dettagliate.

**D: Come posso ottenere una licenza temporanea?**  
R: Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

**D: Dove posso chiedere supporto?**  
R: Unisciti al [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per supporto della community e discussioni.

**D: È disponibile una versione di prova gratuita?**  
R: Sì, la prova gratuita è disponibile [qui](https://releases.aspose.com/).

**D: Dove posso acquistare Aspose.GIS per .NET?**  
R: Puoi acquistare il prodotto [qui](https://purchase.aspose.com/buy).

## Conclusione
In questo tutorial abbiamo esplorato l’intero processo di **convert shapefile to geojson** usando Aspose.GIS per .NET, dimostrato come copiare gli attributi tra i layer e mostrato un modo pulito per *c# generate geojson file*. Sperimenta con filtri diversi, dataset più grandi o trasformazioni geometriche aggiuntive per sfruttare appieno le potenzialità della libreria.

---

**Ultimo aggiornamento:** 2026-01-13  
**Testato con:** Aspose.GIS per .NET (ultima versione stabile)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}