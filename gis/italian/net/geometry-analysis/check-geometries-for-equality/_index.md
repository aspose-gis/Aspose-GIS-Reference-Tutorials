---
date: 2025-12-03
description: Scopri come confrontare le geometrie usando Aspose.GIS per .NET e verificare
  l'uguaglianza delle geometrie nelle tue applicazioni .NET.
language: it
linktitle: How to Compare Geometries for Equality
second_title: Aspose.GIS .NET API
title: Come confrontare le geometrie per uguaglianza con Aspose.GIS per .NET
url: /net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come confrontare le geometrie per uguaglianza usando Aspose.GIS per .NET

## Introduzione
In questo tutorial scoprirai **come confrontare le geometrie** con Aspose.GIS per .NET. Che tu stia costruendo un servizio di mappatura, eseguendo analisi spaziali o semplicemente abbia bisogno di verificare che due forme rappresentino la stessa posizione, sapere come confrontare le geometrie è fondamentale. Ti guideremo attraverso un esempio completo, end‑to‑end, che mostra come creare, modificare e testare l’uguaglianza geometrica in poche righe di codice C#.

## Risposte rapide
- **Cosa significa “confrontare le geometrie”?** Verifica se due oggetti geometrici occupano lo stesso spazio, indipendentemente da come sono stati costruiti.  
- **Quale metodo viene usato?** `SpatiallyEquals` dall’API Aspose.GIS.  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è richiesta una licenza commerciale per la produzione.  
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tempo tipico di implementazione?** Circa 5‑10 minuti per un controllo di uguaglianza di base.

## Che cos’è l’uguaglianza geometrica?
L’uguaglianza geometrica (spesso chiamata uguaglianza spaziale) significa che due geometrie rappresentano lo stesso insieme di punti sulla superficie terrestre. Due forme possono essere costruite in modo diverso — ad esempio un MultiLineString rispetto a un singolo LineString — ma risultare comunque spazialmente uguali.

## Perché usare Aspose.GIS per confrontare le geometrie?
Aspose.GIS fornisce un motore geometrico robusto e ad alte prestazioni che:
- Gestisce una vasta gamma di formati vettoriali (WKT, GeoJSON, Shapefile, ecc.).
- Offre metodi di confronto sensibili alla precisione come `SpatiallyEquals`.
- Funziona offline, senza servizi esterni, rendendolo ideale per ambienti sicuri o isolati.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

- **.NET Framework o .NET Core installati** – qualsiasi versione supportata da Aspose.GIS.  
- **Libreria Aspose.GIS per .NET** – scaricala dalla [pagina di download di Aspose.GIS](https://releases.aspose.com/gis/net/).  
- **Un IDE di sviluppo** – Visual Studio, Rider o VS Code con estensioni C#.

## Importare gli spazi dei nomi
Nel tuo progetto .NET, aggiungi le istruzioni `using` necessarie affinché il compilatore sappia dove trovare le classi GIS:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Passo 1: Definire le geometrie
Per prima cosa creiamo due geometrie da confrontare. In questo esempio `geometry1` è un `MultiLineString` composto da due segmenti, mentre `geometry2` è un singolo `LineString` che copre gli stessi punti di inizio e fine.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## Passo 2: Verificare l’uguaglianza delle geometrie
Ora utilizziamo il metodo `SpatiallyEquals` per vedere se le due forme sono considerate uguali dal motore GIS.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

La console stampa `True` perché, nonostante la costruzione diversa, entrambe le geometrie coprono la stessa linea da (0,0) a (2,2).

## Passo 3: Modificare una delle geometrie
Per illustrare come una modifica influisce sull’uguaglianza, aggiungiamo un punto extra a `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Passo 4: Ricontrollare l’uguaglianza dopo la modifica
Dopo la modifica, le geometrie non sono più identiche, quindi `SpatiallyEquals` restituisce `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

L’output `False` conferma che il punto aggiuntivo ha rotto l’uguaglianza spaziale.

## Problemi comuni e suggerimenti
- **Problemi di precisione** – Se lavori con coordinate ad altissima precisione, considera l’arrotondamento o l’uso di una sovraccarico di `SpatiallyEquals` con tolleranza.  
- **SRID diversi** – Assicurati che entrambe le geometrie condividano lo stesso Spatial Reference System Identifier (SRID) prima del confronto.  
- **Prestazioni** – Per collezioni di grandi dimensioni, i confronti in batch tramite LINQ possono ridurre l’overhead.

## Domande frequenti
**D: Posso usare Aspose.GIS per .NET con altri framework .NET?**  
R: Sì, Aspose.GIS funziona con progetti .NET Framework, .NET Core e .NET Standard.

**D: È disponibile una versione di prova gratuita?**  
R: Assolutamente. Scarica una versione di prova dalla [pagina dei rilasci di Aspose.GIS](https://releases.aspose.com/).

**D: Dove posso trovare la documentazione completa dell’API?**  
R: La documentazione dettagliata è disponibile sulla [pagina della documentazione di Aspose.GIS](https://reference.aspose.com/gis/net/).

**D: Come posso ottenere supporto se incontro un problema?**  
R: Pubblica la tua domanda sul forum della community di Aspose.GIS [qui](https://forum.aspose.com/c/gis/33).

**D: È possibile acquistare una licenza temporanea per la valutazione?**  
R: Sì, le licenze temporanee sono disponibili nella [pagina di acquisto](https://purchase.aspose.com/temporary-license/).

## Conclusione
Ora sai **come confrontare le geometrie** usando Aspose.GIS per .NET, dalla creazione degli oggetti al controllo dell’uguaglianza spaziale e alla gestione delle modifiche. Questa capacità è un blocco fondamentale per analisi spaziali più avanzate, come la validazione topologica, il rilevamento di duplicati e il filtraggio basato su geometrie.

---

**Ultimo aggiornamento:** 2025-12-03  
**Testato con:** Aspose.GIS per .NET 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}