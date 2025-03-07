---
title: Imposta il sistema di riferimento spaziale del layer
linktitle: Imposta il sistema di riferimento spaziale del layer
second_title: API Aspose.GIS .NET
description: Impostazione principale del sistema di riferimento spaziale dei livelli con Aspose.GIS per .NET. Migliora i tuoi progetti GIS con questo tutorial passo passo.
weight: 19
url: /it/net/layer-data-operations/set-layer-spatial-reference-system/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta il sistema di riferimento spaziale del layer

## introduzione
Nel vasto panorama dei Sistemi Informativi Geografici (GIS), Aspose.GIS per .NET si distingue come uno strumento robusto e versatile per gli sviluppatori. Questo tutorial ti guiderà attraverso il processo di impostazione del sistema di riferimento spaziale dei livelli utilizzando Aspose.GIS per .NET. Che tu sia uno sviluppatore esperto o un nuovo arrivato nello sviluppo GIS, questa guida passo passo ti aiuterà a sfruttare la potenza di Aspose.GIS per migliorare le tue capacità di gestione dei dati spaziali.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Una conoscenza pratica della programmazione .NET.
- Visual Studio installato nel sistema.
-  Libreria Aspose.GIS per .NET, che è possibile scaricare[Qui](https://releases.aspose.com/gis/net/).
- Una conoscenza di base dei sistemi di riferimento spaziale nei GIS.
## Importa spazi dei nomi
Nel tuo progetto .NET, inizia importando gli spazi dei nomi necessari per accedere alle funzionalità fornite da Aspose.GIS. Utilizza il seguente snippet di codice:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```
## Passaggio 1: specificare la directory dei documenti
Inizia specificando il percorso della directory dei documenti. Questa sarà la posizione in cui verranno archiviati i file di dati spaziali.
```csharp
string dataDir = "Your Document Directory";
```
## Passaggio 2: creare e impostare il sistema di riferimento spaziale
Definire il percorso per lo Shapefile e creare un nuovo sistema di riferimento spaziale utilizzando il codice EPSG (26918 in questo esempio).
```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```
## Passaggio 3: crea il livello vettoriale
Utilizzare Aspose.GIS per creare un livello vettoriale con il percorso Shapefile, il tipo di driver (Shapefile) e il sistema di riferimento spaziale specificati.
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Il tuo codice per ulteriori operazioni sul livello va qui
}
```
## Passaggio 4: aggiungi funzionalità al livello
Costruisci un nuovo elemento e impostane la geometria (in questo caso, un punto con coordinate 60, 24). Aggiungi la funzionalità al livello vettoriale.
```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```
## Passaggio 5: recuperare le informazioni sul sistema di riferimento spaziale
Apri il layer vettoriale e recupera informazioni sul sistema di riferimento spaziale.
```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```
Ripeti questi passaggi in base al tuo caso d'uso specifico e sarai sulla buona strada per padroneggiare l'arte di impostare il sistema di riferimento spaziale dei livelli con Aspose.GIS per .NET.
## Conclusione
In questo tutorial, abbiamo esplorato i passaggi essenziali per impostare il sistema di riferimento spaziale dei livelli utilizzando Aspose.GIS per .NET. Con la sua API intuitiva e potenti funzionalità, Aspose.GIS consente agli sviluppatori di gestire i dati spaziali senza problemi. Incorpora queste tecniche nei tuoi progetti GIS per migliorare le tue capacità di elaborazione dei dati spaziali.
## Domande frequenti
### Aspose.GIS è compatibile con altre librerie GIS?
Sì, Aspose.GIS si integra bene con altre librerie GIS e può essere utilizzato insieme ad esse.
### Posso utilizzare Aspose.GIS sia per applicazioni desktop che web?
Assolutamente! Aspose.GIS è versatile e può essere utilizzato sia in applicazioni desktop che basate sul web.
### Sono disponibili opzioni di licenza per Aspose.GIS?
 Sì, puoi esplorare le opzioni di licenza ed effettuare un acquisto[Qui](https://purchase.aspose.com/buy).
### È disponibile una prova gratuita per Aspose.GIS?
 Certamente! È possibile scaricare una versione di prova gratuita[Qui](https://releases.aspose.com/).
### Dove posso cercare supporto per le query relative ad Aspose.GIS?
 Per qualsiasi supporto o domanda, visitare il[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
