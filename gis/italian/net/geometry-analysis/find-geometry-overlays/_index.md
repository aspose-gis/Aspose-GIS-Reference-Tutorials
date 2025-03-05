---
title: Padroneggiare le sovrapposizioni di geometria con Aspose.GIS per .NET
linktitle: Trova sovrapposizioni di geometria
second_title: API Aspose.GIS .NET
description: Scopri come eseguire operazioni di sovrapposizione geometrica utilizzando Aspose.GIS per .NET. Padroneggiare le operazioni di intersezione, unione, differenza e differenza simmetrica.
type: docs
weight: 16
url: /it/net/geometry-analysis/find-geometry-overlays/
---
## introduzione
Nel campo dei Sistemi Informativi Geografici (GIS), le operazioni di sovrapposizione sono fondamentali per l'analisi spaziale. Consentono il confronto e la combinazione di diversi set di dati spaziali per ricavare informazioni preziose. Aspose.GIS per .NET fornisce funzionalità robuste per eseguire sovrapposizioni geometriche in modo efficiente. In questo tutorial, approfondiremo varie operazioni di sovrapposizione come Intersezione, Unione, Differenza e Differenza simmetrica utilizzando Aspose.GIS per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
### 1. Ambiente di sviluppo .NET
Assicurati di avere un ambiente di sviluppo .NET configurato sul tuo computer. È possibile scaricare e installare .NET SDK dal sito Web .NET.
### 2. Aspose.GIS per la libreria .NET
 Scarica e installa la libreria Aspose.GIS per .NET da[sito web](https://releases.aspose.com/gis/net/).
## Importa spazi dei nomi
Prima di poter iniziare a utilizzare Aspose.GIS per .NET, è necessario importare gli spazi dei nomi necessari nel progetto.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Passaggio 1: crea oggetti poligonali
Per prima cosa definiremo due oggetti poligonali che rappresentano regioni spaziali.
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
## Passaggio 2: eseguire l'operazione di intersezione
Successivamente, troviamo l'intersezione dei due poligoni.
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Poligono
```
## Passaggio 3: stampa dei punti di intersezione
Stamperemo i punti del poligono di intersezione.
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## Passaggio 4: eseguire l'operazione sindacale
Ora troviamo l'unione dei due poligoni.
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Poligono
```
## Passaggio 5: stampa dei punti di unione
Stampa i punti del poligono di unione.
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## Passaggio 6: eseguire l'operazione di differenza
Successivamente, troviamo la differenza tra i due poligoni.
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Poligono
```
## Passaggio 7: stampare i punti di differenza
Stampa i punti del poligono differenza.
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## Passaggio 8: eseguire l'operazione di differenza simmetrica
Infine, troviamo la differenza simmetrica tra i due poligoni.
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // Multipoligono
```
## Passaggio 9: stampa poligoni di differenza simmetrica
Stampa i punti di ciascun poligono nella differenza simmetrica.
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## Conclusione
Padroneggiare le sovrapposizioni geometriche è fondamentale nell'analisi spaziale e Aspose.GIS per .NET fornisce un set completo di strumenti per eseguire queste operazioni in modo efficiente. Seguendo questo tutorial, hai imparato come utilizzare Aspose.GIS per .NET per eseguire operazioni di intersezione, unione, differenza e differenza simmetrica su forme geometriche.
## Domande frequenti
### D: Posso utilizzare Aspose.GIS per .NET nei miei progetti commerciali?
Sì, Aspose.GIS per .NET può essere utilizzato sia in progetti commerciali che non commerciali.
### D: È disponibile una versione di prova per Aspose.GIS per .NET?
 Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### D: Come posso ottenere supporto per Aspose.GIS per .NET?
 È possibile ottenere supporto dal forum della comunità Aspose.GIS[Qui](https://forum.aspose.com/c/gis/33).
### D: Sono disponibili licenze temporanee per Aspose.GIS per .NET?
 Sì, sono disponibili licenze temporanee a scopo di test e valutazione. Puoi ottenerli da[Qui](https://purchase.aspose.com/temporary-license/).
### D: Posso acquistare direttamente Aspose.GIS per .NET?
 Sì, puoi acquistare Aspose.GIS per .NET dal sito web[Qui](https://purchase.aspose.com/buy).