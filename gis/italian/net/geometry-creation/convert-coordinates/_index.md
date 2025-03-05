---
title: Coordinare la conversione con Aspose.GIS
linktitle: Converti coordinate
second_title: API Aspose.GIS .NET
description: Scopri come convertire le coordinate con Aspose.GIS per .NET. Guida passo passo, prerequisiti e domande frequenti forniti.
type: docs
weight: 25
url: /it/net/geometry-creation/convert-coordinates/
---
## introduzione
In questo tutorial approfondiremo il mondo dei sistemi informativi geografici (GIS) utilizzando la potente libreria Aspose.GIS per .NET. Aspose.GIS è un toolkit completo che consente agli sviluppatori di lavorare con i dati spaziali senza sforzo. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questo tutorial ti guiderà attraverso il processo di utilizzo di Aspose.GIS per convertire le coordinate in modo efficace.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
1. Conoscenza di base di C#: La familiarità con il linguaggio di programmazione C# è essenziale per comprendere e implementare gli esempi di codice forniti.
  
2.  Installazione di Aspose.GIS: assicurati di aver scaricato e installato la libreria Aspose.GIS per .NET. Puoi scaricarlo da[Sito web Aspose.GIS](https://releases.aspose.com/gis/net/).

## Importa spazi dei nomi
Prima di iniziare, importiamo gli spazi dei nomi necessari per accedere alle funzionalità di Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

Analizziamo l'esempio fornito in più passaggi per una chiara comprensione:
## Passaggio 1: avvia il processo di conversione
```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```
Questa riga visualizza semplicemente un messaggio che indica l'inizio del processo di conversione delle coordinate.
## Passaggio 2: conversione in gradi decimali
```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```
 Qui, convertiamo le coordinate (25,5, 45,5) nel formato gradi decimali utilizzando il formato`AsPointText` metodo con il`PointFormats.DecimalDegrees` parametro. Il risultato viene quindi stampato sulla console.
## Passaggio 3: conversione in gradi decimali minuti
```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```
Questo passaggio converte le coordinate nel formato gradi decimali minuti e stampa il risultato.
## Passaggio 4: convertire in gradi minuti secondi
```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```
Allo stesso modo, convertiamo le coordinate nel formato gradi minuti secondi e visualizziamo l'output.
## Passaggio 5: Converti in GeoRef
```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```
Infine, convertiamo le coordinate nel formato GeoRef e stampiamo il risultato.

## Conclusione
In questo tutorial, abbiamo esplorato il processo di conversione delle coordinate utilizzando Aspose.GIS per .NET. Seguendo la guida passo passo e utilizzando la libreria Aspose.GIS, puoi manipolare in modo efficiente i dati spaziali all'interno delle tue applicazioni .NET.
## Domande frequenti
### Aspose.GIS è compatibile con altri linguaggi di programmazione?
Aspose.GIS si rivolge principalmente agli sviluppatori .NET, ma offre interoperabilità con Java tramite Aspose.GIS per Java.
### Posso provare Aspose.GIS prima dell'acquisto?
 Sì, puoi accedere a una prova gratuita di Aspose.GIS da[sito web](https://releases.aspose.com/).
### Come posso ottenere supporto per Aspose.GIS?
 È possibile chiedere assistenza al forum della comunità Aspose.GIS[Qui](https://forum.aspose.com/c/gis/33).
### Sono disponibili licenze temporanee per Aspose.GIS?
 Sì, è possibile ottenere licenze temporanee da[pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).
### Dove posso acquistare Aspose.GIS?
 È possibile acquistare Aspose.GIS da[pagina di acquisto](https://purchase.aspose.com/buy).