---
date: 2026-06-10
description: Scopri come creare geometria linestring in .NET e convertire la geometria
  in WKB usando Aspose.GIS per .NET con la variante ExtendedPostGis.
keywords:
- create linestring geometry .net
- WKB variant Aspose GIS
- EWKB conversion .NET
linktitle: Specifica la variante WKB nella traduzione
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  headline: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to create linestring geometry .NET and convert geometry to
    WKB using Aspose.GIS for .NET with the ExtendedPostGis variant.
  name: Create Linestring Geometry & WKB Variant in Aspose.GIS for .NET
  steps:
  - name: Creating a Geometry Object
    text: The `Geometry` class is Aspose.GIS's base type that represents any spatial
      object in memory. Linestring represents a series of connected points forming
      a linear geometry. In this step we instantiate a `Linestring` with a collection
      of coordinate pairs that model a simple road segment.
  - name: Generating WKB Representation
    text: '`WkbVariant.ExtendedPostGis` is the enum value that tells Aspose.GIS to
      include SRID in the output binary. Here we call the `AsBinary` method, passing
      the EWKB variant, which returns a `byte[]` containing the full binary representation.'
  - name: Writing to File
    text: '`File.WriteAllBytes` writes the binary array to disk. The resulting file
      (`EWkbFile.ewkb`) can be imported directly into a PostGIS table using the `ST_GeomFromEWKB`
      function.'
  type: HowTo
- questions:
  - answer: Yes, the `ExtendedPostGis` variant produces EWKB that includes SRID, which
      PostGIS reads directly via `ST_GeomFromEWKB`.
    question: Can I use the EWKB file with PostGIS?
  - answer: Absolutely. Use `Geometry.FromBinary(byteArray)` to reconstruct the geometry
      from its binary form.
    question: Is it possible to read a WKB file back into a geometry object?
  - answer: Yes, Aspose.GIS handles points, linestrings, polygons, multipolygons,
      and many more spatial types.
    question: Does the library support other geometry types like polygons?
  - answer: Set the `SRID` property on the geometry object before calling `AsBinary`,
      e.g., `linestring.SRID = 4326;`.
    question: How do I specify a different SRID when creating the geometry?
  - answer: Yes, the same API works across .NET Framework, .NET Core, and .NET 5/6
      without modification.
    question: Will this code work on .NET Core?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Crea geometria Linestring e variante WKB in Aspose.GIS per .NET
url: /it/net/geometry-processing/specify-wkb-variant-on-translation/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea geometria Linestring e variante WKB in Aspose.GIS per .NET

## Introduzione
Se hai bisogno di **creare geometria linestring .NET** e poi tradurre quella geometria in una forma binaria, Aspose.GIS per .NET ti offre un'API pulita e ad alte prestazioni che funziona su .NET Framework, .NET Core e .NET 5/6+. In questo tutorial percorreremo ogni passaggio—dall'importazione degli spazi dei nomi alla scrittura di un file EWKB—così potrai preservare le informazioni SRID e integrare i dati GIS in PostgreSQL/PostGIS o in qualsiasi flusso di lavoro basato su binari senza problemi.

## Risposte rapide
- **Cosa significa WKB?** Well‑Known Binary, una rappresentazione binaria compatta di oggetti geometrici.  
- **Quale variante WKB memorizza l'SRID?** La variante `ExtendedPostGis` (EWKB) incorpora l'SRID direttamente nel binario.  
- **È necessaria una licenza?** È richiesta una licenza temporanea o completa di Aspose.GIS per le distribuzioni in produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6+.  
- **Quanto tempo richiede l'implementazione?** Tipicamente meno di 10 minuti per un esempio di base.

## Cos'è una geometria Linestring?
Una geometria linestring è una forma semplice costituita da un elenco ordinato di punti collegati da segmenti di linea retti. È la rappresentazione di riferimento per caratteristiche lineari come strade, condutture o percorsi fluviali nei database spaziali.

## Perché specificare una variante WKB?
Utilizzare la variante WKB corretta garantisce che i metadati critici—soprattutto l'Identificatore del Sistema di Riferimento Spaziale (SRID)—viaggino con la tua geometria. La variante `ExtendedPostGis` (EWKB) memorizza l'SRID all'interno del payload binario, consentendo un round‑tripping senza soluzione di continuità con PostGIS, Oracle Spatial o qualsiasi sistema che si aspetti binari consapevoli dell'SRID.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

### Installazione di Aspose.GIS per .NET
1. Scarica Aspose.GIS: visita il [download link](https://releases.aspose.com/gis/net/) per ottenere l'ultimo pacchetto.  
2. Aggiungi il pacchetto NuGet al tuo progetto (ad es., `Install-Package Aspose.GIS`).  

### Familiarità con la programmazione C#
- Comprensione di base della sintassi C# e della struttura del progetto.  
- Capacità di eseguire un progetto console .NET o una libreria di classi.

## Importa spazi dei nomi
Lo spazio dei nomi `Aspose.GIS` ti dà accesso a tutte le classi relative alla geometria.  

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Questi spazi dei nomi forniscono la funzionalità GIS di base, inclusa la creazione di geometrie, la trasformazione e la serializzazione binaria.

## Come creare una geometria linestring?
Per creare una linestring, istanzia un oggetto `Linestring` con un elenco ordinato di coppie di coordinate, imposta il suo SRID se necessario, e poi serializzalo nella variante WKB desiderata. Il processo comprende tre passaggi: costruire la geometria, scegliere la variante `ExtendedPostGis` per mantenere l'SRID e scrivere l'array di byte risultante su file.

### Passo 1: Creazione di un oggetto Geometry
La classe `Geometry` è il tipo base di Aspose.GIS che rappresenta qualsiasi oggetto spaziale in memoria.  
Linestring rappresenta una serie di punti connessi che formano una geometria lineare.  

```csharp
IGeometry geometry = Geometry.FromText("LINESTRING (1.2 3.4, 5.6 7.8)");
```
In questo passaggio istanziamo un `Linestring` con una collezione di coppie di coordinate che modellano un semplice tratto stradale.

### Passo 2: Generazione della rappresentazione WKB
`WkbVariant.ExtendedPostGis` è il valore enum che indica ad Aspose.GIS di includere l'SRID nel binario di output.  

```csharp
byte[] wkb = geometry.AsBinary(WkbVariant.ExtendedPostGis);
```
Qui chiamiamo il metodo `AsBinary`, passando la variante EWKB, che restituisce un `byte[]` contenente la rappresentazione binaria completa.

### Passo 3: Scrittura su file
`File.WriteAllBytes` scrive l'array binario su disco.  

```csharp
File.WriteAllBytes(Path.Combine("Your Document Directory", "EWkbFile.ewkb"), wkb);
```
Il file risultante (`EWkbFile.ewkb`) può essere importato direttamente in una tabella PostGIS usando la funzione `ST_GeomFromEWKB`.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **File vuoto** | `Path.Combine` punta a una directory inesistente. | Assicurati che la directory di destinazione esista o creala con `Directory.CreateDirectory`. |
| **SRID errato** | L'uso del valore predefinito `WkbVariant.Standard` elimina l'SRID. | Usa sempre `WkbVariant.ExtendedPostGis` quando è necessaria la conservazione dell'SRID. |
| **Eccezione di licenza** | Esecuzione senza licenza valida in produzione. | Applica una licenza temporanea o completa prima di eseguire il codice in ambiente di produzione. |

## Domande frequenti
**Q: Posso usare il file EWKB con PostGIS?**  
A: Sì, la variante `ExtendedPostGis` produce EWKB che include l'SRID, che PostGIS legge direttamente tramite `ST_GeomFromEWKB`.  

**Q: È possibile leggere un file WKB e ricreare l'oggetto geometria?**  
A: Assolutamente. Usa `Geometry.FromBinary(byteArray)` per ricostruire la geometria dalla sua forma binaria.  

**Q: La libreria supporta altri tipi di geometria come i poligoni?**  
A: Sì, Aspose.GIS gestisce punti, linestrings, poligoni, multipoligoni e molti altri tipi spaziali.  

**Q: Come specificare un SRID diverso quando creo la geometria?**  
A: Imposta la proprietà `SRID` sull'oggetto geometria prima di chiamare `AsBinary`, ad esempio `linestring.SRID = 4326;`.  

**Q: Questo codice funziona su .NET Core?**  
A: Sì, la stessa API funziona su .NET Framework, .NET Core e .NET 5/6 senza modifiche.

---

**Ultimo aggiornamento:** 2026-06-10  
**Testato con:** Aspose.GIS per .NET 23.9 (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Tradurre la geometria in formato WKB con Aspose.GIS per .NET](/gis/net/geometry-processing/translate-geometry-to-wkb/)
- [Specificare la variante WKT durante la traduzione usando Aspose.GIS](/gis/net/geometry-processing/specify-wkt-variant-on-translation/)
- [Creare geometria MultiLineString usando Aspose.GIS per .NET](/gis/net/geometry-creation/create-multilinestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}