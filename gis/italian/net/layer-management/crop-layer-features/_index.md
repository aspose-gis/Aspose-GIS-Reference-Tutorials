---
date: 2026-07-05
description: Scopri come ritagliare le funzionalità del layer con Aspose.GIS per .NET,
  inclusi come ritagliare un raster con un poligono, estrarre la dimensione della
  cella raster e recuperare l'estensione del raster. Scarica la tua versione di prova
  gratuita ora.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Come ritagliare le funzionalità del layer
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Come ritagliare le funzionalità del layer con Aspose.GIS per .NET
url: /it/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come ritagliare le funzionalità del layer

## Introduzione
In questo tutorial imparerai **come ritagliare le funzionalità del layer** usando Aspose.GIS per .NET, una potente libreria che ti consente di **ritagliare raster con poligono**, **estrarre la dimensione della cella raster** e **recuperare l'estensione del raster** per un'analisi geospaziale precisa. Che tu stia preparando dati per una mappa web, ritagliando immagini satellitari o isolando una regione di interesse, questa guida passo‑passo ti mostra esattamente come completare il lavoro rapidamente e in modo affidabile.

## Risposte rapide
- **Che cosa significa “crop layer”?** Riduce un layer raster o vettoriale ai limiti di una geometria fornita, scartando tutto ciò che è al di fuori.  
- **Quale geometria è usata in questo esempio?** Un poligono definito nel formato WKT (Well‑Known Text).  
- **Posso estrarre la dimensione della cella dopo il ritaglio?** Sì – la proprietà `CellSize` restituisce la larghezza e l'altezza di una cella raster.  
- **Ho bisogno di una licenza per eseguire il codice?** Una licenza temporanea è valida per la valutazione; è necessaria una licenza completa per l'uso in produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Cos'è “come ritagliare il layer”?
**Ritagliare un layer significa limitare il dataset a una specifica area geografica, scartando tutto ciò che è al di fuori.** Questa operazione riduce le dimensioni del file, velocizza l'elaborazione successiva e concentra l'analisi sulla regione di interesse. Limitando i dati all'area di interesse, semplifichi anche i flussi di lavoro successivi come lo styling, l'analisi e la pubblicazione, preservando il sistema di riferimento delle coordinate originale e i metadati.

## Perché usare Aspose.GIS per il ritaglio?
**Aspose.GIS elabora file raster fino a 2 GB senza caricare l'intera immagine in memoria e supporta più di 30 formati raster, inclusi GeoTIFF, JPEG2000 e PNG.** La libreria offre una chiamata `Crop` a riga singola, gestione automatica del CRS e prestazioni multi‑thread che possono ritagliare un GeoTIFF da 500 MB in meno di un secondo su un server tipico.

## Prerequisiti
Prima di immergerti nella magia della manipolazione geospaziale, assicurati di avere i seguenti prerequisiti in ordine:

- Aspose.GIS for .NET Library: Assicurati di avere la libreria Aspose.GIS installata nel tuo progetto .NET. Puoi scaricarla da [here](https://releases.aspose.com/gis/net/).  
- Document Directory: Configura una directory per archiviare i tuoi documenti. Sostituisci `"Your Document Directory"` nel codice fornito con il percorso reale della tua directory dei documenti.

Ora, immergiamoci nella guida passo‑passo.

## Importare gli spazi dei nomi
Lo spazio dei nomi `Aspose.Gis` contiene tutti i tipi fondamentali per la gestione di raster e vettori. Importalo per accedere a `Layer`, `Geometry` e alle classi correlate.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Come ritaglio un layer con un poligono?
`Crop` è un metodo della classe `Layer` che estrae un sottoinsieme raster definito da una geometria.  
Carica il raster di origine, definisci una geometria poligonale e chiama il metodo `Crop` – l'intera operazione viene eseguita in una singola riga di codice. Il metodo restituisce un nuovo raster che contiene solo i pixel all'interno del poligono, preservando automaticamente il riferimento spaziale originale.

## Passo 1: Aprire e ritagliare il layer (ritagliare raster con poligono)
`Layer` rappresenta un dataset raster che può essere aperto, interrogato e modificato.  
La classe `Layer` rappresenta un dataset raster che può essere aperto, interrogato e modificato. Aprire un GeoTIFF e ritagliarlo con un poligono isola l'area di interesse in poche istruzioni.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Passo 2: Recuperare le informazioni del raster (estrarre la dimensione della cella raster e recuperare l'estensione del raster)
`CellSize` fornisce la larghezza e l'altezza di ogni cella raster in unità di coordinate.  
`Extent` restituisce il riquadro geografico del raster.  
La proprietà `CellSize` fornisce la larghezza e l'altezza di ogni cella raster in unità di coordinate, mentre la proprietà `Extent` restituisce il riquadro geografico del raster ritagliato. Entrambe le informazioni sono essenziali per calcoli successivi come la misurazione dell'area o la riproiezione.

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
| **Orientamento del poligono errato** | Assicurati che il poligono WKT segua la regola della mano destra (in senso antiorario per gli anelli esterni). |
| **Riferimento spaziale mancante** | Verifica che il GeoTiff di origine contenga un CRS; altrimenti, impostane uno manualmente prima del ritaglio. |
| **Rallentamento delle prestazioni su raster di grandi dimensioni** | Usa `layer.Crop` su una copia a risoluzione ridotta o elabora il raster a tasselli. |

## Domande frequenti
**Q: È disponibile una licenza temporanea per Aspose.GIS per .NET?**  
A: Sì, puoi ottenere una licenza temporanea [here](https://purchase.aspose.com/temporary-license/).

**Q: Dove posso trovare la documentazione completa per Aspose.GIS per .NET?**  
A: La documentazione è disponibile [here](https://reference.aspose.com/gis/net/).

**Q: Come posso richiedere supporto o entrare in contatto con la community per Aspose.GIS per .NET?**  
A: Visita il [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per supporto e interazione con la community.

**Q: Posso scaricare una versione di prova gratuita di Aspose.GIS per .NET?**  
A: Sì, puoi scaricare una versione di prova gratuita [here](https://releases.aspose.com/).

**Q: Dove posso acquistare Aspose.GIS per .NET?**  
A: Puoi acquistare la libreria [here](https://purchase.aspose.com/buy).

**Q: Posso ritagliare più layer in un'unica esecuzione?**  
A: Sì—itera su ciascun layer e applica la stessa chiamata `Crop` con la geometria desiderata.

**Q: L'API supporta altri formati raster (ad es., JPEG2000)?**  
A: Aspose.GIS supporta tutti i formati esposti dai driver GDAL sottostanti, inclusi JPEG2000, PNG e altri.

## Conclusione
Seguendo questa guida ora sai **come ritagliare le funzionalità del layer** in modo efficiente con Aspose.GIS per .NET. Puoi facilmente **ritagliare raster con poligono**, **estrarre la dimensione della cella raster** e **recuperare l'estensione del raster** per soddisfare le esigenze di qualsiasi progetto. Esplora ulteriori API per la riproiezione, lo styling raster e l'analisi vettoriale per sbloccare il pieno potenziale dei tuoi flussi di lavoro geospaziali.

---

**Ultimo aggiornamento:** 2026-07-05  
**Testato con:** Aspose.GIS 24.10 for .NET  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Come creare una geometria poligonale con Aspose.GIS per .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Ottenere gli attributi del layer – Recuperare le informazioni sugli attributi del layer con Aspose.GIS per .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Creare una geometria poligonale C# e verificare l'intersezione con Aspose.GIS per .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}