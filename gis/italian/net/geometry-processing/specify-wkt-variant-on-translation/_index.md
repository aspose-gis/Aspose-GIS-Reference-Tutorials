---
date: 2026-09-15
description: Scopri come assegnare il sistema di coordinate, impostare la variante
  WKT e controllare la precisione decimale quando si crea una geometria punto in C#
  con Aspose.GIS per .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: Specifica la variante WKT nella traduzione
og_description: Scopri come assegnare il sistema di coordinate, impostare la variante
  WKT e controllare la precisione decimale quando si crea una geometria punto in C#
  con Aspose.GIS per .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Assegna il sistema di coordinate, imposta la variante WKT usando Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Assegna il sistema di coordinate, imposta la variante WKT usando Aspose.GIS
url: /it/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Assegna sistema di coordinate, imposta variante WKT usando Aspose.GIS

## Introduzione
In questo tutorial imparerai a **assegnare il sistema di coordinate**, scegliere la variante WKT corretta e controllare la precisione decimale quando **crei geometrie di tipo punto** in C# con Aspose.GIS per .NET. Che tu stia costruendo un servizio di mappatura, eseguendo analisi spaziali o scambiando dati tra piattaforme GIS, queste impostazioni garantiscono che il tuo output sia sia interoperabile sia leggibile. Procediamo passo dopo passo.

## Risposte rapide
- **Cosa significa “assegnare il sistema di coordinate”?** Associa una geometria a un sistema di riferimento di coordinate specifico, come WGS‑84.  
- **Quali varianti WKT sono supportate?** Iso, SimpleFeatureAccessOutdated e ExtendedPostGis.  
- **Come posso controllare la precisione decimale?** Usa l’enumerazione `NumericFormat` (`General`, `RoundTrip`, `Flat`).  
- **È necessaria una licenza per Aspose.GIS?** È disponibile una versione di prova gratuita; per l’uso in produzione è richiesta una licenza commerciale.  
- **Quali versioni di .NET sono compatibili?** .NET Framework 4.0+ e .NET Core/5/6+.

## Cos’è “assegnare il sistema di coordinate”?
Assegnare un riferimento spaziale (o sistema di riferimento spaziale, SRS) indica al software GIS come interpretare i valori di coordinate di una geometria, collegando i numeri a un sistema di coordinate reale come WGS‑84. Senza un SRS, i numeri di latitudine‑longitudine di un punto non hanno alcun significato nel mondo reale.

## Perché controllare la variante WKT e il formato numerico?
Oltre 30 strumenti GIS si aspettano sintassi WKT specifiche, quindi selezionare la variante corretta evita errori di importazione. Impostare il formato numerico riduce il rumore di arrotondamento e mantiene l’output conciso, aspetto particolarmente importante quando log o file vengono analizzati programmaticamente.

## Prerequisiti
1. Aspose.GIS per .NET – scarica dalla [pagina di download](https://releases.aspose.com/gis/net/).  
2. Un ambiente di sviluppo .NET (Visual Studio, VS Code o Rider).  
3. Familiarità di base con C# e il framework .NET.

## Importa gli spazi dei nomi
Prima di utilizzare qualsiasi classe Aspose.GIS, importa gli spazi dei nomi richiesti:

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Come assegnare il sistema di coordinate a un punto?
Carica un'istanza `Point`, quindi collega un sistema di riferimento spaziale (SRS) usando la classe `SpatialReference`. Questo schema a due passaggi garantisce che la geometria trasporti i metadati del suo sistema di coordinate quando viene esportata, permettendo agli strumenti a valle di interpretare correttamente le coordinate. La classe `Point` rappresenta una singola posizione definita dalle coordinate X (longitudine) e Y (latitudine).

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Passo 2: assegna il sistema di riferimento spaziale (SRS)
Ora **assegniamo il riferimento spaziale** al punto. `SpatialReference` rappresenta un sistema di riferimento di coordinate identificato da un SRID. Qui utilizziamo il sistema ampiamente supportato WGS‑84 (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Passo 3: specifica la variante WKT desiderata
Scegli la variante WKT che corrisponde alla tua applicazione a valle:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Come impostare la precisione decimale per l’output WKT?
Controlla quante cifre appaiono nella stringa finale usando l’enumerazione `NumericFormat`, che definisce regole di formattazione come `General`, `RoundTrip` o `Flat`. Selezionare `RoundTrip` preserva la fedeltà completa delle coordinate per scenari di round‑tripping, mentre `General` fornisce una rappresentazione concisa adatta alla maggior parte dei compiti di visualizzazione. L’enumerazione `NumericFormat` controlla come i numeri delle coordinate vengono formattati nell’output WKT.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Problemi comuni e consigli
- **Problema:** Dimenticare di impostare il SRS prima di chiamare `AsText` può causare la perdita delle informazioni SRID.  
- **Consiglio:** Usa `NumericFormat.RoundTrip` quando hai bisogno di un round‑tripping senza perdita di coordinate.  
- **Consiglio:** La variante `Iso` è la più portabile; scegli `ExtendedPostGis` solo quando è necessario incorporare l’S RID.

## Conclusione
Ora sai come **assegnare il sistema di coordinate**, scegliere la variante WKT appropriata e **impostare la precisione decimale** quando **crei geometrie di tipo punto** con Aspose.GIS. Questi controlli ti offrono la flessibilità necessaria per soddisfare i requisiti esatti di qualsiasi flusso di lavoro GIS, dalla semplice visualizzazione all’analisi spaziale ad alta precisione.

## Domande frequenti

**D:** Aspose.GIS è compatibile con tutte le versioni di .NET?  
**R:** Sì, Aspose.GIS supporta .NET Framework 4.0 e versioni successive, così come .NET Core/5/6.

**D:** Posso usare Aspose.GIS per progetti commerciali?  
**R:** Assolutamente. È necessaria una licenza commerciale per l’uso in produzione, ma è disponibile una versione di prova gratuita per la valutazione.

**D:** Aspose.GIS supporta altri formati di dati spaziali?  
**R:** Sì, funziona con oltre 30 formati, inclusi ESRI Shapefile, GeoJSON, KML, CSV e molti altri.

**D:** Dove posso scaricare una versione di prova gratuita?  
**R:** Puoi scaricare una versione di prova gratuita di Aspose.GIS dalla [pagina di download della prova gratuita di Aspose.GIS](https://releases.aspose.com/).

**D:** Come posso ottenere supporto se incontro problemi?  
**R:** Pubblica le tue domande sul [forum della community Aspose.GIS](https://forum.aspose.com/c/gis/33) dove sia lo staff di Aspose sia i membri della community possono assisterti.

---

**Ultimo aggiornamento:** 2026-09-15  
**Testato con:** Aspose.GIS per .NET (ultima release)  
**Autore:** Aspose

## Tutorial correlati

- [Create a Vector Layer and Set Its Spatial Reference System](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [How to Translate Geometry to WKT with Aspose.GIS for .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [How to Limit Precision Writing Geometries with Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}