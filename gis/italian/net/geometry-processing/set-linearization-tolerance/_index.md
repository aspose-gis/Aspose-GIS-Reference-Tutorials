---
date: 2026-05-31
description: Scopri come creare GeoJSON, configurare le opzioni di GeoJSON e aggiungere
  una feature a un layer utilizzando Aspose.GIS per .NET. Segui questa guida passo‑passo.
keywords:
- how to create geojson
- add feature to layer
- configure geojson options
linktitle: Imposta la tolleranza Linearization
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  headline: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create GeoJSON, configure GeoJSON options, and add feature
    to layer using Aspose.GIS for .NET. Follow this step‑by‑step guide.
  name: How to Create GeoJSON with Tolerance Aspose.GIS for .NET
  steps:
  - name: Configure GeoJSON Options (how to set tolerance)
    text: '`GeoJsonOptions` specifies the serialization settings used when writing
      GeoJSON files. `GeoJsonOptions` defines how Aspose.GIS serializes GeoJSON, including
      linearization tolerance, coordinate precision, and other output settings. We’ll
      create a `GeoJsonOptions` object and tell Aspose.GIS how close '
  - name: Define the Output Path (how to export GeoJSON)
    text: Specify the full file path where the resulting GeoJSON will be saved. Ensure
      the folder exists and the application has write permissions.
  - name: '**Create Vector Layer** with the configured options'
    text: The `VectorLayer` class represents a GIS container that can read and write
      spatial data. `Drivers.GeoJson` is the driver identifier for writing GeoJSON
      format files. Using `VectorLayer.Create` together with the `Drivers.GeoJson`
      driver and the previously configured `GeoJsonOptions` creates a new Geo
  - name: Construct a Geometry (e.g., a circular string)
    text: '`CircularString` is a curved line geometry that Aspose.GIS can linearize
      based on the tolerance you set. You can replace this with any valid WKT representation
      such as `POINT`, `LINESTRING`, or `POLYGON`.'
  - name: '**Add Feature to Layer** and save'
    text: '`Feature` is the object that couples a geometry with attribute data. After
      creating a `Feature` instance, assign the geometry, optionally add attribute
      values, and call `layer.Add(feature)` to persist it. When the `using` block
      ends, the layer is automatically written to the file defined in `path`. '
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.
    question: Is Aspose.GIS for .NET compatible with other .NET frameworks?
  - answer: Absolutely. A commercial license removes all evaluation restrictions and
      provides full technical support.
    question: Can I use Aspose.GIS in commercial projects?
  - answer: Yes, it supports over 30 formats—including Shapefile, KML, GML, and CSV—allowing
      seamless conversion between them.
    question: Does Aspose.GIS support other GIS formats besides GeoJSON?
  - answer: You can download a free 30‑day trial from the Aspose website; it includes
      all features.
    question: Is there a trial version available?
  - answer: Use the Aspose forums, the dedicated support portal, or the “Contact Support”
      link in the product dashboard.
    question: Where can I get support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Come creare GeoJSON con tolleranza Aspose.GIS per .NET
url: /it/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare GeoJSON con tolleranza Aspose.GIS per .NET

## Introduzione
Se vuoi **imparare a creare GeoJSON** file, controllare la precisione delle curve e esportare il risultato come un documento pronto all'uso, Aspose.GIS per .NET lo rende semplice. In questo tutorial scoprirai come configurare le opzioni GeoJSON, impostare la tolleranza di linearizzazione e **add feature to layer** oggetti mantenendo il codice pulito e pronto per la produzione.

## Risposte rapide
- **Che cosa significa “create vector layer”?** Crea un nuovo dataset vettoriale GIS (ad esempio, un file GeoJSON) che può memorizzare geometrie e attributi.  
- **Come impostare la tolleranza di linearizzazione?** Imposta la proprietà `LinearizationTolerance` su un'istanza di `GeoJsonOptions` prima di creare il layer.  
- **Posso esportare direttamente un file GeoJSON?** Sì—usa `VectorLayer.Create` con il driver `Drivers.GeoJson` e le opzioni configurate.  
- **È necessaria una licenza?** Una licenza valida di Aspose.GIS sblocca tutte le funzionalità; una chiave di valutazione temporanea funziona per i test.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Che cos'è “create vector layer”?
Creare un vector layer significa inizializzare un nuovo contenitore GIS (come un file GeoJSON) che può contenere punti, linee, poligoni e i relativi dati attributo. Questo layer diventa il target per qualsiasi geometria tu costruisca e per tutti gli attributi che aggiungi.

## Perché configurare le opzioni GeoJSON?
Configurare le opzioni GeoJSON—soprattutto la **linearization tolerance**—assicura che le geometrie curve (ad esempio, `CircularString`) siano approssimate con una precisione che soddisfi i requisiti di accuratezza della tua applicazione. Una configurazione corretta riduce le dimensioni del file preservando la fedeltà visiva, cosa fondamentale quando il GeoJSON è consumato da mappe web o strumenti di analisi spaziale.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Visual Studio** (qualsiasi versione recente).  
2. **Licenza Aspose.GIS** (o una chiave di valutazione temporanea).  
3. **Libreria Aspose.GIS per .NET** referenziata nel tuo progetto.  
4. Familiarità di base con **C#**.

## Importare gli spazi dei nomi
Prima, importa gli spazi dei nomi richiesti in modo che il compilatore sappia dove trovare le classi GIS:

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

## Guida passo‑passo

### Passo 1: Configurare le opzioni GeoJSON (come impostare la tolleranza)
`GeoJsonOptions` specifica le impostazioni di serializzazione usate quando si scrivono file GeoJSON.  
`GeoJsonOptions` definisce come Aspose.GIS serializza GeoJSON, includendo la tolleranza di linearizzazione, la precisione delle coordinate e altre impostazioni di output.  
Creeremo un oggetto `GeoJsonOptions` e indicheremo ad Aspose.GIS quanto la geometria linearizzata deve avvicinarsi alla curva originale.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Passo 2: Definire il percorso di output (come esportare GeoJSON)
Specifica il percorso completo del file dove il GeoJSON risultante sarà salvato. Assicurati che la cartella esista e che l'applicazione abbia i permessi di scrittura.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Passo 3: **Create Vector Layer** con le opzioni configurate
La classe `VectorLayer` rappresenta un contenitore GIS che può leggere e scrivere dati spaziali.  
`Drivers.GeoJson` è l'identificatore del driver per scrivere file in formato GeoJSON.  
Usare `VectorLayer.Create` insieme al driver `Drivers.GeoJson` e alle `GeoJsonOptions` precedentemente configurate crea un nuovo file GeoJSON pronto per l'inserimento di feature.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Passo 4: Costruire una geometria (ad esempio, una stringa circolare)
`CircularString` è una geometria a linea curva che Aspose.GIS può linearizzare in base alla tolleranza impostata. Puoi sostituirla con qualsiasi rappresentazione WKT valida, come `POINT`, `LINESTRING` o `POLYGON`.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Passo 5: **Add Feature to Layer** e salva
`Feature` è l'oggetto che associa una geometria ai dati attributo. Dopo aver creato un'istanza di `Feature`, assegna la geometria, opzionalmente aggiungi valori di attributi e chiama `layer.Add(feature)` per salvarla. Quando il blocco `using` termina, il layer viene scritto automaticamente nel file definito in `path`.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Quando il blocco `using` termina, il layer viene scritto automaticamente nel file definito in `path`, fornendoti un file GeoJSON pronto all'uso.

## Problemi comuni e consigli
- **Percorso errato** – Verifica che la directory esista e che tu abbia i permessi di scrittura.  
- **Tolleranza troppo bassa** – Impostare `LinearizationTolerance` a un valore molto piccolo può aumentare drasticamente le dimensioni del file; una tolleranza di 0.001 di solito bilancia precisione e dimensione.  
- **Errori di licenza** – Se vedi avvisi di licenza, assicurati che il file di licenza sia caricato prima di qualsiasi chiamata a Aspose.GIS.  
- **Nota sulle prestazioni** – Aspose.GIS supporta l'elaborazione di file fino a 2 GB senza caricare l'intero documento in memoria, grazie alla sua architettura di streaming.

## Domande frequenti

**D: Aspose.GIS per .NET è compatibile con altri framework .NET?**  
R: Sì, funziona con .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6/7.

**D: Posso usare Aspose.GIS in progetti commerciali?**  
R: Assolutamente. Una licenza commerciale rimuove tutte le restrizioni di valutazione e fornisce supporto tecnico completo.

**D: Aspose.GIS supporta altri formati GIS oltre a GeoJSON?**  
R: Sì, supporta oltre 30 formati—incluse Shapefile, KML, GML e CSV—consentendo conversioni fluide tra di essi.

**D: È disponibile una versione di prova?**  
R: Puoi scaricare una prova gratuita di 30 giorni dal sito Aspose; include tutte le funzionalità.

**D: Dove posso ottenere supporto?**  
R: Usa i forum Aspose, il portale di supporto dedicato o il link “Contact Support” nella dashboard del prodotto.

## Conclusione
Seguendo questi passaggi ora sai **come creare GeoJSON**, configurare la tolleranza di linearizzazione e **add feature to layer** per un'esportazione GeoJSON senza interruzioni. Esplora tipi di geometria aggiuntivi, la gestione degli attributi e scenari di elaborazione in blocco per sfruttare appieno Aspose.GIS nei tuoi progetti GIS .NET.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Come convertire GeoJSON – Aspose.GIS per .NET](/gis/net/geo-data-conversion/)
- [Crea Vector Layer, Limita la precisione con Aspose.GIS per .NET](/gis/net/geometry-processing/limit-precision-reading-geometries/)
- [Crea Vector Layer in File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}