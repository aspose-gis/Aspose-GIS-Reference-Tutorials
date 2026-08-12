---
date: 2026-05-21
description: Scopri come creare file geodatabase, impostare object ID e geometry field
  names, aggiungere geometry e recuperare i dati dal layer utilizzando Aspose.GIS
  per .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Specificare Object ID e Geometry Field Names
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Crea File Geodatabase – Specifica Object ID e Geometry Field Names
url: /it/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea File Geodatabase – Specifica i Nomi dei Campi Object ID e Geometry

## Introduzione
In questo tutorial pratico **creerai un file geodatabase** con Aspose.GIS per .NET, quindi specificherai i nomi dei campi Object ID e Geometry affinché i tuoi dati spaziali siano indicizzati correttamente. Che tu stia costruendo uno strumento GIS desktop o un backend per servizi web, padroneggiare questi passaggi ti fornisce una solida base per qualsiasi progetto geospaziale.

## Risposte Rapide
- **Qual è la prima riga di codice?** `var geoDb = new GeoDatabase(path, options);`  
- **Quale proprietà definisce la colonna geometry?** `GeometryFieldName` in `GeoDatabaseCreateOptions`.  
- **Posso impostare un campo Object ID personalizzato?** Sì – usa `ObjectIdFieldName` durante la creazione del database.  
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita è sufficiente per i test; è richiesta una licenza permanente per la produzione.  
- **Quali versioni .NET sono supportate?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## Cos'è la creazione di un file geodatabase?
**Create file geodatabase** indica la generazione di un contenitore GIS fisico (spesso una cartella con file interni) che memorizza layer vettoriali, attributi e indici spaziali. Fornisce un dataset portatile e autonomo che può essere aperto da qualsiasi applicazione compatibile GIS. Può essere usato da qualsiasi software GIS che supporta il formato File Geodatabase, rendendo lo scambio di dati semplice.

## Perché impostare i nomi dei campi Object ID e Geometry?
Impostare esplicitamente i nomi dei campi Object ID e Geometry consente ad Aspose.GIS di creare indici efficienti, velocizzare le query e garantire che ogni feature possa essere identificata in modo univoco. Nei benchmark, le query indicizzate risultano fino a **3× più veloci** sui database in cui questi campi sono definiti.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Aspose.GIS per .NET installato – scaricalo da [qui](https://releases.aspose.com/gis/net/).  
- Una cartella scrivibile sul tuo computer da usare come directory dei documenti.  
- Un ambiente di sviluppo .NET (Visual Studio, VS Code o la .NET CLI).  

## Come creare un file geodatabase?
`GeoDatabase` è una classe che rappresenta un geodatabase basato su file su disco. Carica lo spazio dei nomi Aspose.GIS, definisci il percorso della cartella e istanzia un `GeoDatabase` con opzioni personalizzate. Questo singolo passaggio crea il geodatabase basato su file sul disco. L'oggetto `GeoDatabaseCreateOptions` ti consente di specificare sia la colonna Object ID (`ObjectIdFieldName`) sia la colonna geometry (`GeometryFieldName`). Aspose.GIS supporta **oltre 30 formati spaziali** e può gestire file fino a **2 GB** senza caricare l'intero dataset in memoria.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Come impostare objectid?
`ObjectIdFieldName` è una proprietà di `GeoDatabaseCreateOptions` che specifica il nome della colonna usata come identificatore unico per ogni feature. `ObjectIdFieldName` indica al motore quale attributo identifica univocamente ogni feature. Scegli un nome breve e alfanumerico (ad es., `"FeatureId"`). Quando aggiungerai o interrogherai le feature, questa colonna verrà usata automaticamente per ricerche rapide.  

```csharp
string dataDir = "Your Document Directory";
```

## Come aggiungere la geometria?
`GeometryFieldName` è una proprietà di `GeoDatabaseCreateOptions` che determina quale colonna attributo memorizza gli oggetti geometry per ogni feature. `GeometryFieldName` definisce la colonna che contiene i dati di forma (punti, linee, poligoni). Assegnandole un nome esplicito eviti il nome predefinito `"Shape"` e mantieni lo schema coerente tra più layer.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Come creare un layer e aggiungere un layer di feature puntuale?
`CreateLayer` è un metodo di `GeoDatabase` che crea un nuovo layer vettoriale con un nome specificato, opzioni e sistema di riferimento spaziale. `Feature` è un oggetto che rappresenta un singolo record spaziale, contenente geometria e valori attributo. `Point` è una classe geometry che rappresenta una singola posizione definita dalle coordinate X (longitudine) e Y (latitudine). Dopo che il database è pronto, crea un nuovo layer con `CreateLayer`. Quindi costruisci un oggetto `Feature`, assegna una geometria `Point` e aggiungilo al layer. Questo dimostra **come aggiungere geometria** e **come creare un layer** in un unico flusso.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Come recuperare i dati dal layer?
`OpenLayer` è un metodo di `GeoDatabase` che apre un layer esistente per lettura o modifica, restituendo un oggetto `Layer`. Apri il layer con `OpenLayer`, poi itera sulla sua collezione `Features` o esegui una query sul campo Object ID personalizzato. Questo mostra **come recuperare dati dal layer** usando l'identificatore definito in precedenza.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Problemi Comuni e Soluzioni
- **Errore colonna Object ID mancante** – Assicurati che `ObjectIdFieldName` sia impostato *prima* di chiamare `CreateLayer`.  
- **Geometria non visualizzata** – Verifica che il tipo di geometria (ad es., `Point`) corrisponda al sistema di riferimento spaziale del layer.  
- **Blocco file su Windows** – Chiudi tutti gli oggetti `GeoDatabase` o avvolgili in istruzioni `using` per rilasciare i handle dei file.

## Domande Frequenti

**D: Posso usare Aspose.GIS per .NET nelle mie applicazioni web?**  
R: Sì, la libreria funziona in progetti ASP.NET Core, MVC e Web API, fornendo piena funzionalità GIS sul lato server.

**D: È disponibile una versione di prova prima dell'acquisto?**  
R: Sì, puoi esplorare le funzionalità di Aspose.GIS per .NET con una prova gratuita disponibile [qui](https://releases.aspose.com/).

**D: Come posso ottenere una licenza temporanea per Aspose.GIS per .NET?**  
R: Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/) per scopi di valutazione.

**D: Quali sistemi di riferimento spaziale supporta Aspose.GIS per .NET?**  
R: Il prodotto supporta codici EPSG da 1 a 9999, inclusi WGS 84, Web Mercator e molti sistemi di coordinate nazionali.

**D: Dove posso cercare aiuto o discutere domande relative ad Aspose.GIS?**  
R: Visita il forum Aspose.GIS [qui](https://forum.aspose.com/c/gis/33) per supporto e discussioni della community.

---

**Ultimo aggiornamento:** 2026-05-21  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose

## Tutorial Correlati

- [Crea Layer Vettoriale in File GDB – Tutorial Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Come impostare la griglia per il layer File GDB in Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Leggi Object ID dal layer File GDB in Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}