---
date: 2026-09-10
description: Scopri come convertire curve in linee (linearize geometry) usando Aspose.GIS
  for .NET, consentendo un'elaborazione e analisi geospaziale efficienti nelle tue
  app .NET.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Linearizza una geometria
og_description: Converti curve in linee (linearize geometry) usando Aspose.GIS for
  .NET. Scopri step‑by‑step come simplify geometries per faster rendering e broader
  compatibility.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Converti curve in linee con Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Come convertire curve in linee con Aspose.GIS for .NET
url: /it/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti curve in linee (linearizza geometria) con Aspose.GIS per .NET

## Introduzione
Se hai bisogno di **convertire curve in linee** per la mappatura, l'analisi spaziale o attività di scambio dati, Aspose.GIS per .NET ti offre un modo pulito e programmatico per farlo. In questo tutorial ti guideremo attraverso un esempio completo e reale che mostra come prendere una geometria complessa—contenente curve e forme composte—e trasformarla in una semplice rappresentazione lineare che funziona con qualsiasi sistema GIS.

## Risposte rapide
- **Cosa significa “convertire curve in linee”?** Trasforma le geometrie curve in segmenti lineari.  
- **Perché scegliere Aspose.GIS?** La libreria supporta oltre 30 formati GIS e gestisce la conversione della geometria senza strumenti esterni.  
- **Cosa serve in anticipo?** .NET Framework o .NET Core, Visual Studio (o qualsiasi IDE C#), e il pacchetto NuGet Aspose.GIS.  
- **Quanto tempo impiega l'esempio?** Meno di cinque minuti una volta installata la libreria.  
- **Posso esportare in altri formati?** Assolutamente—sostituisci il driver KML con Shapefile, GeoJSON, ecc.  
Puoi scaricare l'intera suite di prodotti dal [Aspose website](https://releases.aspose.com/).

## Cosa significa convertire curve in linee?
Convertire curve in linee (anche chiamato **linearizzare geometria**) sostituisce ogni segmento curvo con una serie di brevi segmenti lineari, creando una *geometria lineare*. Questo rende il rendering fino a cinque volte più veloce, riduce il consumo di memoria e garantisce che i dati possano essere consumati da servizi GIS legacy che accettano solo feature lineari.

## Perché convertire curve in linee?
Le geometrie lineari vengono renderizzate e interrogate fino a **5× più velocemente** rispetto alle loro controparti curve, e **oltre 30 piattaforme GIS** accettano solo feature lineari. Semplificare la geometria riduce anche le dimensioni del file per anteprime web e abilita algoritmi—come l'analisi di rete o il clustering—che richiedono input lineare.

## Come linearizzare la geometria?
Usa il metodo `ToLinearGeometry()` fornito da Aspose.GIS. Tessella automaticamente ogni curva in una geometria in segmenti lineari mantenendo eventuali valori Z, così ottieni un'approssimazione lineare senza perdere dati di elevazione. Puoi anche specificare una tolleranza per controllare la deviazione massima tra la curva originale e i segmenti generati, consentendoti di bilanciare precisione e dimensione del file. Il metodo funziona sia per geometrie 2‑D che 3‑D.

## Prerequisiti
Prima di immergerti nel codice, assicurati di avere:

1. **Aspose.GIS for .NET** – scaricalo dal [Aspose.GIS website](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (o .NET Core) installato sulla tua macchina di sviluppo.  
3. **Visual Studio** (o qualsiasi IDE compatibile C#) per scrivere ed eseguire l'esempio.

## Importa spazi dei nomi
Per iniziare a utilizzare le funzionalità di Aspose.GIS, importa gli spazi dei nomi richiesti.

### Spazi dei nomi principali di Aspose.GIS
Lo spazio dei nomi `Aspose.Gis` contiene le classi di geometria core, i driver e le utility necessarie per tutte le operazioni GIS.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Driver per il formato di destinazione
`Aspose.Gis.Drivers` fornisce factory statiche per ogni formato di file supportato; `Drivers.Kml` crea un writer KML.  
```csharp
using Aspose.GIS.Kml;
```

## Guida passo‑passo per convertire curve in linee
Di seguito trovi una walkthrough dettagliata di ogni riga di codice, spiegando **come convertire curve in linee** e perché ogni passaggio è importante.

### Passo 1: Definisci il percorso di output
`Path.Combine` costruisce un percorso di file indipendente dalla piattaforma, gestendo automaticamente le barre rovesciate di Windows e le barre forward di Unix.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Sostituisci `"Your Document Directory"` con la cartella in cui desideri salvare il file KML.

### Passo 2: Crea un layer per il file di output
Un *layer* raggruppa feature geografiche dello stesso tipo. Qui istanziamo un nuovo layer KML che memorizzerà la geometria linearizzata.  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### Passo 3: Costruisci una nuova feature
Una *feature* rappresenta un singolo oggetto geografico (punto, linea, poligono, ecc.). Allegheremo la nostra geometria lineare a questa feature.  
```csharp
var feature = layer.ConstructFeature();
```

### Passo 4: Definisci la geometria complessa originale
`Geometry.FromWkt` analizza una stringa Well‑Known Text (WKT) in un oggetto geometria. Il WKT di esempio include un `LineString`, un `CompoundCurve` e un `CircularString` per mostrare la gestione delle curve.  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### Passo 5: Converti curve in linee
`ToLinearGeometry()` tessella ogni curva nella geometria di origine in segmenti lineari, restituendo una nuova geometria lineare che conserva eventuali coordinate Z.  
```csharp
var linear = geometry.ToLinearGeometry();
```

### Passo 6: Assegna la geometria lineare alla feature
La proprietà `Geometry` della feature ora contiene la versione semplificata e lineare della forma originale.  
```csharp
feature.Geometry = linear;
```

### Passo 7: Aggiungi la feature al layer
Aggiungere la feature al layer KML la mette in coda per la scrittura; al termine del blocco `using`, il layer svuota i dati nel file di output.  
```csharp
layer.Add(feature);
```

## Problemi comuni e consigli professionali
- **Separatori di percorso:** Usa `Path.Combine` per evitare problemi su Windows vs. Linux.  
- **Geometrie molto grandi:** Linearizzare forme complesse può generare migliaia di vertici; considera di chiamare `Simplify()` dopo la linearizzazione per ridurre il numero di punti.  
- **Selezione del driver:** Se ti serve un formato di output diverso, sostituisci `Drivers.Kml` con `Drivers.Shapefile`, `Drivers.GeoJson`, ecc., e cambia l'estensione del file di conseguenza.  
- **Preservare i valori Z:** `ToLinearGeometry()` mantiene le coordinate 3‑D (Z), così non perdi i dati di elevazione.

## Domande frequenti (FAQ)

**D: Aspose.GIS per .NET è compatibile con .NET Core?**  
R: Sì, Aspose.GIS funziona con .NET Core, consentendo applicazioni cross‑platform.

**D: Posso lavorare con diversi formati di file GIS usando Aspose.GIS per .NET?**  
R: Assolutamente! La libreria supporta KML, Shapefile, GeoJSON e molti altri formati—oltre 30 in totale.

**D: Aspose.GIS offre operazioni e analisi spaziali?**  
R: Sì, fornisce un'ampia gamma di funzioni spaziali, dal buffering alle join spaziali.

**D: È disponibile una versione di prova gratuita?**  
R: Sì, puoi scaricare una prova gratuita dal [Aspose.GIS website](https://releases.aspose.com/gis/net/).

**D: Dove posso ottenere supporto se incontro problemi?**  
R: Visita il [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) per il supporto della community e del personale.

### Domande comuni aggiuntive

**D: Posso linearizzare geometrie che contengono coordinate 3D (Z)?**  
R: Sì, `ToLinearGeometry()` funziona sia con geometrie 2D che 3D; i valori Z sono preservati.

**D: Come influisce la linearizzazione sulla dimensione del file?**  
R: Convertire curve in molti segmenti lineari brevi può aumentare la dimensione del file; esegui `Simplify()` dopo la linearizzazione se la dimensione è un problema.

**D: Posso controllare la lunghezza dei segmenti quando converto curve in linee?**  
R: Il metodo predefinito usa una tolleranza interna. Per una segmentazione personalizzata puoi tessellare manualmente le curve prima di chiamare `ToLinearGeometry()`.

## Conclusione
In questo tutorial abbiamo coperto **come convertire curve in linee** (linearizzare la geometria) usando Aspose.GIS per .NET, dalla configurazione dell'ambiente alla scrittura del risultato linearizzato in un file KML. Ora puoi integrare questo flusso di lavoro in applicazioni di mappatura, pipeline di elaborazione dati o qualsiasi progetto GIS che richieda geometrie semplificate.

---

**Last Updated:** 2026-09-10  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose

## Tutorial correlati

- [Come creare GeoJSON con tolleranza Aspose.GIS per .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Converti Poligono in Linea con Aspose.GIS per .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Impara a creare geometria LineString con Aspose.GIS per .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}