---
title: Controlla l'uguaglianza delle geometrie
linktitle: Controlla l'uguaglianza delle geometrie
second_title: API Aspose.GIS .NET
description: Scopri come utilizzare Aspose.GIS per .NET per verificare l'uguaglianza delle geometrie nelle tue applicazioni .NET con questo tutorial completo.
type: docs
weight: 10
url: /it/net/geometry-analysis/check-geometries-for-equality/
---
## introduzione
Aspose.GIS per .NET è una potente libreria che consente agli sviluppatori di lavorare in modo efficiente con i dati geospaziali nelle loro applicazioni .NET. Che tu stia creando applicazioni di mappatura, strumenti di analisi spaziale o integrando funzionalità geospaziali nel software esistente, Aspose.GIS fornisce gli strumenti necessari per portare a termine il lavoro.
## Prerequisiti
Prima di immergerti nell'utilizzo di Aspose.GIS per .NET, assicurati di disporre dei seguenti prerequisiti:
### .NET Framework installato
Assicurati di avere .NET Framework installato sul tuo sistema. Puoi scaricarlo dal sito Web di Microsoft.
### Aspose.GIS per la libreria .NET
 Scarica e installa la libreria Aspose.GIS per .NET da[pagina di download](https://releases.aspose.com/gis/net/). Seguire le istruzioni di installazione fornite nella documentazione.
### Sviluppo dell'ambiente
Configura il tuo ambiente di sviluppo preferito, come Visual Studio, per lo sviluppo .NET.

## Importa spazi dei nomi
Nella tua applicazione .NET, importa gli spazi dei nomi necessari per utilizzare la funzionalità Aspose.GIS:
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Passaggio 1: definire le geometrie
Innanzitutto, definisci le geometrie che desideri confrontare. In questo esempio, abbiamo due geometrie:`geometry1` E`geometry2`.
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
## Passaggio 2: verificare l'uguaglianza delle geometrie
 Ora, controlla se le geometrie sono spazialmente uguali usando il`SpatiallyEquals` metodo fornito da Aspose.GIS.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // VERO
```
 Questo verrà stampato`True` alla console da allora`geometry1` E`geometry2` sono spazialmente uguali.
## Passaggio 3: modifica la geometria
 Successivamente, modifichiamo`geometry2` aggiungendo un nuovo punto.
```csharp
geometry2.AddPoint(3, 3);
```
## Passaggio 4: ricontrolla l'uguaglianza
Ora, ricontrolla l'uguaglianza delle geometrie dopo la modifica.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Falso
```
 Questa volta, l'output sarà`False` poiché le geometrie non sono più spazialmente uguali a causa della modifica apportata`geometry2`.

## Conclusione
In conclusione, Aspose.GIS per .NET fornisce potenti strumenti per lavorare con dati geospaziali nelle applicazioni .NET. Seguendo questa guida passo passo, puoi facilmente verificare l'uguaglianza delle geometrie utilizzando i metodi Aspose.GIS.
## Domande frequenti
### Posso utilizzare Aspose.GIS per .NET con altri framework .NET?
Sì, Aspose.GIS per .NET è compatibile con vari framework .NET, inclusi .NET Core e .NET Standard.
### È disponibile una prova gratuita per Aspose.GIS per .NET?
 Sì, puoi scaricare una versione di prova gratuita da[pagina delle uscite](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.GIS per .NET?
 È possibile trovare documentazione dettagliata su[Pagina della documentazione Aspose.GIS](https://reference.aspose.com/gis/net/).
### Come posso ottenere supporto per Aspose.GIS per .NET?
 È possibile ottenere supporto dal forum della comunità Aspose.GIS[Qui](https://forum.aspose.com/c/gis/33).
### Posso acquistare una licenza temporanea per Aspose.GIS per .NET?
 Sì, puoi acquistare una licenza temporanea da[pagina di acquisto](https://purchase.aspose.com/temporary-license/).