---
date: 2026-01-13
description: Scopri come ritagliare le funzionalità dei layer con Aspose.GIS per .NET,
  inclusi come ritagliare un raster con un poligono, estrarre la dimensione delle
  celle del raster e recuperare l’estensione del raster. Scarica subito la tua versione
  di prova gratuita.
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: Come ritagliare le feature del layer con Aspose.GIS per .NET
url: /it/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ritagliare le funzionalità del layer

## Introduzione
In questo tutorial imparerai **come ritagliare le funzionalità del layer** usando Aspose.GIS per .NET, un approccio potente che ti consente di **ritagliare raster con poligono**, **estrarre la dimensione delle celle raster** e **recuperare l'estensione del raster** per un'analisi geospaziale precisa. Che tu stia preparando dati per una mappa web, ritagliando immagini satellitari o isolando una regione di interesse, questa guida passo‑passo ti mostra esattamente come completare il lavoro.

## Risposte rapide
- **Cosa significa “crop layer”?** Ritaglia un layer raster o vettoriale ai limiti di una geometria fornita.  
- **Quale geometria è usata in questo esempio?** Un poligono definito in formato WKT.  
- **Posso estrarre la dimensione della cella dopo il ritaglio?** Sì – la proprietà `CellSize` fornisce quell'informazione.  
- **È necessaria una licenza per eseguire il codice?** Una licenza temporanea è sufficiente per la valutazione; è necessaria una licenza completa per la produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Cos'è “come ritagliare il layer”?
Ritagliare un layer significa limitare il dataset a una specifica area geografica, scartando tutto ciò che si trova al di fuori della forma definita. Questo riduce la dimensione del file, velocizza l'elaborazione e concentra l'analisi sulla regione di tuo interesse.

## Perché usare Aspose.GIS per il ritaglio?
- **Gestione raster ad alte prestazioni** – ideale per file GeoTiff di grandi dimensioni.  
- **API semplice** – chiamata `Crop` in una riga con qualsiasi geometria.  
- **Compatibilità .NET completa** – funziona in applicazioni desktop, server e cloud.  
- **Gestione accurata del riferimento spaziale** – preserva automaticamente le informazioni CRS.

## Prerequisiti
Prima di immergerti nella magia della manipolazione geospaziale, assicurati di avere i seguenti prerequisiti:

- Libreria Aspose.GIS per .NET: Assicurati di aver installato la libreria Aspose.GIS nel tuo progetto .NET. Puoi scaricarla da [qui](https://releases.aspose.com/gis/net/).  
- Directory dei documenti: Configura una directory per archiviare i tuoi documenti. Sostituisci `"Your Document Directory"` nel codice fornito con il percorso reale della tua directory dei documenti.

Ora, immergiamoci nella guida passo‑passo.

## Importare gli spazi dei nomi
Inizia importando gli spazi dei nomi necessari per sfruttare tutta la potenza di Aspose.GIS:

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Passo 1: Aprire e ritagliare il layer (ritagliare raster con poligono)
Inizia aprendo il layer GeoTiff e ritagliandolo in base a un poligono definito. Questo garantisce che i tuoi dati geospaziali siano affinati a una specifica area di interesse.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Passo 2: Recuperare le informazioni del raster (estrarre la dimensione della cella raster e recuperare l'estensione del raster)
Una volta che il layer è stato ritagliato, estrai le informazioni essenziali sul dato raster, come la dimensione della cella, il sistema di riferimento spaziale e i limiti.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Passo 3: Visualizzare le informazioni
Stampa le informazioni estratte per comprendere l'impatto del processo di ritaglio sui tuoi dati geospaziali.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Ripeti questi passaggi secondo necessità per affinare e personalizzare i tuoi dati geospaziali in modo da soddisfare requisiti di progetto specifici.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Orientamento del poligono errato** | Assicurati che il poligono WKT segua la regola della mano destra (contro‑orario per gli anelli esterni). |
| **Riferimento spaziale mancante** | Verifica che il GeoTiff di origine contenga un CRS; altrimenti, impostane uno manualmente prima del ritaglio. |
| **Rallentamento delle prestazioni su raster di grandi dimensioni** | Usa `layer.Crop` su una copia down‑sampled o elabora il raster a tasselli. |

## Domande frequenti
### D: È disponibile una licenza temporanea per Aspose.GIS per .NET?
Sì, puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### D: Dove posso trovare la documentazione completa per Aspose.GIS per .NET?
La documentazione è disponibile [qui](https://reference.aspose.com/gis/net/).

### D: Come posso richiedere supporto o entrare in contatto con la community per Aspose.GIS per .NET?
Visita il [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per supporto e interazione con la community.

### D: Posso scaricare una versione di prova gratuita di Aspose.GIS per .NET?
Sì, puoi scaricare una versione di prova gratuita [qui](https://releases.aspose.com/).

### D: Dove posso acquistare Aspose.GIS per .NET?
Puoi acquistare la libreria [qui](https://purchase.aspose.com/buy).

### D: Posso ritagliare più layer in un'unica esecuzione?
Sì—itera su ciascun layer e applica la stessa chiamata `Crop` con la geometria desiderata.

### D: L'API supporta altri formati raster (ad es., JPEG2000)?
Aspose.GIS supporta tutti i formati esposti dai driver GDAL sottostanti, inclusi JPEG2000, PNG e altri.

## Conclusione
Seguendo questa guida ora sai **come ritagliare le funzionalità del layer** in modo efficiente con Aspose.GIS per .NET. Puoi facilmente **ritagliare raster con poligono**, **estrarre la dimensione della cella raster** e **recuperare l'estensione del raster** per soddisfare le esigenze di qualsiasi progetto. Esplora ulteriori API per la riproiezione, lo styling raster e l'analisi vettoriale per sbloccare il pieno potenziale dei tuoi flussi di lavoro geospaziali.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-01-13  
**Testato con:** Aspose.GIS 24.10 per .NET  
**Autore:** Aspose  

---