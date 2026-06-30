---
date: 2026-06-30
description: Scopri come creare un livello vettoriale in un File Geodatabase usando
  Aspose.GIS per .NET. Gestisci dati geospaziali con riferimento spaziale WGS84 e
  opzioni file gdb.
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: Crea File GDB con un singolo livello
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Crea livello vettoriale in File GDB – Tutorial Aspose.GIS .NET
url: /it/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un layer vettoriale in File GDB

## Introduzione
Se hai bisogno di **create vector layer** all'interno di un File Geodatabase (GDB) e gestire i dati geospaziali in modo efficiente, Aspose.GIS per .NET ti offre un approccio pulito, code‑first. In questa guida passo‑passo ti mostreremo come scrivere una feature lineare, configurare le opzioni del file GDB e lavorare con il riferimento spaziale WGS84—tutto in poche righe di C#. Alla fine sarai in grado di contare le feature in un layer e integrare il GDB risultante in qualsiasi flusso di lavoro di mapping o analisi .NET.

## Risposte rapide
- **Che cosa significa “create vector layer”?** Significa aggiungere un nuovo dataset vettoriale (punti, linee o poligoni) a un file geodatabase.  
- **Quale libreria dovrei usare?** Aspose.GIS per .NET fornisce pieno supporto per la creazione e la modifica di File GDB.  
- **Ho bisogno di una licenza per lo sviluppo?** Una versione di prova gratuita funziona per i test; è necessaria una licenza commerciale per la produzione.  
- **Posso impostare il riferimento spaziale?** Sì – usa `SpatialReferenceSystem.Wgs84` per il comune datum WGS84.  
- **Quante righe di codice?** Meno di 30 righe per creare il GDB, aggiungere una feature lineare e leggere nuovamente il conteggio delle feature.

## Cos'è un'operazione “create vector layer”?
Creare un layer vettoriale definisce una nuova tabella in un geodatabase che memorizza oggetti geometrici (punti, linee, poligoni) e i loro attributi. Ogni riga rappresenta una feature e la colonna geometria contiene la sua forma. In Aspose.GIS lo crei istanziando un `FeatureClass` all'interno di un `FileGdbDataSource` e specificando il tipo di geometria.

## Perché usare Aspose.GIS per creare un layer vettoriale?
Aspose.GIS elimina le dipendenze esterne e supporta **50+** formati GIS, rendendolo una soluzione unica per gli sviluppatori .NET.  
Fornisce compressione integrata dei file GDB (fino al 70 % di riduzione per i dati vettoriali tipici), indicizzazione spaziale e gestione completa di WGS84 pronta all'uso.  
La libreria funziona su .NET Framework 4.6+, .NET Core 2.0+ e .NET 5/6, così puoi mirare a qualsiasi ambiente Windows moderno o cross‑platform senza librerie native aggiuntive.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Aspose.GIS for .NET** – scaricalo dalla [Aspose.GIS for .NET download page](https://releases.aspose.com/gis/net/).  
2. **Un ambiente di sviluppo .NET** – Visual Studio, Rider o il `dotnet` CLI.  
3. **Una cartella** dove verrà creato il File GDB (la chiameremo *Your Document Directory*).

## Importa gli spazi dei nomi
Le istruzioni `using` portano i tipi richiesti nello scope.  

Lo spazio dei nomi `Document` fornisce gli oggetti GIS di base, mentre `System.IO` gestisce i percorsi dei file.

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

## Passo 1: Configura la tua directory dei documenti
Sostituisci `"Your Document Directory"` con il percorso assoluto dove desideri che il File GDB risieda.  
Creare la directory in anticipo evita l'errore “File not found” che spesso colpisce i nuovi utenti.

```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Crea un File Geodatabase con un singolo layer
FileGdbOptions è una classe che consente di configurare la compressione, l'indicizzazione spaziale e altre impostazioni per un File Geodatabase.  
Questo frammento **creates a vector layer** usando `FileGdbOptions`, scrive una semplice feature lineare e la memorizza in un File GDB che utilizza il **spatial reference WGS84**.

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

## Passo 3: Apri il File Geodatabase e recupera le informazioni del layer
`FileGdbDataSource` è il punto di ingresso per creare e aprire File Geodatabase.  
`FeatureClass` rappresenta un layer vettoriale all'interno di un geodatabase e fornisce l'accesso alle sue feature.  
Qui **count features in the layer** aprendo il dataset e stampando il numero di feature – in questo caso, `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## Come verificare che il layer sia stato creato correttamente?
Apri il geodatabase con `FileGdbDataSource.Open` e interroga il `FeatureClass`. La proprietà `Count` restituisce il numero totale di feature, confermando che la linea è stata salvata. Questo rapido passaggio di verifica ti aiuta a individuare i problemi in anticipo, soprattutto quando automatizzi importazioni massive.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **`File not found`** | Variabile `path` errata | Verifica che `dataDir` punti a una cartella esistente e che `path` lo combini con un nome file, ad esempio `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Utilizzo di un tipo di geometria non consentito in File GDB | Usa `Point`, `LineString` o `Polygon` per i layer di base. |
| **`License not set`** | Esecuzione senza una licenza valida in produzione | Registra la tua licenza con `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Domande frequenti
### Posso usare Aspose.GIS per .NET nei miei progetti .NET esistenti?
Sì, Aspose.GIS per .NET può essere integrato senza problemi nei tuoi progetti .NET esistenti.

### È disponibile una versione di prova per Aspose.GIS per .NET?
Sì, puoi esplorare le funzionalità di Aspose.GIS per .NET scaricando la [free trial version](https://releases.aspose.com/).

### Dove posso trovare la documentazione dettagliata per Aspose.GIS per .NET?
Consulta la [documentation](https://reference.aspose.com/gis/net/) per informazioni complete su Aspose.GIS per .NET.

### Come posso ottenere supporto per Aspose.GIS per .NET?
Visita il [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) per supporto e assistenza dalla community.

### Sono disponibili licenze temporanee per Aspose.GIS per .NET?
Sì, puoi ottenere una [temporary license](https://purchase.aspose.com/temporary-license/) per Aspose.GIS per .NET.

---

**Ultimo aggiornamento:** 2026-06-30  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Crea dataset File Geodatabase .NET con Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Crea layer vettoriale e imposta il sistema di riferimento spaziale del layer](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Come eliminare un layer dal dataset File GDB con Aspose.GIS](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}