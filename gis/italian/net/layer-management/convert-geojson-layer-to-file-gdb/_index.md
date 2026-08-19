---
date: 2026-06-20
description: Scopri come convertire geojson in gdb con Aspose.GIS per .NET. Questa
  guida passo‑passo copre la lettura di GeoJSON in C#, la creazione di un File Geodatabase
  e la gestione dei problemi più comuni.
keywords:
- convert geojson to gdb
- how to convert geojson
- read geojson c#
- asp.net geojson conversion
linktitle: Converti layer GeoJSON in GDB
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to convert geojson to gdb with Aspose.GIS for .NET. This
    step‑by‑step guide covers reading GeoJSON in C#, creating a File Geodatabase,
    and handling common issues.
  headline: How to Convert GeoJSON to GDB Using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.
    question: What does this guide teach?
  - answer: '*convert geojson to gdb*.'
    question: Which primary keyword is targeted?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Supported .NET versions?
  - answer: Roughly 10‑15 minutes for a basic conversion.
    question: Implementation time?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Come convertire GeoJSON in GDB usando Aspose.GIS per .NET
url: /it/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come convertire GeoJSON in GDB usando Aspose.GIS per .NET

## Introduzione
Se stai cercando di **convert geojson to gdb** rapidamente e in modo affidabile, sei nel posto giusto. Questo tutorial ti guida passo passo—dalla lettura di un file GeoJSON in C# alla creazione di un File Geodatabase (GDB) con Aspose.GIS. Vedrai perché Aspose.GIS è una libreria preferita per la conversione di dati geospaziali, come configurare l'ambiente e come eseguire la conversione in pochi minuti.

## Risposte rapide
- **Che cosa insegna questa guida?** Conversione di un layer GeoJSON in un GDB con Aspose.GIS per .NET.  
- **Qual è la parola chiave principale?** *convert geojson to gdb*.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per i test; è necessaria una licenza commerciale per la produzione.  
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tempo di implementazione?** Circa 10‑15 minuti per una conversione di base.

## Cos'è GeoJSON e File GDB?
GeoJSON è un formato leggero, basato su testo, per le caratteristiche geografiche, mentre File GDB è un geodatabase ESRI ad alte prestazioni basato su cartelle.  
GeoJSON memorizza punti, linee e poligoni come testo semplice, facilitandone la condivisione e la modifica, mentre File GDB conserva i dati in file binari che offrono query spaziali rapide e una gestione robusta degli attributi. Insieme coprono sia lo scambio web‑friendly sia l'elaborazione GIS desktop ad alta velocità.

## Perché usare Aspose.GIS per la conversione di dati geospaziali?
Aspose.GIS fornisce un'API unica e coerente che nasconde le particolarità specifiche dei formati. Supporta **30+ geospatial formats**, può elaborare file fino a **2 GB** senza caricare l'intero dataset in memoria e preserva automaticamente i sistemi di riferimento delle coordinate. Questo significa che spendi meno tempo a scrivere parser e più tempo a costruire la logica della tua applicazione.

## Prerequisiti
- Familiarità con C# e la struttura dei progetti .NET.  
- Aspose.GIS per .NET installato. Se non l'hai ancora installato, scaricalo da [here](https://releases.aspose.com/gis/net/) e segui la guida all'installazione. Puoi anche esplorare altri prodotti Aspose su [here](https://releases.aspose.com/).

## Importare i namespace
Il primo passo è importare i namespace richiesti nello scope.

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

## Come leggere GeoJSON in C#?
Carica il file GeoJSON con la classe `GeoJsonReader`, che analizza il JSON e crea una `FeatureCollection` in memoria. Il lettore rileva automaticamente il sistema di riferimento delle coordinate, quindi non è necessario gestire manualmente il parsing del CRS. Supporta inoltre lo streaming di file di grandi dimensioni, preserva i tipi di attributo e può essere combinato con trasformazioni geometriche personalizzate, se necessario.

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
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

## Passo 1: Configurare il layer GeoJSON
Crea un file GeoJSON temporaneo che contenga gli attributi e le feature che desideri convertire. Questo esempio aggiunge due semplici feature puntuali.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Passo 2: Copiare il dataset di test
Per mantenere intatti i dati di test originali, duplica il dataset File GDB esistente. Questo garantisce un ambiente pulito per la conversione.

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## Passo 3: Convertire GeoJSON in GDB
`FileGdb` rappresenta un contenitore File Geodatabase e fornisce metodi per gestire i layer. Apri il layer GeoJSON, crea un nuovo layer all'interno del File GDB copiato, copia gli attributi e trasferisci ogni feature. Questo è il cuore del processo di **Aspose.GIS conversion**.

CODE_BLOCK_PLACEHOLDER_4_END

## Come convertire GeoJSON in GDB?
Carica il GeoJSON con `GeoJsonReader`, istanzia un oggetto `FileGdb` che punta alla cartella di destinazione, crea un nuovo layer di feature e poi itera su ogni feature per inserirla. In pratica è un flusso a tre passaggi—lettura, creazione, copia—che si completa in meno di un minuto per dataset tipici.

## Problemi comuni e soluzioni
- **Missing spatial reference:** Assicurati che il GeoJSON di origine includa una definizione CRS o imposta esplicitamente `SpatialReferenceSystem.Wgs84` quando crei il layer GDB.  
- **Attribute type mismatch:** I tipi di dati degli attributi in GeoJSON devono corrispondere allo schema di destinazione; altrimenti Aspose.GIS genererà un'eccezione.  
- **File access errors:** Verifica che la cartella di destinazione abbia i permessi di scrittura e che nessun altro processo stia bloccando i file GDB.

## Domande frequenti
### Aspose.GIS è compatibile con l'ultima versione del framework .NET?
Sì, Aspose.GIS funziona con .NET Framework 4.5+, .NET Core 3.1+, .NET 5 e .NET 6+.

### Posso convertire altri formati geospaziali usando Aspose.GIS?
Assolutamente! Aspose.GIS supporta più di 30 formati di input e output, inclusi Shapefile, KML, GML e SQLite.

### È disponibile una versione di prova per Aspose.GIS?
Sì, puoi esplorare le funzionalità di Aspose.GIS scaricando la versione di prova [here](https://releases.aspose.com/).

### Come posso ottenere supporto per le domande relative ad Aspose.GIS?
Visita il forum Aspose.GIS [forum](https://forum.aspose.com/c/gis/33) per assistenza dedicata dalla community e dal team di prodotto.

### Posso ottenere una licenza temporanea per Aspose.GIS?
Sì, puoi ottenere una licenza temporanea [here](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2026-06-20  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Creare dataset File Geodatabase .NET con Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Leggere le feature da File Geodatabase in Aspose.GIS](/gis/net/layer-data-operations/read-features-from-file-geodatabase/)
- [Creare layer vettoriale in File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}