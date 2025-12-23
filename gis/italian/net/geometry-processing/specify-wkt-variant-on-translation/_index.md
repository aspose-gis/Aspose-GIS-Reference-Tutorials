---
date: 2025-12-23
description: Scopri come convertire la geometria in WKT con opzioni varianti, impostare
  il formato numerico e regolare la precisione decimale utilizzando Aspose.GIS per
  .NET.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Converti la geometria in opzioni di variante WKT usando Aspose.GIS
url: /it/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti la geometria in opzioni di variante WKT usando Aspose.GIS

## Introduzione
Nelle moderne applicazioni .NET, **convertire la geometria in WKT** è un passaggio comune quando è necessario scambiare dati spaziali con altri sistemi o archiviarli in un formato basato su testo. Aspose.GIS per .NET rende questa conversione senza sforzo fornendo il pieno controllo sulla variante WKT, sul formato numerico e sulla precisione decimale. In questo tutorial imparerai come convertire la geometria in WKT, scegliere la variante corretta e perfezionare l'output per soddisfare i requisiti esatti del tuo progetto.

## Risposte rapide
- **Cosa significa “convertire la geometria in WKT”?** Trasforma gli oggetti geometrici (punti, linee, poligoni) nella rappresentazione Well‑Known Text.  
- **Quali varianti WKT sono supportate?** `Iso`, `SimpleFeatureAccessOutdated` e `ExtendedPostGis`.  
- **Come posso controllare la precisione decimale?** Usa le opzioni `NumericFormat` come `General`, `RoundTrip` o `Flat`.  
- **È necessaria una licenza per la produzione?** Sì, è richiesta una licenza commerciale per l'uso non‑trial.  
- **Quali versioni di .NET sono compatibili?** .NET Framework 4.0+ e .NET 5/6/7.

## Cos'è “convertire la geometria in WKT”?
Convertire la geometria in WKT produce una stringa leggibile dall'uomo che descrive gli oggetti spaziali. Questo formato è ampiamente accettato da strumenti GIS, database e servizi web, rendendolo ideale per lo scambio di dati.

## Perché usare Aspose.GIS per questa conversione?
- **Controllo della precisione** – Scegli quante cifre decimali emettere.  
- **Flessibilità della variante** – Corrispondi al dialetto WKT esatto richiesto dal tuo sistema a valle.  
- **Nessuna dipendenza esterna** – Libreria .NET pura, senza binari nativi.

## Prerequisiti
1. **Aspose.GIS for .NET** – Scaricalo e installalo dalla [pagina di download](https://releases.aspose.com/gis/net/).  
2. **Ambiente di sviluppo** – Qualsiasi versione recente di Visual Studio o VS Code con .NET SDK.  
3. **Conoscenza base di C#** – Familiarità con classi, oggetti e il framework .NET.

## Importa gli spazi dei nomi
Per prima cosa, porta gli spazi dei nomi richiesti nello scope:

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

## Passo 1: Crea un oggetto Point
Crea un `Point` che in seguito **convertirai in WKT**. Il punto include latitudine, longitudine e un valore di misura (M) opzionale:

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Passo 2: Imposta il Sistema di Riferimento Spaziale (SRS)
Assegna un sistema di riferimento spaziale affinché l'output WKT sappia a quale sistema di coordinate fare riferimento. Qui usiamo il comune sistema WGS84:

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Passo 3: Specifica la variante WKT
Scegli la variante WKT appropriata quando **converti la geometria in WKT**. Ogni variante formatta l'output in modo leggermente diverso:

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Passo 4: Controlla il formato numerico (Imposta il formato numerico e regola la precisione decimale)
Affina la rappresentazione numerica delle coordinate. La classe `NumericFormat` ti consente di **impostare il formato numerico** e **regolare la precisione decimale** secondo le tue esigenze:

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Problemi comuni e consigli
- **Valore M mancante** – Se non ti serve una misura, ometti la proprietà `M`; la variante ISO la rimuoverà automaticamente.  
- **Precisione inattesa** – Verifica di utilizzare il `NumericFormat` corretto; `General` conserva la piena precisione double, mentre `Flat` arrotonda al numero di cifre decimali specificato.  
- **SRID non visualizzato** – Solo la variante `ExtendedPostGis` antepone all'output `SRID=`. Scegli questa variante quando il tuo sistema di destinazione si aspetta un SRID.

## Conclusione
Seguendo questi passaggi ora sai come **convertire la geometria in WKT**, selezionare la variante corretta e controllare con precisione l'output numerico. Questo ti offre la flessibilità di integrare Aspose.GIS con qualsiasi flusso di lavoro GIS, database o servizio web che consuma WKT.

## FAQ
### Aspose.GIS è compatibile con tutte le versioni di .NET?
Sì, Aspose.GIS supporta .NET Framework 4.0 e versioni successive.  

### Posso usare Aspose.GIS per progetti commerciali?
Sì, Aspose.GIS può essere usato sia per progetti personali che commerciali.  

### Aspose.GIS fornisce supporto per altri formati di dati spaziali?
Sì, Aspose.GIS supporta un'ampia gamma di formati di dati spaziali, inclusi ESRI Shapefile, GeoJSON e KML.  

### È disponibile una versione di prova gratuita per Aspose.GIS?
Sì, puoi scaricare una versione di prova gratuita di Aspose.GIS da [qui](https://releases.aspose.com/).  

### Dove posso ottenere aiuto o supporto per Aspose.GIS?
Puoi pubblicare le tue domande o chiedere assistenza alla community di Aspose.GIS sul [forum](https://forum.aspose.com/c/gis/33).

## Domande frequenti
**D: Come esportare una collezione di Geometry in una singola stringa WKT?**  
Itera su ogni geometria nella collezione e concatena i risultati `AsText`, opzionalmente separandoli con virgole o nuove righe.

**D: Posso cambiare il SRID senza modificare le coordinate?**  
Sì, imposta la proprietà `SpatialReferenceSystem` sul SRID desiderato; i valori delle coordinate rimangono invariati.

**D: Cosa succede se utilizzo una variante WKT non supportata?**  
Aspose.GIS genererà un `ArgumentException`. Convalida sempre la variante rispetto ai valori dell'enum `WktVariant`.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}