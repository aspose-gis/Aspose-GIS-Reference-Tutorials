---
date: 2026-02-10
description: Scopri come calcolare la lunghezza della geometria in .NET usando Aspose.GIS
  per una gestione efficiente dei dati spaziali. Include esempi per ottenere la lunghezza
  di una linea in C# e per calcolare la lunghezza di una linea in C#.
linktitle: Get Geometry Length
second_title: Aspose.GIS .NET API
title: Come calcolare la lunghezza della geometria in .NET con Aspose.GIS
url: /it/net/geometry-analysis/get-geometry-length/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come calcolare la lunghezza della geometria .NET con Aspose.GIS

## Introduzione
Se stai cercando un modo chiaro e pratico per **calcolare la lunghezza della geometria .NET**, sei nel posto giusto. Aspose.GIS per .NET ti offre un ricco insieme di API focalizzate sul GIS che rendono i calcoli spaziali — come la misurazione della lunghezza di una linea o del perimetro di un poligono — semplici e performanti. In questo tutorial percorreremo l’intero processo, dalla configurazione dell’ambiente alla scrittura del codice C# che restituisce valori di lunghezza accurati.

## Risposte rapide
- **Cosa restituisce “GetLength()”?** Per le linee restituisce la lunghezza della linea; per i poligoni restituisce il perimetro.  
- **Quale namespace è richiesto?** `Aspose.Gis.Geometries`.  
- **Posso usarlo con .NET 6?** Sì, Aspose.GIS supporta .NET 5, .NET 6 e versioni successive.  
- **Ho bisogno di una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per la valutazione; è necessaria una licenza per la produzione.  
- **Il calcolo è consapevole dell'unità?** La lunghezza è restituita nelle unità del sistema di coordinate (ad esempio metri per CRS proiettati).

## Che cos'è la lunghezza della geometria?
`Geometry.GetLength()` è un metodo che restituisce la misura lineare di un oggetto geometrico. Per un `LineString` fornisce la lunghezza totale della linea, mentre per un `Polygon` restituisce il perimetro (la somma di tutti i suoi bordi). Questo metodo astrae la matematica sottostante, permettendoti di concentrarti sulla logica GIS di livello superiore.

## Perché usare Aspose.GIS per i calcoli di lunghezza?
- **Nessuna dipendenza esterna** – libreria .NET pura, senza DLL native.  
- **Alta precisione** – utilizza aritmetica a doppia precisione per risultati accurati.  
- **Cross‑platform** – funziona su Windows, Linux e macOS con .NET Core/5/6+.  

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

### 1. Libreria Aspose.GIS per .NET
In primo luogo, è necessario avere la libreria Aspose.GIS per .NET installata nel proprio ambiente di sviluppo. Se non l'hai ancora fatto, puoi scaricarla dalla pagina [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/) .

### 2. Ambiente di sviluppo .NET
Assicurati di avere un ambiente di sviluppo .NET configurato sulla tua macchina. Questo include avere Visual Studio o qualsiasi altro IDE compatibile installato.

### 3. Conoscenza di base di C#
Una conoscenza di base del linguaggio di programmazione C# è essenziale per seguire questo tutorial.

## Importare i namespace
Per utilizzare le funzionalità offerte da Aspose.GIS per .NET, è necessario importare i namespace necessari nel tuo progetto C#.

### Importare il namespace Aspose.GIS
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Come ottenere la lunghezza della linea C#
### Passo 1: Creare oggetti Geometry
Per cominciare, crea gli oggetti geometria che rappresentano le forme per le quali desideri calcolare la lunghezza. Questo può includere linee, poligoni o qualsiasi altra forma geometrica.

```csharp
var line = new LineString();
line.AddPoint(0, 0);
line.AddPoint(2, 2);
line.AddPoint(2, 0);
```

### Passo 2: Calcolare la lunghezza della linea in C#
Una volta creata la geometria della linea, puoi calcolare la sua lunghezza usando il metodo `GetLength()`. Questo dimostra **calcolare la lunghezza della linea c#** in una singola riga di codice.

```csharp
Console.WriteLine("{0:F}", line.GetLength()); // Output: 4.83
```

## Come calcolare la lunghezza della linea C# per i poligoni
### Passo 3: Creare la geometria del poligono
Allo stesso modo, puoi creare oggetti geometria poligonale usando le classi `Polygon` e `LinearRing`.

```csharp
var rectangle = new Polygon(new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(1, 0),
    new Point(0, 0),
}));
```

### Passo 4: Ottenere la lunghezza di un poligono
Per i poligoni, il metodo `GetLength()` restituisce il perimetro, che è effettivamente il **come ottenere la lunghezza** della forma.

```csharp
Console.WriteLine("{0:F}", rectangle.GetLength()); // Output: 4.00
```

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Lunghezza zero inaspettata** | Verifica che il sistema di coordinate della geometria corrisponda ai dati forniti; punti duplicati possono causare segmenti di lunghezza zero. |
| **Unità errate** | Ricorda che `GetLength()` restituisce valori nelle unità del CRS. Converti in metri/piedi se necessario. |
| **Prestazioni con grandi dataset** | Riutilizza gli oggetti geometria quando possibile ed evita di creare migliaia di punti temporanei all'interno di loop stretti. |

## Domande frequenti

**D: Aspose.GIS per .NET è compatibile con tutti i framework .NET?**  
R: Aspose.GIS per .NET è compatibile con .NET Framework 4.6.1 o versioni successive, così come con .NET 5/6/7.

**D: Posso provare Aspose.GIS per .NET prima di acquistarlo?**  
R: Sì, puoi usufruire di una versione di prova gratuita di Aspose.GIS per .NET da [qui](https://releases.aspose.com/).

**D: Dove posso trovare supporto per Aspose.GIS per .NET?**  
R: Puoi trovare supporto e assistenza dal forum della community Aspose.GIS [qui](https://forum.aspose.com/c/gis/33).

**D: Come posso ottenere una licenza temporanea per Aspose.GIS per .NET?**  
R: Puoi acquisire una licenza temporanea da [qui](https://purchase.aspose.com/temporary-license/).

**D: Posso personalizzare il formato di output per i calcoli della lunghezza della geometria?**  
R: Sì, Aspose.GIS per .NET offre varie opzioni di formattazione per personalizzare il formato di output secondo le tue esigenze.

## Conclusione
In questo tutorial abbiamo coperto **come calcolare la lunghezza della geometria .NET** per geometrie sia di linea che di poligono usando Aspose.GIS per .NET. Seguendo gli esempi passo‑passo, ora puoi integrare misurazioni spaziali precise in qualsiasi applicazione .NET, sia essa uno strumento GIS desktop, un servizio web o una pipeline di elaborazione dati backend.

---

**Ultimo aggiornamento:** 2026-02-10  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}