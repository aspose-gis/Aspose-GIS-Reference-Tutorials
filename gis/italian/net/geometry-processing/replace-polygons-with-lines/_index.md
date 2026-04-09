---
date: 2026-04-09
description: Scopri come convertire un poligono in linea e trasformare i poligoni
  in linee usando Aspose.GIS per .NET. Una guida rapida per gli sviluppatori GIS.
keywords:
- convert polygon to line
- how to replace polygons
- transform polygons to lines
linktitle: Sostituisci i poligoni con le linee
second_title: Aspose.GIS .NET API
title: Converti Poligono in Linea con Aspose.GIS per .NET
url: /it/net/geometry-processing/replace-polygons-with-lines/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti Poligono in Linea con Aspose.GIS per .NET

## Introduzione
Se hai bisogno di **convertire un poligono in linea** in un progetto GIS .NET, Aspose.GIS rende il processo semplice. Che tu stia semplificando le visualizzazioni della mappa, preparando i dati per algoritmi di routing, o abbia semplicemente bisogno di una rappresentazione geometrica più pulita, questo tutorial ti guiderà passo passo nella sostituzione dei poligoni con geometrie lineari usando l'API di Aspose.GIS.

## Risposte Rapide
- **Cosa significa “convertire poligono in linea”?** Trasforma le forme di poligono chiuse nelle loro stringhe di linee di confine.  
- **Perché usare Aspose.GIS per questa operazione?** Fornisce un unico metodo (`ReplacePolygonsByLines`) che gestisce la conversione in modo efficiente senza dover analizzare manualmente la geometria.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6+.  
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita è sufficiente per i test; è richiesta una licenza commerciale per la produzione.  
- **Quanto tempo richiede l'implementazione?** Tipicamente meno di 10 minuti per una conversione di base.

## Che cosa è “convertire poligono in linea”?
Convertire un poligono in una linea significa estrarre l'anello esterno del poligono (il suo perimetro) e rappresentarlo come un `LineString`. La geometria risultante conserva il contorno della forma ma perde le informazioni sull'area interna, il che è utile per attività come l'analisi di rete o il rendering dei bordi.

## Perché trasformare i poligoni in linee con Aspose.GIS?
- **Semplificare le visualizzazioni:** Le linee sono più leggere da renderizzare, specialmente su mappe web.  
- **Preparare i dati per il routing:** Molti motori di routing richiedono geometrie lineari.  
- **Mantenere la topologia:** La linea conserva il confine esatto del poligono originale, garantendo precisione spaziale.  
- **Soluzione in una riga:** Il metodo `ReplacePolygonsByLines()` esegue tutto il lavoro pesante per te.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

### Installazione di Aspose.GIS per .NET
1. Scarica Aspose.GIS per .NET: visita [questo link](https://releases.aspose.com/gis/net/) per scaricare l'ultima versione.  
2. Installa Aspose.GIS per .NET: segui le istruzioni di installazione nel pacchetto o consulta la [documentazione](https://reference.aspose.com/gis/net/) per i passaggi dettagliati.

## Importa Namespace
Nel tuo progetto .NET, importa i namespace richiesti così potrai lavorare con le classi di Aspose.GIS.

```csharp
using System;
using Aspose.Gis.Geometries;
```

## Guida Passo‑Passo

### Passo 1: Definisci la geometria di origine
Crea una collezione di geometrie che includa uno o più poligoni da convertire. In questo esempio aggiungiamo anche un punto per mostrare che gli elementi non‑poligono rimangono invariati.

```csharp
var srcGeometry = Geometry.FromText(@"GeometryCollection (POLYGON((1 2, 1 4, 3 4, 3 2)), Point (5 1))");
```

### Passo 2: Converti i poligoni in linee
Chiama il metodo `ReplacePolygonsByLines()`. Questa singola chiamata analizza la collezione, sostituisce ogni poligono con la sua corrispondente rappresentazione lineare e lascia intatti gli altri tipi di geometria.

```csharp
var dstGeometry = srcGeometry.ReplacePolygonsByLines();
```

### Passo 3: Visualizza le geometrie originali e convertite
Stampa sia le geometrie originali sia quelle trasformate sulla console così potrai verificare la conversione.

```csharp
Console.WriteLine($"source: {srcGeometry.AsText()}");
Console.WriteLine($"result: {dstGeometry.AsText()}");
```

## Problemi Comuni e Soluzioni
- **Output di linea mancante:** Assicurati che la geometria di origine contenga effettivamente dei poligoni; punti o multipunti verranno passati attraverso invariati.  
- **Problemi di ordine delle coordinate:** Aspose.GIS si aspetta le coordinate nell'ordine `X Y` (longitudine latitudine). Valori invertiti possono generare forme inattese.  
- **Collezioni grandi:** Per dataset molto grandi, considera di elaborare le geometrie in batch per evitare un elevato consumo di memoria.

## Domande Frequenti

**D: Aspose.GIS per .NET può lavorare con vari formati di file GIS?**  
R: Sì, supporta Shapefile, GeoJSON, KML e molti altri formati GIS comuni.

**D: È disponibile una prova gratuita per Aspose.GIS per .NET?**  
R: Sì, puoi accedere alla prova gratuita di Aspose.GIS per .NET [qui](https://releases.aspose.com/).

**D: Aspose.GIS per .NET offre supporto per gli sviluppatori?**  
R: Sì, gli sviluppatori possono ottenere supporto e assistenza dal forum della community Aspose.GIS [qui](https://forum.aspose.com/c/gis/33).

**D: Posso acquistare una licenza temporanea per Aspose.GIS per .NET?**  
R: Sì, puoi ottenere una licenza temporanea da [qui](https://purchase.aspose.com/temporary-license/).

**D: Aspose.GIS per .NET è adatto sia ai principianti che agli sviluppatori esperti?**  
R: Assolutamente, fornisce documentazione completa, esempi di codice e riferimenti API per tutti i livelli di competenza.

## Conclusione
Seguendo questi passaggi, hai imparato a **convertire un poligono in linea** e a **trasformare efficacemente i poligoni in linee** usando Aspose.GIS per .NET. Questa capacità apre la porta a visualizzazioni più leggere, preparazioni per il routing e molti altri flussi di lavoro GIS. Sentiti libero di esplorare ulteriori funzionalità di Aspose.GIS come query spaziali, riproiezione e conversione di formati per ampliare le capacità della tua applicazione.

---

**Ultimo aggiornamento:** 2026-04-09  
**Testato con:** Aspose.GIS per .NET (ultima release)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}