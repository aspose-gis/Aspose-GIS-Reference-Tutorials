---
title: Crea un poligono con la geometria del foro utilizzando Aspose.GIS
linktitle: Crea un poligono con la geometria del foro
second_title: API Aspose.GIS .NET
description: Scopri come creare un poligono con la geometria del foro utilizzando Aspose.GIS per .NET. Tutorial passo passo con esempi di codice.
type: docs
weight: 13
url: /it/net/geometry-creation/create-polygon-with-hole-geometry/
---
## introduzione
In questo tutorial, esamineremo il processo di creazione di un poligono con una geometria del foro utilizzando Aspose.GIS per .NET. Aspose.GIS è una potente libreria che consente agli sviluppatori di lavorare con dati geospaziali nelle loro applicazioni .NET. 
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Aspose.GIS per .NET Library: puoi scaricarlo da[Qui](https://releases.aspose.com/gis/net/).
2. Ambiente di sviluppo: assicurati di avere un ambiente di sviluppo configurato con Visual Studio o qualsiasi altro IDE .NET installato.
## Importa spazi dei nomi
Innanzitutto, è necessario importare gli spazi dei nomi necessari per lavorare con le funzionalità Aspose.GIS. Ecco come farlo:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ora procediamo a creare un poligono con una geometria del foro utilizzando Aspose.GIS per .NET.
## Passaggio 1: crea un oggetto poligono
```csharp
Polygon polygon = new Polygon();
```
## Passaggio 2: Definire l'anello esterno
```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```
## Passaggio 3: Definire l'anello interno (foro)
```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```
## Passaggio 4: assegna l'anello esterno e aggiungi l'anello interno al poligono
```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```
## Conclusione
Congratulazioni! Hai imparato con successo come creare un poligono con una geometria del foro utilizzando Aspose.GIS per .NET. Questa conoscenza sarà utile per varie applicazioni geospaziali in cui tali geometrie sono essenziali.
## Domande frequenti
### 1. Cos'è Aspose.GIS?
Aspose.GIS è una libreria .NET che consente agli sviluppatori di lavorare con dati geospaziali, consentendo loro di creare, leggere e manipolare vari formati di file geospaziali.
### 2. Posso utilizzare Aspose.GIS per progetti commerciali?
 Sì, puoi utilizzare Aspose.GIS sia per progetti personali che commerciali acquistando una licenza. Visita[Qui](https://purchase.aspose.com/buy) per ulteriori dettagli.
### 3. È disponibile una prova gratuita per Aspose.GIS?
 Sì, puoi usufruire di una prova gratuita di Aspose.GIS da[Qui](https://releases.aspose.com/).
### 4. Dove posso trovare supporto per Aspose.GIS?
 Puoi trovare supporto per Aspose.GIS su[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### 5. Come posso ottenere una licenza temporanea per Aspose.GIS?
 È possibile ottenere una licenza temporanea per Aspose.GIS da[Qui](https://purchase.aspose.com/temporary-license/).