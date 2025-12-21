---
date: 2025-12-21
description: Scopri come creare un layer vettoriale, impostare la tolleranza di linearizzazione
  e aggiungere una feature al layer usando Aspose.GIS per .NET. Segui questa guida
  passo‑passo per esportare file GeoJSON.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Creare un layer vettoriale e impostare la tolleranza di linearizzazione usando
  Aspose.GIS per .NET
url: /it/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea Vector Layer e imposta Linearization Tolerance usando Aspose.GIS per .NET

## Introduction
Se hai bisogno di **create vector layer** file, controllare la precisione delle curve e esportare il risultato come documento GeoJSON, Aspose.GIS per .NET lo rende semplice. In questo tutorial imparerai come configurare le opzioni GeoJSON, impostare la tolleranza di linearizzazione e **add feature to layer** oggetti—tutto mantenendo il codice pulito e pronto per la produzione.

## Quick Answers
- **What does “create vector layer” mean?** Crea un nuovo dataset GIS vettoriale (ad es., un file GeoJSON) che può memorizzare geometrie e attributi.  
- **How to set tolerance?** Usa la proprietà `LinearizationTolerance` di `GeoJsonOptions`.  
- **Can I export a GeoJSON file?** Sì—basta creare un `VectorLayer` con il driver `Drivers.GeoJson`.  
- **Do I need a license?** Una licenza valida di Aspose.GIS sblocca tutte le funzionalità; una licenza temporanea è valida per la valutazione.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is “create vector layer”?
Creare un vector layer significa inizializzare un nuovo contenitore GIS (come un file GeoJSON) che può contenere feature geometriche come punti, linee e poligoni. Questo layer diventa il target per qualsiasi geometria che costruisci e per qualsiasi attributo che aggiungi.

## Why configure GeoJSON options?
Configurare le opzioni GeoJSON—soprattutto la **linearization tolerance**—assicura che le geometrie curve (ad es., `CircularString`) siano approssimate con una precisione che soddisfa i requisiti di accuratezza della tua applicazione. Questo passaggio è cruciale quando successivamente **export GeoJSON file** per l'uso in mappe web o analisi spaziali.

## Prerequisites
1. **Visual Studio** installato (qualsiasi versione recente).  
2. **Licenza Aspose.GIS** (o una chiave di valutazione temporanea).  
3. Libreria **Aspose.GIS for .NET** scaricata e referenziata nel tuo progetto.  
4. Familiarità di base con **C#**.

## Import Namespaces
Per prima cosa, importa gli spazi dei nomi richiesti così il compilatore sa dove trovare le classi GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step‑by‑Step Guide

### Step 1: Configure GeoJSON Options (how to set tolerance)
Creeremo un oggetto `GeoJsonOptions` e diremo ad Aspose.GIS quanto deve essere vicina la geometria linearizzata alla curva originale.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Step 2: Define the Output Path (how to export GeoJSON)
Specifica dove verrà salvato il file risultante. Sostituisci il segnaposto con la tua cartella reale.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Step 3: **Create Vector Layer** with the configured options
Ora **Create Vector Layer** usando il metodo `VectorLayer.Create`. Il blocco `using` garantisce il corretto rilascio delle risorse.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Step 4: Construct a Geometry (e.g., a circular string)
Qui costruiamo una geometria di esempio—un `CircularString`. Puoi sostituirla con qualsiasi WKT valido.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Step 5: **Add Feature to Layer** and save
Infine, creiamo una feature, assegniamo la geometria e la aggiungiamo al layer. Questo è il nucleo dell'operazione **Add Feature to Layer**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Quando il blocco `using` termina, il layer viene scritto automaticamente nel file definito in `path`, fornendoti un file GeoJSON pronto all'uso.

## Common Issues & Tips
- **Incorrect path** – Assicurati che la directory esista e che tu abbia i permessi di scrittura.  
- **Tolerance too low** – Impostare `LinearizationTolerance` a un valore molto piccolo può aumentare drasticamente la dimensione del file. Regola in base alle tue esigenze di accuratezza.  
- **License errors** – Se vedi avvisi di licenza, verifica che il file di licenza sia caricato correttamente prima di qualsiasi chiamata a Aspose.GIS.

## Frequently Asked Questions

**Q: Aspose.GIS per .NET è compatibile con altri framework .NET?**  
A: Sì, funziona con .NET Framework, .NET Core e .NET 5/6/7.

**Q: Posso usare Aspose.GIS in progetti commerciali?**  
A: Assolutamente. Una licenza commerciale rimuove tutte le restrizioni di valutazione.

**Q: Aspose.GIS supporta altri formati GIS oltre a GeoJSON?**  
A: Sì, supporta Shapefile, KML, GML e molti altri.

**Q: È disponibile una versione di prova?**  
A: Puoi scaricare una prova gratuita dal sito web di Aspose.

**Q: Dove posso ottenere supporto?**  
A: Usa i forum di Aspose o il link di supporto nella sezione risorse.

## Conclusion
Seguendo questi passaggi ora sai come **create vector layer**, configurare la tolleranza di linearizzazione e **add feature to layer** per una creazione senza problemi di **export GeoJSON file**. Esplora tipi di geometria aggiuntivi e la gestione degli attributi per sfruttare al massimo Aspose.GIS nei tuoi progetti GIS .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose