---
title: Specificare l'ID oggetto e i nomi dei campi geometria
linktitle: Specificare l'ID oggetto e i nomi dei campi geometria
second_title: API Aspose.GIS .NET
description: Esplora la magia GIS con Aspose.GIS per .NET! Gestisci i dati geospaziali senza sforzo. Scaricalo ora e libera il potere dell'intelligenza spaziale.
weight: 20
url: /it/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Specificare l'ID oggetto e i nomi dei campi geometria

## introduzione
Intraprendere un viaggio nel regno dei sistemi informativi geografici (GIS) utilizzando Aspose.GIS per .NET apre un mondo di possibilità sia per gli sviluppatori che per gli appassionati. Questa potente libreria ti consente di gestire i dati geospaziali senza sforzo. In questo tutorial ti guideremo attraverso il processo di specifica dei nomi dei campi ID oggetto e Geometria, gettando le basi per le tue attività GIS.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
-  Aspose.GIS per .NET: scarica e installa la libreria da[Qui](https://releases.aspose.com/gis/net/).
- Directory dei documenti: imposta una directory in cui i tuoi documenti archiviano i geodatabase.
- Ambiente .NET: assicurati di disporre di un ambiente .NET funzionante.
## Importa spazi dei nomi
Per dare il via alle cose, devi importare gli spazi dei nomi necessari nel tuo progetto. Questi spazi dei nomi forniscono le classi e i metodi essenziali per interagire con Aspose.GIS per .NET.
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## Passaggio 1: specificare l'ID oggetto e i nomi dei campi geometria
In questo passaggio imparerai come impostare i nomi dei campi ID oggetto e Geometria per i tuoi dati GIS. Questo è fondamentale per una gestione efficiente dei dati.
## Passaggio 1.1: impostare la directory dei documenti
Inizia definendo il percorso della directory dei documenti:
```csharp
string dataDir = "Your Document Directory";
```
## Passaggio 1.2: creare un geodatabase e definire le opzioni
Crea un GeoDatabase con i nomi dei campi ID oggetto e Geometria specificati:
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specificare il nome del campo ID oggetto
        GeometryFieldName = "POINT",       // Specificare il nome del campo Geometria
    };
```
## Passaggio 1.3: crea e aggiungi un livello
Crea un layer all'interno del GeoDatabase e aggiungi una feature con una geometria specifica:
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //Specificare la geometria (in questo caso, un punto)
    layer.Add(feature);
}
```
## Passaggio 1.4: aprire e recuperare i dati dal livello
Apri il layer e recupera i dati da esso in base all'ID oggetto specificato:
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Uscita: 1
}
```
## Conclusione
Congratulazioni! Hai navigato con successo attraverso il processo di specifica dei nomi dei campi ID oggetto e geometria utilizzando Aspose.GIS per .NET. Ciò costituisce una solida base per i tuoi progetti GIS, consentendoti di gestire facilmente i dati geospaziali.
## Domande frequenti
### D: Posso utilizzare Aspose.GIS per .NET nelle mie applicazioni web?
R: Sì, Aspose.GIS per .NET è adatto sia per applicazioni desktop che web, fornendo funzionalità geospaziali versatili.
### D: È disponibile una versione di prova prima dell'acquisto?
 R: Sì, puoi esplorare le funzionalità di Aspose.GIS per .NET con una prova gratuita disponibile[Qui](https://releases.aspose.com/).
### D: Come posso ottenere una licenza temporanea per Aspose.GIS per .NET?
 R: Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/) a fini di valutazione.
### D: Quali sistemi di riferimento spaziale supporta Aspose.GIS per .NET?
R: Aspose.GIS per .NET supporta vari sistemi di riferimento spaziale, fornendo flessibilità per diversi set di dati geografici.
### D: Dove posso chiedere aiuto o discutere domande relative ad Aspose.GIS?
 R: Visita il forum Aspose.GIS[Qui](https://forum.aspose.com/c/gis/33) per supporto e discussioni.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
