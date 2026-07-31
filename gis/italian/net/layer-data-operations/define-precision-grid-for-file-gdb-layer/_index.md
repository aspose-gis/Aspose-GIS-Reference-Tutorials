---
date: 2026-04-24
description: Scopri come creare un geodatabase file e impostare una griglia di precisione
  per un layer File GDB usando Aspose.GIS per .NET, includendo l'aggiunta di feature
  al layer e la convalida dell'intervallo di coordinate.
keywords:
- create file geodatabase
- handle out of range
- add features layer
- configure coordinate grid
- validate coordinate range
linktitle: Definisci la griglia di precisione per il layer File GDB
second_title: Aspose.GIS .NET API
title: Crea Geodatabase File e Imposta Griglia per il Layer GDB (Aspose.GIS)
url: /it/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare la griglia per il layer File GDB in Aspose.GIS

## Introduzione
In questo tutorial **creerai oggetti file geodatabase** e imparerai come **impostare la griglia** per un layer File Geodatabase (GDB) utilizzando Aspose.GIS per .NET. Definire una griglia di precisione ti consente di **validare l’intervallo delle coordinate**, previene errori fuori intervallo e garantisce che qualsiasi operazione di **add features layer** memorizzi i dati in modo accurato. Ti guideremo passo passo, spiegheremo perché ogni impostazione è importante e ti mostreremo come **gestire scenari fuori intervallo** in modo elegante.

## Risposte rapide
- **Che cosa significa “set grid”?** Definisce la precisione delle coordinate e l’intervallo valido per un layer GIS.  
- **Perché usare una griglia di precisione?** Protegge i tuoi dati da coordinate non valide e migliora l’efficienza di memorizzazione.  
- **Quale libreria fornisce questa funzionalità?** Aspose.GIS per .NET.  
- **È necessaria una licenza?** È disponibile una versione di prova; per la produzione è richiesta una licenza commerciale.  
- **Posso usarlo con .NET Core?** Sì, Aspose.GIS supporta .NET Framework e .NET Core.

## Cos'è una griglia di precisione e perché impostarla?
Una griglia di precisione è un insieme di parametri (origine, scala, ecc.) che indica al motore GIS come arrotondare e memorizzare i valori delle coordinate. Configurando una griglia **validi automaticamente l’intervallo delle coordinate**, e qualsiasi tentativo di inserire un punto fuori dalla griglia solleverà un’eccezione, aiutandoti a **gestire scenari fuori intervallo** fin dalle fasi di sviluppo.

## Perché creare un file geodatabase con una griglia di precisione?
Creare un file geodatabase ti offre un contenitore portatile e ad alte prestazioni per dati vettoriali. Aggiungere una griglia di precisione al momento della creazione garantisce:

- **Qualità dei dati coerente** – ogni feature rispetta la stessa precisione numerica.  
- **Indicizzazione più veloce** – il motore può memorizzare le coordinate in modo più efficiente.  
- **Rilevamento precoce degli errori** – le coordinate fuori intervallo vengono intercettate prima di corrompere il dataset.

## Prerequisiti
Prima di iniziare, assicurati di avere installato quanto segue:

1. **Visual Studio** – qualsiasi versione recente (Community, Professional o Enterprise).  
2. **Aspose.GIS per .NET** – scaricalo dal [website](https://releases.aspose.com/gis/net/).  
3. **Conoscenza base di C#** – dovresti sentirti a tuo agio nella creazione di progetti console .NET.

## Casi d'uso comuni
- **Raccolta dati sul campo** dove i dispositivi GPS possono produrre coordinate leggermente al di fuori dell’estensione prevista.  
- **Migrazione dati** da sistemi legacy che utilizzavano precisioni di coordinate diverse.  
- **Pipeline ETL automatizzate** che devono garantire l’integrità spaziale prima di caricare i dati in un database GIS.

## Importare gli spazi dei nomi
Per prima cosa, importa gli spazi dei nomi necessari per lavorare con Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Come configurare la griglia di coordinate in un layer File GDB
Di seguito trovi una guida passo‑per‑passo che mostra esattamente come configurare la griglia, creare un layer e aggiungere **feature al layer** in modo sicuro.

### Passo 1: Creare un dataset
Iniziamo creando un nuovo dataset File Geodatabase. Qui vivrà il layer.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Passo 2: Definire le opzioni della griglia di precisione
Qui specifichiamo i parametri della griglia. Regola le origini e le scale per corrispondere al sistema di coordinate del tuo progetto.

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*Il flag `EnsureValidCoordinatesRange = true` indica ad Aspose.GIS di **validare l’intervallo delle coordinate** per ogni feature aggiunta.*

### Passo 3: Creare un layer con la griglia
Ora creiamo un nuovo layer all’interno del dataset, applicando le opzioni di griglia appena definite. Useremo il sistema di riferimento spaziale WGS84.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Passo 4: Aggiungere feature al layer
Costruiamo due feature puntuali. Il primo punto si trova all’interno della griglia, mentre il secondo cade deliberatamente fuori per dimostrare **come gestire errori fuori intervallo**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Passo 5: Gestire le eccezioni quando si aggiungono feature fuori intervallo
Il tentativo di aggiungere la seconda feature genererà un’eccezione perché la sua coordinata X (`-410`) è al di fuori della griglia definita. Catturiamo l’eccezione e mostriamo un messaggio chiaro.

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### Passo 6: Pulizia
Le istruzioni `using` chiudono e rilasciano automaticamente il dataset e il layer, garantendo che tutte le risorse vengano liberate.

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| **Eccezione: “X value … is out of valid range.”** | Le coordinate sono al di fuori della griglia di precisione. | Regola `XOrigin`, `YOrigin` o `XYScale` per includere i tuoi dati, oppure assicurati che i dati di input siano entro l’intervallo definito. |
| **Le feature non compaiono nel visualizzatore GIS** | Layer non salvato o riferimento spaziale errato. | Verifica che `SpatialReferenceSystem.Wgs84` corrisponda al CRS del visualizzatore e che `Dataset.Create` sia riuscito. |
| **Valori M ignorati** | `MScale` impostato a 0 o troppo basso. | Imposta un `MScale` ragionevole (es. `1e4`) per memorizzare i valori di misura. |

## Suggerimenti per la risoluzione dei problemi
- **Verifica attentamente le estensioni della griglia** prima di caricare grandi batch di dati; un piccolo errore di battitura in `XOrigin` può causare il rifiuto di molte righe.  
- **Registra il messaggio di eccezione** (come mostrato nel blocco try‑catch) su un file durante l’importazione automatizzata; questo facilita l’individuazione di pattern nei dati fuori intervallo.  
- **Usa `EnsureValidCoordinatesRange = false` solo per fonti dati fidate** – disattivare la validazione può portare a geometrie corrotte.

## Domande frequenti

**D: Posso usare Aspose.GIS per .NET con altri formati di file GIS?**  
R: Sì, Aspose.GIS supporta Shapefile, GeoJSON, KML e molti altri formati.

**D: Aspose.GIS per .NET è compatibile con .NET Core?**  
R: Assolutamente. La libreria funziona con .NET Framework, .NET Core e .NET 5/6+.

**D: Posso eseguire operazioni spaziali come buffering o intersezione?**  
R: Sì, l’API include metodi per il buffering, l’intersezione e il calcolo delle distanze.

**D: Aspose.GIS fornisce capacità di trasformazione delle coordinate?**  
R: Sì, puoi trasformare le geometrie tra diversi sistemi di riferimento spaziale usando gli strumenti di riproiezione integrati.

**D: È disponibile una versione di prova?**  
R: Sì, puoi scaricare una prova gratuita dal [website](https://releases.aspose.com/gis/net/).

---

**Ultimo aggiornamento:** 2026-04-24  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}