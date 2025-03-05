---
title: Padronanza GIS aggiungi livelli a GDB con Aspose.GIS per .NET
linktitle: Aggiungi livello al set di dati GDB del file
second_title: API Aspose.GIS .NET
description: Sblocca la potenza del GIS con Aspose.GIS per .NET! Scopri come aggiungere layer ai set di dati File GDB in questo tutorial passo passo. #datigeografici #Aspose #GIS
type: docs
weight: 16
url: /it/net/layer-management/add-layer-to-file-gdb-dataset/
---
## introduzione
Sei pronto a migliorare le tue capacità GIS utilizzando Aspose.GIS per .NET? In questa guida passo passo ti guideremo attraverso il processo di aggiunta di un layer a un set di dati File Geodatabase (GDB). Aspose.GIS per .NET fornisce potenti funzionalità per manipolare le informazioni geografiche e con questo tutorial sarai in grado di integrare perfettamente livelli aggiuntivi nei tuoi set di dati.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
-  Aspose.GIS per .NET Library: scarica e installa la libreria da[Aspose.GIS per la documentazione .NET](https://reference.aspose.com/gis/net/).
- Directory dei documenti: crea una directory dei documenti dedicata sul tuo computer per archiviare e gestire i file relativi al GIS.
## Importa spazi dei nomi
Nel tuo progetto .NET, assicurati di importare gli spazi dei nomi necessari per accedere alle funzionalità Aspose.GIS. Utilizza il seguente snippet di codice:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Passaggio 1: copiare la directory
Prima di procedere, duplica la directory contenente il tuo set di dati GDB. Questo passaggio garantisce che il set di dati originale rimanga intatto. Utilizza lo snippet di codice fornito:
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## Passaggio 2: aprire il set di dati e verificare la capacità di creazione
 Apri il set di dati duplicato e controlla se può creare livelli. Ciò è confermato dalla presenza di`True` nell'output della console.
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // VERO
```
## Passaggio 3: crea e popola un nuovo livello
Crea un nuovo layer all'interno del set di dati, definendone il sistema di riferimento spaziale, gli attributi e una caratteristica campione. Questo frammento di codice dimostra il processo:
```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```
## Passaggio 4: aprire e convalidare il livello aggiunto
Apri il livello che hai appena creato e convalida il suo contenuto. Controlla il conteggio e recupera i valori degli attributi utilizzando il seguente codice:
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Nome_1"
}
```
## Conclusione
Congratulazioni! Hai imparato con successo come aggiungere un livello a un set di dati File GDB utilizzando Aspose.GIS per .NET. Con queste nuove competenze, puoi manipolare in modo efficiente i dati geografici nei tuoi progetti GIS.
## Domande frequenti
### D: Posso utilizzare Aspose.GIS per .NET con altre librerie GIS?
Aspose.GIS per .NET è progettato per funzionare in modo indipendente, ma può essere integrato con altre librerie per funzionalità avanzate.
### D: È disponibile una licenza temporanea a scopo di test?
 Sì, puoi ottenere una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/) per test e valutazioni.
### D: Quali sistemi di riferimento spaziale supporta Aspose.GIS per .NET?
Aspose.GIS per .NET supporta un'ampia gamma di sistemi di riferimento spaziale, fornendo flessibilità nella gestione dei dati geografici.
### D: Posso contribuire alla comunità Aspose.GIS?
 Assolutamente! Partecipa alle discussioni e condividi le tue esperienze su[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### D: Dove posso trovare la documentazione dettagliata per Aspose.GIS per .NET?
 Esplora la documentazione completa[Qui](https://reference.aspose.com/gis/net/) per informazioni approfondite su Aspose.GIS per .NET.