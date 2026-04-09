---
date: 2026-04-09
description: Scopri come assegnare il riferimento spaziale e impostare la precisione
  decimale quando crei un punto C# con Aspose.GIS per .NET nelle tue applicazioni
  .NET.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: Specifica variante WKT nella traduzione
second_title: Aspose.GIS .NET API
title: Assegna riferimento spaziale e imposta variante WKT usando Aspose.GIS
url: /it/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Assegna riferimento spaziale e imposta variante WKT usando Aspose.GIS

## Introduzione
In questo tutorial imparerai come **assegnare il riferimento spaziale** a una geometria e controllare il formato di output WKT esatto con Aspose.GIS per .NET. Che tu abbia bisogno di **creare point C#** oggetti per la mappatura, l'analisi o lo scambio di dati, la possibilità di scegliere la variante WKT corretta e la precisione numerica rende i tuoi dati spaziali interoperabili e facili da leggere. Procediamo passo passo attraverso il processo.

## Risposte rapide
- **Che cosa significa “assign spatial reference”?** Associa una geometria a un sistema di coordinate specifico come WGS‑84.  
- **Quali varianti WKT sono supportate?** Iso, SimpleFeatureAccessOutdated e ExtendedPostGis.  
- **Come posso controllare la precisione decimale?** Usa le opzioni `NumericFormat` come `General`, `RoundTrip` o `Flat`.  
- **È necessaria una licenza?** È disponibile una versione di prova gratuita; è richiesta una licenza commerciale per la produzione.  
- **Quali versioni di .NET sono compatibili?** .NET Framework 4.0+ e .NET Core/5/6+.

## Cos'è “assign spatial reference”?
Assegnare un riferimento spaziale (o sistema di riferimento spaziale, SRS) indica al software GIS come interpretare i valori di coordinate di una geometria. Senza un SRS, i numeri di latitudine‑longitudine di un punto non hanno alcun significato nel mondo reale.

## Perché controllare la variante WKT e il formato numerico?
Diversi strumenti GIS si aspettano sintassi WKT leggermente diverse. Selezionare la variante corretta garantisce uno scambio di dati senza interruzioni, mentre impostare la precisione decimale previene errori di arrotondamento o numeri eccessivamente lunghi che ingombrano i log e i file.

## Prerequisiti
1. Aspose.GIS per .NET – scarica dalla [pagina di download](https://releases.aspose.com/gis/net/).  
2. Un ambiente di sviluppo .NET (Visual Studio, VS Code o Rider).  
3. Familiarità di base con C# e il framework .NET.

## Importa spazi dei nomi
Before using any Aspose.GIS classes, import the required namespaces:

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

## Passo 1: Crea un oggetto Point (creare point C#)
Iniziamo costruendo un `Point` con latitudine, longitudine e un valore di misura (M) opzionale:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Passo 2: Assegna il sistema di riferimento spaziale (SRS)
Ora **assegniamo il riferimento spaziale** al punto. Qui utilizziamo il sistema WGS‑84 ampiamente supportato (SRID 4326):

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Passo 3: Specifica la variante WKT desiderata
Scegli la variante WKT che corrisponde alla tua applicazione downstream:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Passo 4: Imposta la precisione decimale per l'output WKT
Controlla quante cifre appaiono nella stringa finale usando `NumericFormat`:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Problemi comuni e consigli
- **Problema:** Dimenticare di impostare il SRS prima di chiamare `AsText` può causare la mancanza di informazioni SRID.  
- **Consiglio:** Usa `NumericFormat.RoundTrip` quando hai bisogno di un round‑trip senza perdita di coordinate.  
- **Consiglio:** La variante `Iso` è la più portabile; scegli `ExtendedPostGis` solo quando hai bisogno di SRID incorporato.

## Conclusione
Ora sai come **assegnare il riferimento spaziale**, scegliere la variante WKT appropriata e **impostare la precisione decimale** quando **crei point C#** oggetti con Aspose.GIS. questi controlli ti offrono la flessibilità per soddisfare i requisiti esatti di qualsiasi flusso di lavoro GIS, dalla visualizzazione semplice all'analisi spaziale ad alta precisione.

## Domande frequenti

**Q:** Aspose.GIS è compatibile con tutte le versioni di .NET?  
**A:** Sì, Aspose.GIS supporta .NET Framework 4.0 e versioni successive, così come .NET Core/5/6.

**Q:** Posso usare Aspose.GIS per progetti commerciali?  
**A:** Assolutamente. È necessaria una licenza commerciale per l'uso in produzione, ma è disponibile una versione di prova gratuita per la valutazione.

**Q:** Aspose.GIS supporta altri formati di dati spaziali?  
**A:** Sì, funziona con ESRI Shapefile, GeoJSON, KML e molti altri formati.

**Q:** Dove posso scaricare una versione di prova gratuita?  
**A:** Puoi scaricare una versione di prova gratuita di Aspose.GIS da [qui](https://releases.aspose.com/).

**Q:** Come posso ottenere assistenza se incontro problemi?  
**A:** Pubblica le tue domande sul [forum](https://forum.aspose.com/c/gis/33) della community Aspose.GIS, dove sia lo staff di Aspose sia i membri della community possono aiutare.

---

**Ultimo aggiornamento:** 2026-04-09  
**Testato con:** Aspose.GIS for .NET (latest release)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}