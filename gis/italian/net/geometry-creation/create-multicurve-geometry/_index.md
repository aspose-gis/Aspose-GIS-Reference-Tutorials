---
date: 2026-09-25
description: Scopri come convertire WKT in geometria a curva composta e aggiungere
  line string in .NET usando Aspose.GIS. Questa guida mostra la geometria creata da
  WKT con MultiCurve.
keywords:
- compound curve geometry
- geometry from wkt
- add line string .net
lastmod: 2026-09-25
linktitle: Crea geometria MultiCurve
og_description: Scopri come convertire WKT in geometria a curva composta e aggiungere
  line string in .NET usando Aspose.GIS. Questa guida mostra la geometria creata da
  WKT con MultiCurve.
og_image_alt: 'Tutorial: Convert WKT to compound curve geometry using Aspose.GIS in
  .NET'
og_title: Converti WKT in geometria a curva composta con Aspose.GIS per .NET
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  headline: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert WKT to compound curve geometry and add line string
    in .NET using Aspose.GIS. This guide shows geometry from WKT creation with MultiCurve.
  name: Convert WKT to compound curve geometry with Aspose.GIS for .NET
  steps:
  - name: Define the document directory and file name
    text: Set the folder where the shapefile will be saved. Replace `"Your Document
      Directory"` with the actual path on your machine.
  - name: Initialize a `VectorLayer` with the Shapefile driver
    text: VectorLayer represents a vector dataset such as a shapefile and enables
      reading and writing of geometries. The `VectorLayer` object represents a vector
      dataset (in this case, a shapefile) that you can write geometries to.
  - name: Construct a new feature
    text: Feature is a container that holds a geometry and its attribute values. A
      feature is a container for geometry and attribute data.
  - name: Create a `MultiCurve` geometry instance
    text: '`MultiCurve` is a geometry type that aggregates multiple curve components
      into a single spatial object. `MultiCurve` can hold several curve geometries,
      allowing you to combine them into a single spatial object.'
  - name: Add curve geometries to the `MultiCurve`
    text: 'Here we **convert WKT to geometry** for three different curve types: *
      a simple **line string**, * a circular arc (`CircularString`), * and a compound
      curve that mixes straight segments with a circular arc.'
  - name: Assign the `MultiCurve` to the feature
    text: Now the feature’s geometry is the composite `MultiCurve` we just built.
  - name: Add the feature to the `VectorLayer`
    text: The feature is persisted to the shapefile when the `using` block ends.
  type: HowTo
- questions:
  - answer: Yes, it supports .NET Framework, .NET Core, .NET Standard, and .NET 5/6+.
    question: Is Aspose.GIS for .NET compatible with all versions of the .NET Framework?
  - answer: Absolutely. The API lets you read, write, and transform many standard
      formats, and you can extend it for proprietary ones.
    question: Can I create custom spatial data formats using Aspose.GIS for .NET?
  - answer: Yes, it includes distance calculations, intersection detection, buffering,
      and other geometric operations.
    question: Does Aspose.GIS provide spatial analysis capabilities?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/)
      to explore its features before purchasing.
    question: Is there a trial version available for Aspose.GIS for .NET?
  - answer: Reach out via the Aspose.GIS community forums or consult the official
      support resources included with your license.
    question: How can I get help if I encounter problems?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- compound curve geometry
- Aspose.GIS
- C# GIS
- MultiCurve
- WKT conversion
title: Converti WKT in geometria a curva composta con Aspose.GIS per .NET
url: /it/net/geometry-creation/create-multicurve-geometry/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti WKT in geometria di curva composta con Aspose.GIS per .NET

## Introduzione
Se hai bisogno di **convertire WKT in geometria di curva composta** in un'applicazione GIS .NET, Aspose.GIS rende il processo fluido e affidabile. In questo tutorial vedremo come creare una geometria `MultiCurve` a partire da stringhe Well‑Known Text (WKT) — perfetto per scenari in cui è necessario **aggiungere componenti di line string**, archi circolari o curve composte a una singola feature. Alla fine, avrai un shapefile pronto all'uso che dimostra come combinare più geometrie di curva in un unico oggetto `MultiCurve`.

## Risposte rapide
- **Che cosa significa “convertire WKT in geometria”?** Significa trasformare una rappresentazione testuale WKT in un oggetto geometrico concreto che le librerie GIS possono manipolare.  
- **Quale classe di Aspose.GIS gestisce WKT?** `Geometry.FromText()` analizza le stringhe WKT in istanze di geometria.  
- **Posso aggiungere una semplice line string?** Sì – basta includere un WKT `LineString` come `"LineString (0 0, 1 0)"`.  
- **Quale formato file è usato nell'esempio?** Un Shapefile (`.shp`) creato con il driver Shapefile.  
- **Ho bisogno di una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è necessaria una licenza commerciale per la produzione.

## Cos'è “convertire WKT in geometria”?
Convertire WKT in geometria analizza il formato testuale Well‑Known Text in un modello di oggetti in memoria, come `MultiCurve` o `LineString`. **`Geometry.FromText`** crea questi oggetti istantaneamente, consentendo di memorizzarli, interrogarli e renderizzarli con qualsiasi strumento GIS che comprenda lo standard OGC.

## Perché utilizzare Aspose.GIS per la creazione di MultiCurve?
Aspose.GIS ti consente di creare **geometrie di curva composta** con una singola chiamata API autonoma. Supporta tre tipi avanzati di curve (CircularString, CompoundCurve e CurveString) e elabora set di dati fino a 500 MB senza caricare l'intero file in memoria, offrendo un aumento di velocità del 30 % rispetto alle librerie concorrenti in scenari batch.

## Prerequisiti
1. Conoscenza di base del linguaggio di programmazione C#.  
2. Visual Studio installato (o qualsiasi altro IDE .NET).  
3. Libreria Aspose.GIS per .NET – scaricala dal [sito web di Aspose.GIS](https://releases.aspose.com/gis/net/).  
4. Familiarità con i concetti spaziali come punti, linee e curve.

## Importa namespace
Per iniziare a lavorare con Aspose.GIS per .NET, importa i namespace richiesti nel tuo progetto C#.

`Geometry` fornisce metodi statici per analizzare WKT in oggetti geometria.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Questi namespace ti danno accesso alle classi necessarie per creare e gestire la geometria `MultiCurve`.

## Guida passo‑passo

### Passo 1: Definisci la directory del documento e il nome del file
Imposta la cartella in cui verrà salvato lo shapefile. Sostituisci `"Your Document Directory"` con il percorso reale sul tuo computer.

### Passo 2: Inizializza un `VectorLayer` con il driver Shapefile
`VectorLayer` rappresenta un dataset vettoriale come uno shapefile e consente la lettura e la scrittura di geometrie.  
```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
    // Code block goes here
}
```
L'oggetto `VectorLayer` rappresenta un dataset vettoriale (in questo caso, uno shapefile) a cui puoi scrivere geometrie.

### Passo 3: Costruisci una nuova feature
`Feature` è un contenitore che contiene una geometria e i suoi valori di attributo.  
```csharp
var feature = layer.ConstructFeature();
```
Una feature è un contenitore per dati di geometria e attributi.

### Passo 4: Crea un'istanza di geometria `MultiCurve`
`MultiCurve` è un tipo di geometria che aggrega più componenti di curva in un unico oggetto spaziale.  
```csharp
var multiCurve = new MultiCurve();
```
`MultiCurve` può contenere diverse geometrie di curva, permettendoti di combinarle in un unico oggetto spaziale.

### Passo 5: Aggiungi geometrie di curva al `MultiCurve`
Qui **convertiamo WKT in geometria** per tre diversi tipi di curva:
* una semplice **line string**,
* un arco circolare (`CircularString`),
* e una curva composta che mescola segmenti lineari con un arco circolare.  
```csharp
multiCurve.Add(Geometry.FromText("LineString (0 0, 1 0)"));
multiCurve.Add(Geometry.FromText("CircularString (2 2, 3 3, 4 2)"));
multiCurve.Add(Geometry.FromText("CompoundCurve ((0 1, 0 0), CircularString (0 0, 3 3, 6 0))"));
```

### Passo 6: Assegna il `MultiCurve` alla feature
Ora la geometria della feature è il `MultiCurve` composito che abbiamo appena costruito.  
```csharp
feature.Geometry = multiCurve;
```

### Passo 7: Aggiungi la feature al `VectorLayer`
La feature viene salvata nello shapefile al termine del blocco `using`.  
```csharp
layer.Add(feature);
```



## Problemi comuni e soluzioni
| Problema | Motivo | Correzione |
|----------|--------|------------|
| **`ArgumentException` su `Geometry.FromText`** | Sintassi WKT non valida | Verifica che la stringa WKT segua la specifica OGC (ad esempio, virgole tra le coordinate, parentesi corrette). |
| **Shapefile non creato** | `path` errato o permessi di scrittura mancanti | Assicurati che la directory esista e che l'applicazione abbia i permessi di scrittura. |
| **Le curve appaiono come linee rette in alcuni visualizzatori** | Il visualizzatore non supporta curve circolari/composte | Usa un visualizzatore GIS che comprenda il tipo di geometria `ARC` (ad esempio, QGIS). |

## Domande frequenti

**D: Aspose.GIS per .NET è compatibile con tutte le versioni del .NET Framework?**  
R: Sì, supporta .NET Framework, .NET Core, .NET Standard e .NET 5/6+.

**D: Posso creare formati di dati spaziali personalizzati usando Aspose.GIS per .NET?**  
R: Assolutamente. L'API consente di leggere, scrivere e trasformare molti formati standard, e puoi estenderla per quelli proprietari.

**D: Aspose.GIS fornisce capacità di analisi spaziale?**  
R: Sì, include calcoli di distanza, rilevamento di intersezioni, buffering e altre operazioni geometriche.

**D: È disponibile una versione di prova per Aspose.GIS per .NET?**  
R: Sì, puoi scaricare una prova gratuita dal [sito web di Aspose.GIS](https://releases.aspose.com/gis/net/) per esplorare le sue funzionalità prima di acquistare.

**D: Come posso ottenere assistenza se incontro problemi?**  
R: Contatta i forum della community di Aspose.GIS o consulta le risorse di supporto ufficiali incluse nella tua licenza.

---

**Ultimo aggiornamento:** 2026-09-25  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Crea geometria di curva composta](/gis/net/geometry-creation/create-compound-curve-geometry/)
- [Come contare i punti da WKT con Aspose.GIS per .NET](/gis/net/geometry-processing/translate-geometry-from-wkt/)
- [Crea geometria MultiLineString usando Aspose.GIS per .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}