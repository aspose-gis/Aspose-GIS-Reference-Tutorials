---
title: Crea file GDB con livello singolo
linktitle: Crea file GDB con livello singolo
second_title: API Aspose.GIS .NET
description: Sblocca il potenziale della gestione dei dati geospaziali in .NET con Aspose.GIS. Scopri come creare geodatabase di file e layer passo dopo passo. Scarica ora!
weight: 11
url: /it/net/layer-management/create-file-gdb-with-single-layer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea file GDB con livello singolo

## introduzione
Sei pronto a migliorare le tue applicazioni geospaziali con geodatabase e layer di file robusti? Non cercare oltre Aspose.GIS per .NET. In questo tutorial ti guideremo attraverso il processo di creazione di un file geodatabase (GDB) con un singolo livello utilizzando Aspose.GIS per .NET. Sfrutta facilmente la potenza della gestione e della visualizzazione dei dati spaziali nelle tue applicazioni .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
1.  Aspose.GIS per .NET: assicurati di avere la libreria Aspose.GIS installata. Puoi scaricarlo da[Pagina di download di Aspose.GIS per .NET](https://releases.aspose.com/gis/net/).
2. Ambiente di sviluppo: configura un ambiente di sviluppo .NET funzionante sul tuo computer.
3. Directory dei documenti: scegli o crea una directory sul tuo sistema in cui memorizzerai i file di dati geospaziali.
## Importa spazi dei nomi
Per iniziare, devi importare gli spazi dei nomi necessari nel tuo progetto .NET. Questi spazi dei nomi forniranno l'accesso alle funzionalità Aspose.GIS. Aggiungi le seguenti righe all'inizio del file di codice:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```
## Passaggio 1: imposta la directory dei documenti
```csharp
string dataDir = "Your Document Directory";
```
Sostituisci "La tua directory dei documenti" con il percorso della directory in cui desideri archiviare i file di dati geospaziali.
## Passaggio 2: creare un geodatabase di file con un singolo livello
```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Questo frammento di codice crea un file geodatabase con un singolo layer e vi aggiunge una caratteristica di linea.
## Passaggio 3: aprire il file geodatabase e recuperare le informazioni sul livello
```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Risultato: conteggio delle funzionalità: 1
}
```
In questo passaggio, apriamo il file geodatabase creato, recuperiamo il layer denominato "layer" e stampiamo il conteggio delle caratteristiche nel layer.
## Conclusione
Congratulazioni! Hai creato con successo un file geodatabase con un singolo livello utilizzando Aspose.GIS per .NET. Esplora con facilità le vaste funzionalità della gestione dei dati spaziali nelle tue applicazioni.
## Domande frequenti
### Posso utilizzare Aspose.GIS per .NET nei miei progetti .NET esistenti?
Sì, Aspose.GIS per .NET può essere perfettamente integrato nei tuoi progetti .NET esistenti.
### È disponibile una versione di prova per Aspose.GIS per .NET?
 Sì, puoi esplorare le funzionalità di Aspose.GIS per .NET scaricando il file[versione di prova gratuita](https://releases.aspose.com/).
### Dove posso trovare la documentazione dettagliata per Aspose.GIS per .NET?
 Fare riferimento al[documentazione](https://reference.aspose.com/gis/net/) per informazioni complete su Aspose.GIS per .NET.
### Come posso ottenere supporto per Aspose.GIS per .NET?
 Visitare il[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per il sostegno e l'assistenza della comunità.
### Sono disponibili licenze temporanee per Aspose.GIS per .NET?
 Sì, puoi ottenere un[licenza temporanea](https://purchase.aspose.com/temporary-license/) per Aspose.GIS per .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
