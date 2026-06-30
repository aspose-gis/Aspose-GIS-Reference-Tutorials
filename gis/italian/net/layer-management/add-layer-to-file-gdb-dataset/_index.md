---
date: 2026-06-30
description: Scopri come aggiungere un layer a un dataset File GDB usando Aspose.GIS
  con riferimento spaziale WGS84. Segui questa guida passo‑passo per aggiungere un
  layer in .NET.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: Aggiungi layer a dataset File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Come aggiungere un layer a un dataset File GDB con riferimento spaziale WGS84
  usando Aspose.GIS
url: /it/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# come aggiungere layer – riferimento spaziale wgs84 con Aspose.GIS

## Introduzione
Pronto a potenziare il tuo flusso di lavoro GIS con Aspose.GIS per .NET? In questo tutorial imparerai **come aggiungere layer** a un dataset File GDB lavorando con il sistema di coordinate **spatial reference WGS84**. Ti guideremo passo passo, dalla preparazione della cartella dei dati alla convalida del layer appena creato, così potrai iniziare a manipolare i dati geografici con fiducia ed efficienza.

## Risposte rapide
- **Qual è il sistema di coordinate principale utilizzato?** spatial reference wgs84 (WGS 84)  
- **Quale libreria fornisce l'API?** Aspose.GIS for .NET  
- **È necessaria una licenza per i test?** Sì – è disponibile una licenza temporanea Aspose.  
- **Posso aggiungere attributi al nuovo layer?** Assolutamente, è possibile definire qualsiasi numero di attributi di feature.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Cos'è il riferimento spaziale wgs84?
Il riferimento spaziale wgs84 (World Geodetic System 1984) è il sistema di coordinate geografiche più ampiamente utilizzato. Definisce latitudine e longitudine in gradi e funge da CRS predefinito per molti dataset GIS, incluso quello che creeremo in questa guida.

## Perché usare Aspose.GIS per aggiungere un layer?
Carica i tuoi dati GIS senza binari di terze parti e mantieni il pieno controllo sulla definizione dello schema. Aspose.GIS supporta **oltre 40 sistemi di riferimento spaziale**, può elaborare file più grandi di **2 GB** senza caricare l'intero dataset in memoria, e funziona su Windows, Linux e macOS. Questo lo rende una soluzione affidabile e multipiattaforma per l'automazione GIS di livello enterprise.

## Prerequisiti
- Aspose.GIS for .NET Library: Scarica e installa la libreria da [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Document Directory: Crea una cartella dedicata sul tuo computer per archiviare i file GIS.  
- Una licenza temporanea Aspose (opzionale per la valutazione) – vedi le FAQ qui sotto per il link di download.

## Importa Namespace
Aggiungi le istruzioni `using` necessarie al tuo progetto C# così da poter accedere alle classi Aspose.GIS:

*Non è necessario alcun blocco di codice qui; aggiungi semplicemente le seguenti righe all'inizio del tuo file:*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## Passo 1: Copia la directory
**Definition anchor:** Un dataset File GDB è un geodatabase ESRI basato su cartelle che memorizza i dati spaziali in un insieme di file.  
Prima, duplica la cartella che contiene il dataset GDB originale. Mantenere una copia protegge i dati sorgente mentre sperimenti.

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

## Passo 2: Apri il dataset e verifica la capacità di creazione
`Dataset` rappresenta una collezione di layer GIS memorizzati in un File GDB. Apri il dataset appena copiato e conferma che può creare nuovi layer. La proprietà `CanCreateLayers` dovrebbe restituire **True**. **`CanCreateLayers` è una proprietà booleana che indica se il dataset supporta la creazione di nuovi layer.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Passo 3: Crea e popola un nuovo layer con riferimento spaziale wgs84
Ora creiamo un layer chiamato **data** e impostiamo esplicitamente il suo riferimento spaziale a **Wgs84**. Aggiungiamo anche un semplice attributo chiamato **Name** e inseriamo una feature punto. **`CreateLayer` crea un nuovo layer nel dataset con il nome e il riferimento spaziale specificati.** **`SpatialReference` rappresenta il sistema di coordinate usato da un layer.** **`Feature` è un oggetto geografico individuale (punto, linea o poligono) memorizzato in un layer.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Passo 4: Apri e valida il layer aggiunto
Infine, apri il layer appena creato e verifica il suo contenuto. La console mostrerà che il layer contiene una feature e che l'attributo **Name** corrisponde a quanto impostato. **`Layer.Open` apre un layer esistente per lettura o modifica.** Questo conferma che il layer è stato aggiunto correttamente e che il riferimento spaziale è WGS84.

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

## Come aggiungere un layer a un dataset File GDB?
Carica il dataset, chiama `CreateLayer` con il nome e il riferimento spaziale desiderati, definisci lo schema degli attributi e poi inserisci le feature. Tutto ciò può essere fatto con poche chiamate ai metodi di Aspose.GIS, e l'API gestisce automaticamente il blocco dei file e la convalida dello schema. Il processo garantisce che il nuovo layer rispetti il riferimento spaziale del dataset, che le definizioni degli attributi siano memorizzate nello schema del layer e che i dati possano essere accessibili da qualsiasi software GIS che supporti File GDB.

## Problemi comuni e consigli
- **Percorso errato:** Assicurati che `dataDir` termini con un separatore di percorso (`/` o `\`) in modo che le stringhe concatenate formino percorsi file validi.  
- **Errori di licenza:** Se visualizzi avvisi di licenza, applica una licenza temporanea dal portale Aspose prima di eseguire il codice.  
- **Mancata corrispondenza CRS:** Quando apri il layer in seguito in un altro strumento GIS, verifica che lo strumento riconosca WGS 84 (EPSG:4326) come sistema di coordinate.  
- **Dataset di grandi dimensioni:** Per dataset superiori a 1 GB, considera l'uso di `Dataset.OpenReadOnly` per ridurre il consumo di memoria.

## Domande frequenti
### Q: Posso usare Aspose.GIS per .NET con altre librerie GIS?
A: Sì, Aspose.GIS funziona in modo indipendente ma può essere combinato con librerie come GDAL o NetTopologySuite per elaborazioni avanzate.

### Q: È disponibile una licenza temporanea per scopi di test?
A: Sì, è possibile ottenere una licenza temporanea da [qui](https://purchase.aspose.com/temporary-license/) per test e valutazione.

### Q: Quali sistemi di riferimento spaziale supporta Aspose.GIS per .NET?
A: Aspose.GIS supporta oltre **40 codici EPSG**, inclusi sistemi popolari come WGS84 (EPSG:4326), Web Mercator (EPSG:3857) e NAD83 (EPSG:4269). Esplora la documentazione completa [qui](https://reference.aspose.com/gis/net/).

### Q: Posso contribuire alla community di Aspose.GIS?
A: Assolutamente! Partecipa alle discussioni e condividi le tue esperienze sul [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### Q: Dove posso trovare la documentazione dettagliata per Aspose.GIS per .NET?
A: Esplora la documentazione completa [qui](https://reference.aspose.com/gis/net/) per informazioni approfondite su tutte le classi, i metodi e le best practice.

---

**Ultimo aggiornamento:** 2026-06-30  
**Testato con:** Aspose.GIS for .NET (latest stable version)  
**Autore:** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Tutorial correlati

- [Crea dataset File Geodatabase .NET con Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Crea layer vettoriale in File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Crea dataset File GDB e imposta le tolleranze per un layer](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}