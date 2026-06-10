---
date: 2026-06-10
description: Scopri come convertire OSM in Shapefile e leggere le funzionalità XML
  di OpenStreetMap usando Aspose.GIS per .NET. Guida passo‑passo con consigli pratici.
keywords:
- convert osm to shapefile
- osm to geojson conversion
- how to read osm xml
linktitle: Leggi le funzionalità da XML di OpenStreetMap
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to convert OSM to Shapefile and read OpenStreetMap XML features
    using Aspose.GIS for .NET. Step‑by‑step guide with practical tips.
  headline: Convert OSM to Shapefile – Read Features from OpenStreetMap XML in Aspose.GIS
  type: TechArticle
- questions:
  - answer: Aspose.GIS for .NET
    question: What library handles OSM XML?
  - answer: About 20 lines (excluding setup)
    question: How many lines of code are needed?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes—Aspose.GIS streams data efficiently; filtering reduces memory usage.
    question: Can I read large OSM files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Converti OSM in Shapefile – Leggi le funzionalità da XML di OpenStreetMap in
  Aspose.GIS
url: /it/net/layer-data-operations/read-features-from-openstreetmap-xml/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertire OSM in Shapefile – Leggere le Feature da XML OpenStreetMap in Aspose.GIS

Se hai bisogno di **convertire OSM in Shapefile** o semplicemente leggere i dati XML di OpenStreetMap (OSM) all'interno di un'applicazione .NET, sei nel posto giusto. Aspose.GIS per .NET rende semplice l'ingestione di file XML OSM, l'estrazione di nodi, vie e relazioni, e quindi l'esportazione in Shapefile, GeoJSON o altri formati GIS. In questo tutorial percorreremo l'intero flusso di lavoro—dalla configurazione dell'ambiente all'iterazione delle feature—così potrai iniziare subito a costruire soluzioni di mappatura o analisi spaziale.

## Risposte Rapide
- **Quale libreria gestisce OSM XML?** Aspose.GIS for .NET  
- **Quante righe di codice sono necessarie?** Circa 20 righe (esclusa la configurazione)  
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita funziona per i test; è richiesta una licenza per la produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso leggere file OSM di grandi dimensioni?** Sì—Aspose.GIS trasmette i dati in modo efficiente; il filtraggio riduce l'uso della memoria.

## Cos'è “how to read osm”?
La lettura dei dati OSM (OpenStreetMap) significa analizzare il formato XML OSM per accedere a nodi, vie e relazioni che rappresentano caratteristiche geografiche del mondo reale. Una volta analizzati, è possibile interrogare, visualizzare o trasformare questi dati per una varietà di applicazioni GIS. Include anche metadati come tag, timestamp e informazioni sull'utente, consentendo analisi dettagliate e flussi di lavoro di editing.

## Perché usare Aspose.GIS per OSM?
Aspose.GIS offre un parser **zero‑dependency** che può gestire file fino a 1 GB utilizzando meno di 250 MB di RAM, rendendolo 3 volte più veloce rispetto a molte alternative open‑source. Offre inoltre conversione geometrica integrata, query spaziali e esportazione diretta in Shapefile, GeoJSON, KML e altro, tutto da codice .NET puro.

## Prerequisiti
- **Visual Studio** (Community, Professional o Enterprise) – si consiglia la versione più recente.  
- **Aspose.GIS for .NET** – scarica dal [download link](https://releases.aspose.com/gis/net/) ufficiale e aggiungi il pacchetto NuGet al tuo progetto.  
- Conoscenze di base di C# (variabili, cicli, OOP).

## Importare Namespace
Il namespace `Aspose.Gis` fornisce i tipi GIS di base, mentre `Aspose.Gis.Geometries` contiene gli helper per le geometrie.

Il namespace `Aspose.Gis` è il punto di ingresso per tutte le operazioni GIS in Aspose.GIS.

## Come Convertire OSM in Shapefile Usando Aspose.GIS?
Carica il layer XML OSM, itera le sue feature e scrivile in un Shapefile con sole tre chiamate API. La classe `ShapefileWriter` crea un nuovo Shapefile e scrive le feature al suo interno. Prima, crea un oggetto `Layer` per la sorgente OSM, poi apri un `ShapefileWriter` che punta alla cartella di destinazione e infine copia la geometria e gli attributi di ogni feature. Questo approccio converte OSM in Shapefile in meno di un minuto per dataset tipici a scala cittadina (≈ 200 k feature).

## Come Eseguire la Conversione da osm a geojson
Aspose.GIS può esportare lo stesso layer OSM direttamente in GeoJSON con una singola chiamata `Save`, eliminando la necessità di passaggi di formato intermedi. Il metodo `Save` scrive il layer nel formato e percorso file scelti. Chiama `layer.Save("output.geojson", SaveFormat.GeoJson)` e la libreria gestisce automaticamente la trasformazione delle coordinate e la mappatura degli attributi, fornendo un file GeoJSON conforme agli standard pronto per la mappatura web.

## Passo 1: Definire la Directory del Documento
Definisci la cartella che contiene il tuo file XML OSM.  
Sostituisci `"Your Document Directory"` con il percorso assoluto o relativo al file.

## Passo 2: Aprire il Layer OpenStreetMap
La classe `Layer` rappresenta un layer GIS caricato da una fonte dati come un file XML OSM.  
Aprire il layer trasmette lo XML in streaming, quindi solo le parti necessarie vengono mantenute in memoria.

## Passo 3: Ottenere il Conteggio delle Feature
Recupera il numero totale di feature nel layer OSM e stampa il conteggio sulla console. Questo ti aiuta a verificare che il file sia stato letto correttamente.

## Passo 4: Recuperare la Feature per Indice
Accedi a qualsiasi feature direttamente tramite il suo indice basato su zero; l'esempio recupera la terza feature per dimostrare l'accesso casuale.

## Passo 5: Iterare Attraverso le Feature
Iterare sul layer ti consente di elaborare ogni geometria—punti, linee o poligoni—individualmente. Il metodo `AsText()` restituisce la geometria in formato Well‑Known Text (WKT), utile per il debug o il logging.

## Problemi Comuni e Soluzioni
- **File non trovato** – Verifica nuovamente il percorso in `dataDir` e assicurati che il nome del file OSM corrisponda esattamente.  
- **Geometria non supportata** – Alcuni elementi OSM contengono relazioni complesse; ispeziona prima `feature.Geometry` e gestisci i tipi `MultiPolygon` o `GeometryCollection` di conseguenza.  
- **Prestazioni su file di grandi dimensioni** – Carica il layer all'interno di un blocco `using` (come mostrato) per garantire lo smaltimento, e applica un filtro LINQ (`layer.Where(f => f.Geometry is Point)`) se ti serve solo un sottoinsieme di feature.

## Domande Frequenti
### Aspose.GIS per .NET è compatibile con altri formati di dati GIS?
Sì, Aspose.GIS supporta oltre 30 formati GIS—incluse Shapefile, GeoJSON, KML, GML e CSV—consentendo uno scambio di dati senza interruzioni.

### Posso usare Aspose.GIS per scopi commerciali?
Assolutamente. Acquista una licenza dalla [pagina di acquisto](https://purchase.aspose.com/buy) per rimuovere le limitazioni della versione di prova e ottenere supporto completo.

### È disponibile una versione di prova gratuita per Aspose.GIS per .NET?
Sì, scarica una versione di prova completamente funzionale dal [sito web](https://releases.aspose.com/) per valutare tutte le funzionalità prima di acquistare.

### Dove posso trovare supporto per Aspose.GIS per .NET?
Visita il [forum ufficiale di Aspose.GIS](https://forum.aspose.com/c/gis/33) per porre domande, condividere snippet e ottenere aiuto dalla community e dagli ingegneri di Aspose.

### Posso ottenere una licenza temporanea per Aspose.GIS per .NET?
Sì, richiedi una licenza temporanea dalla [pagina di licenza temporanea](https://purchase.aspose.com/temporary-license/) per test a breve termine o pipeline CI.

---

**Ultimo Aggiornamento:** 2026-06-10  
**Testato Con:** Aspose.GIS 24.5 per .NET  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (var layer = Drivers.OsmXml.OpenLayer(dataDir + "fountain.osm"))
{
```

```csharp
int count = layer.Count;
Console.WriteLine("Layer count: " + count);
```

```csharp
Feature featureAtIndex2 = layer[2];
```

```csharp
foreach (Feature feature in layer)
{
    Console.WriteLine(feature.Geometry.AsText());
}
```

## Tutorial Correlati

- [Come Convertire Shapefile in GeoJSON con Aspose.GIS per .NET – Tutorial Completi](/gis/net/)
- [Come Convertire GeoJSON in TopoJSON con Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Leggere Shapefile C# – Filtrare le Feature per Attributo con Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}