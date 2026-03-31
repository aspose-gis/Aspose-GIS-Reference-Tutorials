---
date: 2025-12-28
description: Impara come impostare la griglia per un layer File GDB usando Aspose.GIS
  per .NET, includendo l'aggiunta di feature al layer e la convalida dell'intervallo
  di coordinate.
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: Come impostare la griglia per il layer File GDB in Aspose.GIS
url: /it/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare la griglia per un layer File GDB in Aspose.GIS

## Introduzione
In questo tutorial imparerai **come impostare la griglia** per un layer File Geodatabase (GDB) utilizzando Aspose.GIS per .NET. Impostare una griglia di precisione ti aiuta a **convalidare l'intervallo delle coordinate**, previene errori di fuori‑intervallo e garantisce che i dati a cui **aggiungi feature al layer** rimangano accurati e affidabili. Ti guideremo passo dopo passo, spiegheremo perché le impostazioni sono importanti e ti mostreremo come gestire le difficoltà più comuni.

## Risposte rapide
- **Cosa significa “impostare la griglia”?** Definisce la precisione delle coordinate e l'intervallo valido per un layer GIS.  
- **Perché usare una griglia di precisione?** Protegge i tuoi dati da coordinate non valide e migliora l'efficienza di archiviazione.  
- **Quale libreria fornisce questa funzionalità?** Aspose.GIS per .NET.  
- **È necessaria una licenza?** È disponibile una versione di prova; per la produzione è richiesta una licenza commerciale.  
- **Posso usarla con .NET Core?** Sì, Aspose.GIS supporta .NET Framework e .NET Core.

## Cos'è una griglia di precisione e perché impostarla?
Una griglia di precisione è un insieme di parametri (origine, scala, ecc.) che indica al motore GIS come arrotondare e memorizzare i valori delle coordinate. Definendo una griglia **convalidi automaticamente l'intervallo delle coordinate** e qualsiasi tentativo di inserire un punto al di fuori della griglia genererà un'eccezione, aiutandoti a **gestire gli errori di fuori intervallo** già nelle fasi iniziali dello sviluppo.

## Prerequisiti
Prima di iniziare, assicurati di avere installato quanto segue:

1. **Visual Studio** – qualsiasi versione recente (Community, Professional o Enterprise).  
2. **Aspose.GIS per .NET** – scaricalo dal [sito web](https://releases.aspose.com/gis/net/).  
3. **Conoscenza di base di C#** – dovresti sentirti a tuo agio nella creazione di progetti console .NET.

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

## Come impostare la griglia in un layer File GDB
Di seguito trovi una guida passo‑per‑passo che mostra esattamente come configurare la griglia, creare un layer e aggiungere in modo sicuro **feature al layer**.

### Passo 1: Creare un dataset
Iniziamo creando un nuovo dataset File Geodatabase. È qui che vivrà il layer.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Passo 2: Definire le opzioni della griglia di precisione
Qui specifichiamo i parametri della griglia. Regola le origini e le scale per farle corrispondere al sistema di coordinate del tuo progetto.

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

*Il flag `EnsureValidCoordinatesRange = true` indica ad Aspose.GIS di **convalidare l'intervallo delle coordinate** per ogni feature che aggiungi.*

### Passo 3: Creare un layer con la griglia
Ora creiamo un nuovo layer all'interno del dataset, applicando le opzioni di griglia appena definite. Useremo il sistema di riferimento spaziale WGS84.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Passo 4: Aggiungere feature al layer
Costruiamo due feature puntuali. Il primo punto si trova all'interno della griglia, mentre il secondo è deliberatamente fuori per dimostrare **come gestire gli errori di fuori intervallo**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Passo 5: Gestire le eccezioni quando si aggiungono feature fuori intervallo
Il tentativo di aggiungere la seconda feature genererà un'eccezione perché la sua coordinata X (`-410`) è al di fuori della griglia definita. Catturiamo l'eccezione e mostriamo un messaggio chiaro.

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
Le istruzioni `using` chiudono e rilasciano automaticamente il dataset e il layer, garantendo il rilascio di tutte le risorse.

## Problemi comuni e soluzioni
| Problema | Perché si verifica | Soluzione |
|----------|--------------------|-----------|
| **Eccezione: “Il valore X … è fuori dall'intervallo valido.”** | Le coordinate sono al di fuori della griglia di precisione. | Regola `XOrigin`, `YOrigin` o `XYScale` per includere i tuoi dati, oppure assicurati che i dati di input siano entro l'intervallo definito. |
| **Le feature non compaiono nel visualizzatore GIS** | Layer non salvato o riferimento spaziale errato. | Verifica che `SpatialReferenceSystem.Wgs84` corrisponda al CRS del visualizzatore e che `Dataset.Create` sia riuscito. |
| **Valori M ignorati** | `MScale` impostato a 0 o troppo basso. | Imposta un `MScale` ragionevole (ad es. `1e4`) per memorizzare i valori di misura. |

## Domande frequenti

**D: Posso usare Aspose.GIS per .NET con altri formati di file GIS?**  
R: Sì, Aspose.GIS supporta Shapefile, GeoJSON, KML e molti altri formati.

**D: Aspose.GIS per .NET è compatibile con .NET Core?**  
R: Assolutamente. La libreria funziona con .NET Framework, .NET Core e .NET 5/6+.

**D: Posso eseguire operazioni spaziali come buffering o intersezione?**  
R: Sì, l'API include metodi per il buffering, l'intersezione e il calcolo delle distanze.

**D: Aspose.GIS offre capacità di trasformazione delle coordinate?**  
R: Sì, puoi trasformare geometrie tra diversi sistemi di riferimento spaziale usando gli strumenti di riproiezione integrati.

**D: È disponibile una versione di prova?**  
R: Sì, puoi scaricare una prova gratuita dal [sito web](https://releases.aspose.com/gis/net/).

---

**Ultimo aggiornamento:** 2025-12-28  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}