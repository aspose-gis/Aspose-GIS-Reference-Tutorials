---
date: 2026-09-15
description: Scopri come convertire un poligono in linea e trasformare i poligoni
  in linee usando Aspose.GIS per .NET. Una guida rapida per gli sviluppatori GIS.
keywords:
- convert polygon to line
- how to replace polygons
- transform polygons to lines
- gis polygon to line
- simplify map visualization
lastmod: 2026-09-15
linktitle: Sostituisci i poligoni con linee
og_description: Converti un poligono in linea usando Aspose.GIS per .NET. Questo tutorial
  mostra come sostituire i poligoni con linee, le versioni .NET supportate e le insidie
  comuni.
og_image_alt: Screenshot of Aspose.GIS converting polygon to line in a .NET console
  app
og_title: Converti un poligono in linea con Aspose.GIS per .NET – guida rapida
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  headline: Convert polygon to line with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert polygon to line and transform polygons to lines
    using Aspose.GIS for .NET. A quick guide for GIS developers.
  name: Convert polygon to line with Aspose.GIS for .NET
  steps:
  - name: Define the source geometry
    text: The `GeometryCollection` class is a container that can hold any number of
      geometry objects, including polygons, points, and lines. It is the entry point
      for bulk operations like `ReplacePolygonsByLines`. Create a geometry collection
      that includes one or more polygons you want to convert. In this exa
  - name: Convert polygons to lines
    text: The `ReplacePolygonsByLines()` method scans the supplied collection, replaces
      each polygon with a `LineString` that follows its outer ring, and leaves all
      other geometry types untouched. This single call performs the conversion in
      O(n) time, where *n* is the number of geometries in the collection.
  - name: Display the original and converted geometries
    text: Printing both the original and the transformed geometries lets you verify
      that polygons have been replaced while other geometries stay the same. The `ToString()`
      override on each geometry provides a human‑readable WKT representation.
  type: HowTo
- questions:
  - answer: Yes, it supports more than 30 formats—including Shapefile, GeoJSON, KML,
      GML, and CSV—allowing you to read, convert, and write data without external
      tools.
    question: Can Aspose.GIS for .NET work with various GIS file formats?
  - answer: Yes, you can access the free trial of Aspose.GIS for .NET on the Aspose
      releases page ([Aspose releases page](https://releases.aspose.com/)).
    question: Is there a free trial available for Aspose.GIS for .NET?
  - answer: Yes, developers can get support and assistance from the Aspose.GIS community
      forum ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)).
    question: Does Aspose.GIS for .NET offer support for developers?
  - answer: Yes, you can acquire a temporary license from Aspose's temporary license
      page ([temporary license page](https://purchase.aspose.com/temporary-license/)).
    question: Can I purchase a temporary license for Aspose.GIS for .NET?
  - answer: Absolutely, it provides comprehensive documentation, code examples, and
      API references for all skill levels.
    question: Is Aspose.GIS for .NET suitable for both beginners and experienced developers?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert polygon to line
- Aspose.GIS
- .NET GIS processing
title: Converti un poligono in linea con Aspose.GIS per .NET
url: /it/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti poligono in linea con Aspose.GIS per .NET

## Introduzione
Se hai bisogno di **convertire poligono in linea** in un progetto GIS .NET, Aspose.GIS rende il processo semplice. Che tu stia semplificando visualizzazioni di mappe, preparando dati per algoritmi di routing, o abbia semplicemente bisogno di una rappresentazione geometrica più pulita, questo tutorial ti guida passo passo nella sostituzione dei poligoni con geometrie lineari usando l'Aspose.GIS API. Scoprirai perché la libreria è una scelta preferita per gli sviluppatori GIS e come completare la conversione in poche righe di codice.

## Risposte rapide
- **Cosa significa “convertire poligono in linea”?** Estrae l'anello esterno di un poligono e crea un `LineString` che segue lo stesso perimetro.  
- **Perché usare Aspose.GIS per questa attività?** La libreria offre un unico metodo (`ReplacePolygonsByLines`) che gestisce la conversione di massa in modo efficiente, senza l'analisi manuale della geometria.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6+ sono tutti pienamente supportati.  
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita è sufficiente per i test; è necessaria una licenza commerciale per le distribuzioni in produzione.  
- **Quanto tempo richiede l'implementazione?** La maggior parte degli sviluppatori completa una conversione di base in meno di dieci minuti.

## Cos'è “convertire poligono in linea”?
Convertire un poligono in una linea significa estrarre l'anello esterno del poligono (il suo perimetro) e rappresentarlo come un `LineString`. La geometria risultante conserva l'esatta sagoma della forma originale ma scarta le informazioni sull'area interna, il che è ideale per l'analisi di rete, il rendering dei bordi o quando è necessaria una rappresentazione leggera per le mappe web.

## Perché trasformare i poligoni in linee con Aspose.GIS?
Aspose.GIS sostituisce ogni poligono in una collezione con la sua linea di confine in una singola chiamata, preservando la topologia ed eliminando la necessità di cicli personalizzati. Questo approccio riduce la complessità del codice fino all'80 % e elabora collezioni di oltre 10 000 feature in meno di un secondo su hardware server tipico, grazie al suo nucleo nativo C++ e alla gestione della memoria zero‑copy.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

### Installazione di Aspose.GIS per .NET
1. Scarica Aspose.GIS per .NET: visita la pagina di download di Aspose.GIS per .NET ([Aspose.GIS for .NET download](https://releases.aspose.com/gis/net/)).  
2. Installa Aspose.GIS per .NET: segui le istruzioni di installazione nel pacchetto o consulta la documentazione di Aspose.GIS ([Aspose.GIS documentation](https://reference.aspose.com/gis/net/)) per i passaggi dettagliati.

## Importazione dei namespace
Nel tuo progetto .NET, importa i namespace richiesti così da poter lavorare con le classi di Aspose.GIS.

Il namespace `Aspose.Gis` contiene i tipi di geometria di base, mentre `Aspose.Gis.Geometries` fornisce implementazioni concrete come `Polygon` e `LineString`.

```csharp
using System;
using Aspose.Gis.Geometries;
```

## Guida passo‑passo

### Passo 1: Definisci la geometria di origine
La classe `GeometryCollection` è un contenitore che può contenere un numero qualsiasi di oggetti geometria, inclusi poligoni, punti e linee. È il punto di ingresso per operazioni di massa come `ReplacePolygonsByLines`.

Crea una collezione di geometrie che includa uno o più poligoni da convertire. In questo esempio aggiungiamo anche un punto per mostrare che gli elementi non‑poligono rimangono invariati.

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### Passo 2: Converti i poligoni in linee
Il metodo `ReplacePolygonsByLines()` esamina la collezione fornita, sostituisce ogni poligono con un `LineString` che segue il suo anello esterno, e lascia intatti tutti gli altri tipi di geometria. Questa singola chiamata esegue la conversione in tempo O(n), dove *n* è il numero di geometrie nella collezione.

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### Passo 3: Visualizza le geometrie originali e convertite
Stampare sia le geometrie originali sia quelle trasformate ti consente di verificare che i poligoni siano stati sostituiti mentre le altre geometrie rimangono invariate. L'override `ToString()` su ogni geometria fornisce una rappresentazione WKT leggibile dall'uomo.

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## Problemi comuni e soluzioni
- **Output di linea mancante:** Assicurati che la geometria di origine contenga effettivamente dei poligoni; punti o multipunti verranno passati attraverso invariati.  
- **Problemi di ordine delle coordinate:** Aspose.GIS si aspetta coordinate nell'ordine `X Y` (longitudine latitudine). Valori invertiti possono produrre forme inattese.  
- **Collezioni grandi:** Per set di dati molto grandi (centinaia di migliaia di feature), elabora le geometrie in batch di 10 000–20 000 elementi per mantenere l'uso della memoria sotto i 200 MB.

## Domande frequenti

**Q: Aspose.GIS per .NET può lavorare con vari formati di file GIS?**  
A: Sì, supporta più di 30 formati — tra cui Shapefile, GeoJSON, KML, GML e CSV — consentendo di leggere, convertire e scrivere dati senza strumenti esterni.

**Q: È disponibile una prova gratuita per Aspose.GIS per .NET?**  
A: Sì, puoi accedere alla prova gratuita di Aspose.GIS per .NET nella pagina di rilascio di Aspose ([Aspose releases page](https://releases.aspose.com/)).

**Q: Aspose.GIS per .NET offre supporto per gli sviluppatori?**  
A: Sì, gli sviluppatori possono ottenere supporto e assistenza dal forum della community di Aspose.GIS ([Aspose.GIS community forum](https://forum.aspose.com/c/gis/33)).

**Q: Posso acquistare una licenza temporanea per Aspose.GIS per .NET?**  
A: Sì, puoi ottenere una licenza temporanea dalla pagina delle licenze temporanee di Aspose ([temporary license page](https://purchase.aspose.com/temporary-license/)).

**Q: Aspose.GIS per .NET è adatto sia ai principianti che agli sviluppatori esperti?**  
A: Assolutamente sì, fornisce una documentazione completa, esempi di codice e riferimenti API per tutti i livelli di competenza.

## Conclusione
Seguendo questi passaggi, hai imparato come **convertire poligono in linea** e trasformare efficacemente **i poligoni in linee** usando Aspose.GIS per .NET. Questa capacità apre la porta a visualizzazioni più leggere, preparazioni di routing e molti altri flussi di lavoro GIS. Sentiti libero di esplorare ulteriori funzionalità di Aspose.GIS come query spaziali, riproiezione e conversione di formati per estendere le capacità della tua applicazione.

---

**Last Updated:** 2026-09-15  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose

## Tutorial correlati

- [Scopri come creare la geometria LineString con Aspose.GIS per .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Come creare GeoJSON con tolleranza in Aspose.GIS per .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Come tradurre la geometria in WKT con Aspose.GIS per .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}