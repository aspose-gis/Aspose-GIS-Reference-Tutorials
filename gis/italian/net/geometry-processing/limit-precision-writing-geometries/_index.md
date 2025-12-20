---
date: 2025-12-20
description: Scopri come limitare la precisione durante la scrittura di geometrie
  con Aspose.GIS per .NET. Questa guida passo‑passo ti aiuta a gestire i dati spaziali
  con un controllo preciso delle coordinate.
linktitle: Limit Precision Writing Geometries
second_title: Aspose.GIS .NET API
title: Come limitare la precisione nella scrittura di geometrie con Aspose.GIS
url: /it/net/geometry-processing/limit-precision-writing-geometries/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come limitare la precisione nella scrittura di geometrie con Aspose.GIS

Se ti chiedi **come limitare la precisione** quando scrivi geometrie in un'applicazione GIS .NET, Aspose.GIS per .NET offre un modo semplice e ad alte prestazioni per controllare l'arrotondamento delle coordinate. In questo tutorial percorreremo l'intero processo—dalla configurazione dell'ambiente alla verifica che l'output rispetti le regole di precisione da te definite.

## Risposte rapide
- **Cosa significa “limitare la precisione”?** Arrotonda i valori delle coordinate a un numero definito di cifre decimali durante la scrittura di un file spaziale.  
- **Quale formato è usato nell'esempio?** GeoJSON, ma le stesse opzioni si applicano ad altri formati supportati.  
- **È necessaria una licenza per provare?** Una versione di prova gratuita è sufficiente per sviluppo e test; è necessaria una licenza commerciale per la produzione.  
- **Quali versioni .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso controllare separatamente la precisione della coordinata Z?** Sì—usa `ZPrecisionModel` per impostare valori esatti o arrotondati.

## Come limitare la precisione quando si scrivono geometrie
Limitare la precisione è fondamentale quando hai bisogno di una rappresentazione coerente delle coordinate tra diversi strumenti GIS, ridurre le dimensioni del file o rispettare standard di scambio dati. Di seguito definiremo le opzioni di precisione, scriveremo una geometria e poi la leggeremo nuovamente per confermare l'arrotondamento.

## Prerequisiti

### 1. Download e installazione
Scarica l'ultima versione del pacchetto Aspose.GIS per .NET dal sito ufficiale: [download link](https://releases.aspose.com/gis/net/). Segui la guida di installazione per aggiungere il pacchetto NuGet al tuo progetto.

### 2. Importazione dei namespace
Aggiungi i namespace necessari così da poter accedere alle classi GIS e alle utility di supporto.

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

## Guida passo‑passo

### Passo 1: Definire le opzioni di precisione
Crea un'istanza di `GeoJsonOptions` e indica ad Aspose.GIS quante cifre decimali desideri per le coordinate X/Y e Z.

```csharp
var options = new GeoJsonOptions
{
    // Limit X and Y coordinates to 3 fractional digits.
    XYPrecisionModel = PrecisionModel.Rounding(3),

    // Write all fractional digits of the Z coordinate.
    ZPrecisionModel = PrecisionModel.Exact
};
```

### Passo 2: Impostare il percorso di output
Specifica dove verrà salvato il file GeoJSON risultante.

```csharp
var path = "Your Document Directory" + "LimitPrecisionWhenWritingGeometries_out.json";
```

### Passo 3: Creare e popolare la geometria
Apri un nuovo `VectorLayer` con le opzioni definite sopra, costruisci una geometria `Point` e aggiungila al layer.

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

### Passo 4: Leggere e verificare la precisione
Apri il file appena creato e stampa le coordinate. Dovresti vedere i valori X/Y arrotondati a tre cifre decimali mentre il valore Z rimane esatto.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.GeoJson))
{
    var point = (IPoint)layer[0].Geometry;

    // Output: 1.889, 1.001, 1.123456789
    Console.WriteLine("{0}, {1}, {2}", point.X, point.Y, point.Z);
}
```

## Problemi comuni e consigli

- **Errori di percorso:** Assicurati che la directory in `path` esista o usa `Path.Combine` con `Environment.CurrentDirectory` per costruire un percorso file sicuro.  
- **Precisione non applicata:** Verifica di passare l'oggetto `GeoJsonOptions` quando crei il layer; altrimenti verrà usata la precisione predefinita (double completo).  
- **Dataset di grandi dimensioni:** Per operazioni in batch, considera di riutilizzare una singola istanza di `VectorLayer` e aggiungere le feature in blocco per migliorare le prestazioni.

## Domande frequenti

**D: Aspose.GIS per .NET è compatibile con altri formati GIS?**  
R: Sì, supporta Shapefile, GeoJSON, KML, GML e molti altri, consentendo conversioni fluide tra i formati.

**D: Posso provare Aspose.GIS per .NET prima di acquistare?**  
R: Assolutamente. Una versione di prova gratuita è disponibile dalla pagina di download, offrendoti pieno accesso a tutte le funzionalità per la valutazione.

**D: Come ottengo una licenza temporanea per i test?**  
R: Le licenze di valutazione temporanee possono essere generate tramite il portale licenze Aspose; sono valide per 30 giorni.

**D: Dove posso trovare aiuto se incontro problemi?**  
R: Il forum Aspose.GIS e il tag Stack Overflow `aspose-gis` sono ottimi posti per porre domande e trovare soluzioni della community.

**D: La libreria funziona sia per script piccoli sia per applicazioni su scala enterprise?**  
R: Sì, Aspose.GIS è progettata per gestire tutto, dai prototipi rapidi alle applicazioni server ad alto volume.

## Conclusione
Seguendo i passaggi sopra, ora sai **come limitare la precisione** quando scrivi geometrie con Aspose.GIS per .NET. Controllare l'arrotondamento delle coordinate aiuta a mantenere i dati spaziali puliti, interoperabili e efficienti in termini di spazio—benefici chiave per qualsiasi progetto incentrato sul GIS.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose