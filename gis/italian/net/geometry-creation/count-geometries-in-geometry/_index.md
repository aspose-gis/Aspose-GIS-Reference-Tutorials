---
title: Contare le geometrie in geometria con Aspose.GIS
linktitle: Contare le geometrie in Geometria
second_title: API Aspose.GIS .NET
description: Scopri come contare le geometrie in una geometria utilizzando Aspose.GIS per .NET. Tutorial passo passo con esempi di codice per gli sviluppatori.
weight: 23
url: /it/net/geometry-creation/count-geometries-in-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Contare le geometrie in geometria con Aspose.GIS

## introduzione
Aspose.GIS per .NET è un potente strumento per gli sviluppatori che cercano di incorporare funzionalità geospaziali nelle loro applicazioni .NET. Che tu stia creando software di mappatura, servizi basati sulla posizione o strumenti di analisi spaziale, Aspose.GIS fornisce un set completo di funzionalità per soddisfare le tue esigenze. In questo tutorial esploreremo come contare le geometrie all'interno di una geometria utilizzando Aspose.GIS per .NET.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di possedere i seguenti prerequisiti:
1. Visual Studio: assicurati di avere Visual Studio installato sul tuo sistema.
2. Aspose.GIS per .NET: scaricare e installare Aspose.GIS per .NET da[pagina di download](https://releases.aspose.com/gis/net/).
3. Conoscenza di base di C#: familiarizza con le nozioni di base del linguaggio di programmazione C#.

## Importa spazi dei nomi
Prima di iniziare a scrivere codice, è necessario importare gli spazi dei nomi necessari per accedere alla funzionalità Aspose.GIS.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Passaggio 2: crea la geometria del punto
```csharp
Point point = new Point(40.7128, -74.006);
```
 Qui creiamo un file`Point` geometria con latitudine 40.7128 e longitudine -74.006.
## Passaggio 3: crea la geometria LineString
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 Questo passaggio crea un file`LineString` geometria e vi aggiunge due punti.
## Passaggio 4: crea una raccolta di geometrie
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 Creiamo quindi un`GeometryCollection` e aggiungivi le geometrie di punti e linee create in precedenza.
## Passaggio 5: contare le geometrie
```csharp
int geometriesCount = geometryCollection.Count;
```
 Questo passaggio conta il numero di geometrie all'interno del file`GeometryCollection`.
## Passaggio 6: visualizzare il conteggio
```csharp
Console.WriteLine(geometriesCount); // 2
```
 Infine, stampiamo il conteggio delle geometrie, che in questo caso lo è`2`.

## Conclusione
In questo tutorial, abbiamo imparato come contare le geometrie all'interno di una geometria utilizzando Aspose.GIS per .NET. Seguendo questi passaggi è possibile incorporare facilmente funzionalità geospaziali nelle applicazioni .NET.
## Domande frequenti
### Aspose.GIS per .NET è adatto sia per applicazioni desktop che web?
Sì, Aspose.GIS per .NET può essere utilizzato senza problemi sia in applicazioni desktop che web.
### Posso eseguire query spaziali utilizzando Aspose.GIS per .NET?
Assolutamente, Aspose.GIS per .NET fornisce un solido supporto per l'esecuzione di query spaziali sulle geometrie.
### Aspose.GIS per .NET supporta vari formati di file GIS?
Sì, Aspose.GIS per .NET supporta un'ampia gamma di formati di file GIS tra cui SHP, KML e GeoJSON.
### È disponibile una prova gratuita per Aspose.GIS per .NET?
 Sì, puoi scaricare una versione di prova gratuita da[sito web](https://releases.aspose.com/).
### Dove posso trovare supporto per Aspose.GIS per .NET?
 Puoi trovare supporto su[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
