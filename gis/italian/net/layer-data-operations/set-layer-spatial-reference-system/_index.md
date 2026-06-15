---
date: 2026-06-15
description: Scopri come creare un layer vettoriale e impostare il sistema di riferimento
  spaziale del layer con Aspose.GIS per .NET. Impara a definire il riferimento spaziale,
  aggiungere una feature puntuale e recuperare il codice EPSG.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Imposta il sistema di riferimento spaziale del layer
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Crea un layer vettoriale e imposta il sistema di riferimento spaziale del layer
url: /it/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un layer vettoriale e imposta il sistema di riferimento spaziale del layer

## Introduzione
Nel vasto panorama dei sistemi informativi geografici (GIS), **Aspose.GIS per .NET** si distingue come una libreria robusta e ad alte prestazioni che supporta più di **70** formati vettoriali e raster e può elaborare file più grandi di **10 GB** senza caricare l'intero dataset in memoria. In questo tutorial **creerai un layer vettoriale**, definirai il suo riferimento spaziale, **aggiungerai una feature puntuale** e recupererai il codice EPSG — tutto con una guida chiara passo‑passo. Che tu stia costruendo un servizio di mappatura, una pipeline di conversione dati o un motore di analisi spaziale, padroneggiare questi fondamenti garantirà che il sistema di coordinate del tuo shapefile sia accurato e che il tuo flusso di lavoro GIS sia affidabile.

## Risposte rapide
- **Che cosa significa “create vector layer”?** Crea un nuovo layer GIS (ad es., uno Shapefile) che può memorizzare geometrie come punti, linee o poligoni.  
- **Quale codice EPSG è usato nell'esempio?** EPSG 26918 (NAD83 / UTM zona 18N).  
- **Posso aggiungere una feature puntuale dopo aver creato il layer?** Sì — usa `ConstructFeature()` e assegna una geometria `Point`.  
- **Come recupero il CRS del layer?** Leggi `layer.SpatialReferenceSystem.EpsgCode` o `.Name`.  
- **È necessaria una licenza per Aspose.GIS?** È disponibile una prova gratuita; è richiesta una licenza per l'uso in produzione.

## Che cos'è creare un layer vettoriale?
L'operazione **create vector layer** crea un nuovo dataset vettoriale (come uno Shapefile) che può contenere feature geometriche e dati attributivi. In Aspose.GIS, ciò avviene istanziando un oggetto `VectorLayer` con un driver e un sistema di riferimento spaziale.

## Perché impostare correttamente il sistema di coordinate del layer (CRS)?
Impostare il corretto sistema di riferimento delle coordinate (CRS) garantisce che ogni geometria memorizzata sia allineata con altri dataset spaziali. Con Aspose.GIS è possibile definire il CRS usando un codice EPSG standard, il che garantisce l'interoperabilità con i software GIS a livello globale. Per esempio, EPSG 26918 definisce NAD83 / UTM zona 18N, una proiezione comune per i dati nella costa orientale degli Stati Uniti.

## Prerequisiti
- Esperienza di sviluppo .NET (C# o VB.NET).  
- Visual Studio 2022 o versioni successive.  
- Aspose.GIS for .NET library – scaricala **[qui](https://releases.aspose.com/gis/net/)**.  
- Familiarità di base con i sistemi di riferimento spaziale (CRS/EPSG).

## Importa i namespace
Il namespace `Aspose.Gis` fornisce le classi GIS di base, mentre `Aspose.Gis.Geometries` offre tipi di geometria come `Point`.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Come si crea un layer vettoriale in Aspose.GIS per .NET?
`VectorLayer` rappresenta un dataset vettoriale come uno Shapefile e fornisce metodi per creare, leggere e modificare le feature.  
`SpatialReferenceSystem` definisce il sistema di riferimento delle coordinate usando un codice EPSG.  

Carica la cartella di destinazione, definisci un `SpatialReferenceSystem` con codice EPSG e chiama `VectorLayer.Create` con il driver Shapefile. Questa singola chiamata crea un nuovo file `.shp`, scrive i file di accompagnamento `.shx` e `.dbf`, e incorpora i metadati CRS, pronto per l'inserimento delle feature in modo efficiente.

### Passo 1: Specifica la directory del documento
Inizia specificando il percorso della tua directory dei documenti. Questa sarà la posizione in cui verranno archiviati i file dei dati spaziali.

```csharp
string dataDir = "Your Document Directory";
```

### Passo 2: Definisci il riferimento spaziale e imposta il sistema di coordinate dello Shapefile
`SpatialReferenceSystem` rappresenta il CRS di un layer, identificato da un codice EPSG.  

Definisci il percorso per lo Shapefile e **definisci il riferimento spaziale** usando il codice EPSG (26918 in questo esempio). Questo passo **imposta il sistema di coordinate dello Shapefile** per il layer.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Come aggiungere una feature puntuale a un layer vettoriale?
`Point` è un tipo di geometria che rappresenta una singola coppia di coordinate X/Y.  

Costruisci una nuova feature, assegna una geometria `Point` con le coordinate X/Y desiderate e aggiungi la feature al `VectorLayer` aperto. L'operazione scrive la geometria nel file `.shp` e il record attributo nel file `.dbf` in un'unica transazione.

### Passo 3: Crea il layer vettoriale
`ConstructFeature` crea un nuovo oggetto feature che può contenere dati di geometria e attributi.  

Ora **crea il layer vettoriale** con il percorso Shapefile specificato, il tipo di driver (Shapefile) e il sistema di riferimento spaziale appena definito.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Passo 4: Aggiungi la feature puntuale al layer
Costruisci una nuova feature e **aggiungi la feature puntuale** impostando la sua geometria (un `Point` con coordinate 60, 24). Quindi aggiungi la feature al layer vettoriale.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Passo 5: Recupera le informazioni del sistema di riferimento spaziale (Recupera il codice EPSG)
Apri il Vector Layer e recupera le informazioni sul sistema di riferimento spaziale, come il codice EPSG e il nome leggibile. Questo dimostra come **recuperare il codice EPSG** e **impostare il CRS del layer**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| **Il layer non si apre** | Driver errato o percorso file corrotto | Verifica `Drivers.Shapefile` e assicurati che `path` punti a un file `.shp` esistente. |
| **CRS visualizzato errato** | Uso di un codice EPSG sbagliato | Controlla nuovamente il codice EPSG con una fonte autorevole (ad es., EPSG.io). |
| **Feature non salvata** | Mancata chiamata a `layer.Add(feature)` all'interno del blocco `using` | Assicurati che il metodo `Add` venga eseguito prima che il layer venga eliminato. |

## Domande frequenti
**D: Come cambio il CRS di uno Shapefile esistente?**  
R: Apri il layer, crea un nuovo `SpatialReferenceSystem` con il codice EPSG desiderato, assegnalo a `layer.SpatialReferenceSystem`, quindi salva il layer.

**D: Posso aggiungere altri tipi di geometria (ad es., poligoni) usando lo stesso approccio?**  
R: Sì — sostituisci `new Point(x, y)` con `new Polygon(...)` o `new LineString(...)` secondo necessità.

**D: È possibile lavorare con dataset di grandi dimensioni in modo efficiente?**  
R: Usa le API di streaming (`VectorLayer.Create` con `FeatureCollection`) e rilascia i layer tempestivamente per liberare le risorse.

**D: Aspose.GIS supporta la trasformazione delle coordinate?**  
R: Sì — usa `Geometry.Transform(targetSrs)` per riproiettare le geometrie tra diversi riferimenti spaziali.

**D: Quali versioni di .NET sono supportate?**  
R: Aspose.GIS funziona con .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

---

**Ultimo aggiornamento:** 2026-06-15  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Crea un layer vettoriale e imposta la tolleranza di linearizzazione usando Aspose.GIS per .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Crea un layer vettoriale in File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [riferimento spaziale wgs84 – Aggiungi layer a GDB usando Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}