---
title: Conversione da GeoJSON a file GDB demistificata
linktitle: Converti layer GeoJSON in file GDB
second_title: API Aspose.GIS .NET
description: Sblocca meraviglie geospaziali con Aspose.GIS per .NET! Converti facilmente layer GeoJSON in geodatabase di file. Provalo ora! #Aspose #GIS
weight: 17
url: /it/net/layer-management/convert-geojson-layer-to-file-gdb/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Conversione da GeoJSON a file GDB demistificata

## introduzione
Nel regno dinamico dei Sistemi Informativi Geografici (GIS), la capacità di convertire senza problemi i dati tra diversi formati è fondamentale. Aspose.GIS per .NET emerge come un potente alleato, offrendo una suite completa di strumenti per gestire i dati geospaziali senza sforzo. In questo tutorial, approfondiremo il processo di conversione di un layer GeoJSON in un file geodatabase (file GDB) utilizzando Aspose.GIS per .NET.
## Prerequisiti
Prima di intraprendere questo viaggio geospaziale, assicurati di disporre dei seguenti prerequisiti:
- Una conoscenza pratica della programmazione .NET.
-  Aspose.GIS per .NET installato. In caso contrario, scaricalo da[Qui](https://releases.aspose.com/gis/net/) e seguire le istruzioni di installazione.
## Importa spazi dei nomi
Per avviare il processo di conversione, inizia importando gli spazi dei nomi necessari:
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
Ora suddividiamo il processo in una guida passo passo:
## Passaggio 1: imposta il livello GeoJSON
Inizia creando un livello GeoJSON con attributi e funzionalità pertinenti. Ecco uno snippet per guidarti:
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Aggiungi attributi
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Costruisci e aggiungi funzionalità
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## Passaggio 2: copiare il set di dati di test
Per preservare l'integrità dei dati del test, crea una copia del set di dati. Utilizza il seguente snippet di codice:
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## Passaggio 3: converti GeoJSON in file GDB
Ora è il momento di eseguire la conversione. Utilizza il seguente codice:
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copia attributi
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Aggiungi funzionalità
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## Conclusione
In questo tutorial, abbiamo esplorato l'intrigante terreno della conversione di un livello GeoJSON in un file geodatabase utilizzando Aspose.GIS per .NET. Grazie a queste conoscenze, ora sei in grado di manipolare senza problemi i dati geospaziali nelle tue applicazioni .NET.
## Domande frequenti
### Aspose.GIS è compatibile con l'ultimo framework .NET?
Sì, Aspose.GIS è compatibile con le ultime versioni di .NET framework.
### Posso convertire altri formati geospaziali utilizzando Aspose.GIS?
Assolutamente! Aspose.GIS supporta un'ampia gamma di formati geospaziali per una manipolazione versatile dei dati.
### È disponibile una versione di prova per Aspose.GIS?
 Sì, puoi esplorare le funzionalità di Aspose.GIS scaricando la versione di prova[Qui](https://releases.aspose.com/).
### Come posso ottenere supporto per le query relative ad Aspose.GIS?
 Vai su Aspose.GIS[Forum](https://forum.aspose.com/c/gis/33) per un supporto dedicato.
### Posso ottenere una licenza temporanea per Aspose.GIS?
 Sì, puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
