---
date: 2025-12-07
description: Impara come eseguire operazioni di overlay in questo tutorial di overlay
  spaziale usando Aspose.GIS per .NET. Padroneggia intersezione, unione, differenza
  e differenza simmetrica.
linktitle: Find Geometry Overlays
second_title: Aspose.GIS .NET API
title: Come eseguire operazioni di sovrapposizione con Aspose.GIS per .NET
url: /it/net/geometry-analysis/find-geometry-overlays/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come eseguire operazioni di overlay con Aspose.GIS per .NET

## Introduzione
L'analisi di overlay è una tecnica fondamentale in qualsiasi **tutorial di overlay spaziale**: consente di combinare, confrontare ed estrarre informazioni da più livelli geografici. In questa guida imparerai **come eseguire operazioni di overlay** come Intersezione, Unione, Differenza e Differenza Simmetrica utilizzando la potente libreria Aspose.GIS per .NET. Alla fine del tutorial sarai in grado di applicare questi metodi a problemi GIS reali, come la pianificazione dell'uso del suolo, studi di impatto ambientale e ottimizzazione di percorsi.

## Risposte rapide
- **Cos'è un'operazione di overlay?** Un metodo spaziale che combina due geometrie per produrre una nuova geometria (intersezione, unione, ecc.).  
- **Quale libreria gestisce gli overlay in .NET?** Aspose.GIS per .NET.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per l'esempio base.  
- **È necessaria una licenza?** Una versione di prova è gratuita; è richiesta una licenza commerciale per la produzione.  
- **Posso eseguirlo su .NET Core / .NET 6+?** Sì—Aspose.GIS supporta tutti i runtime .NET moderni.

## Cos'è un'operazione di overlay?
Un'operazione di overlay prende due forme geometriche e calcola una nuova forma basata sulla loro relazione spaziale.  
- **Intersezione** restituisce l'area comune a entrambe le forme.  
- **Unione** fonde le forme in un'unica geometria.  
- **Differenza** sottrae una forma dall'altra.  
- **Differenza Simmetrica** restituisce le parti che appartengono a una delle due forme ma non a entrambe.

## Perché usare Aspose.GIS per gli overlay?
Aspose.GIS offre un'API pulita, completamente gestita, che astrae la matematica di basso livello, permettendoti di concentrarti sulla logica di business. Funziona cross‑platform, gestisce grandi dataset in modo efficiente e si integra perfettamente con altri componenti .NET.

## Prerequisiti
- Un ambiente di sviluppo .NET funzionante (Visual Studio, VS Code o la CLI .NET).  
- Libreria Aspose.GIS per .NET – scarica l'ultima versione dal [sito ufficiale](https://releases.aspose.com/gis/net/).  

### Importare i namespace
Prima di poter iniziare a utilizzare Aspose.GIS per .NET, è necessario importare i namespace richiesti nel tuo progetto.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Come eseguire operazioni di overlay in .NET
Di seguito trovi una procedura passo‑per‑passo per creare due poligoni e applicare ciascun metodo di overlay.

### Passo 1: Creare oggetti Polygon
Innanzitutto definiamo due semplici poligoni quadrati che si sovrappongono parzialmente. Questi serviranno come dati di test.

```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```

### Passo 2: Eseguire l'operazione di Intersezione
L'**Intersezione** ci fornisce l'area di sovrapposizione dei due poligoni.

```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygon
```

### Passo 3: Stampare i punti di Intersezione
Utilizziamo un metodo di supporto (`PrintRing`) per visualizzare le coordinate del poligono risultante.

```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```

### Passo 4: Eseguire l'operazione di Unione
L'**Unione** fonde entrambi i poligoni in una singola forma che copre tutta l'area coperta da almeno uno dei due poligoni.

```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygon
```

### Passo 5: Stampare i punti di Unione
Stampa le coordinate della geometria unita.

```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```

### Passo 6: Eseguire l'operazione di Differenza
La **Differenza** sottrae `polygon2` da `polygon1`, lasciando solo la parte di `polygon1` che non interseca `polygon2`.

```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygon
```

### Passo 7: Stampare i punti di Differenza
Mostra i vertici rimanenti dopo la sottrazione.

```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```

### Passo 8: Eseguire l'operazione di Differenza Simmetrica
La **Differenza Simmetrica** restituisce le aree che appartengono a uno dei due poligoni ma non a entrambi. Il risultato è un `MultiPolygon`.

```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygon
```

### Passo 9: Stampare i poligoni della Differenza Simmetrica
Itera su ciascun poligono nel `MultiPolygon` e stampa i suoi punti.

```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|---------------|-----------|
| risultato `null` da `Intersection` | I poligoni non si sovrappongono realmente. | Verifica le coordinate o usa il controllo `Intersects` prima di chiamare `Intersection`. |
| `MultiPolygon` inatteso da `SymDifference` | La differenza simmetrica può produrre componenti disgiunte. | Esegui il cast a `IMultiPolygon` e itera come mostrato. |
| Rallentamento delle prestazioni su grandi dataset | Ogni operazione ricalcola la geometria da zero. | Riutilizza i risultati intermedi o semplifica le geometrie con `Simplify()` prima dell'overlay. |

## Domande frequenti

**D: Posso usare Aspose.GIS per .NET nei miei progetti commerciali?**  
R: Sì, Aspose.GIS per .NET può essere utilizzato sia in progetti commerciali che non commerciali con una licenza valida.

**D: È disponibile una versione di prova di Aspose.GIS per .NET?**  
R: Sì, puoi scaricare una versione di prova gratuita da [qui](https://releases.aspose.com/).

**D: Come posso ottenere supporto per Aspose.GIS per .NET?**  
R: Puoi ottenere supporto dal forum della community Aspose.GIS [qui](https://forum.aspose.com/c/gis/33).

**D: Sono disponibili licenze temporanee per Aspose.GIS per .NET?**  
R: Sì, le licenze temporanee sono disponibili per scopi di test e valutazione. Puoi ottenerle da [qui](https://purchase.aspose.com/temporary-license/).

**D: Posso acquistare Aspose.GIS per .NET direttamente?**  
R: Sì, puoi acquistare Aspose.GIS per .NET dal sito web [qui](https://purchase.aspose.com/buy).

---

**Ultimo aggiornamento:** 2025-12-07  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}