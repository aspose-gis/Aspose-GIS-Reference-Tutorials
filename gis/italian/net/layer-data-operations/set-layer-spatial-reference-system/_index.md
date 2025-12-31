---
date: 2025-12-31
description: Scopri come creare un layer vettoriale e impostare il sistema di riferimento
  spaziale del layer con Aspose.GIS per .NET. Impara a definire il riferimento spaziale,
  aggiungere una feature puntuale e recuperare il codice EPSG.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: Crea livello vettoriale e imposta il sistema di riferimento spaziale del livello
url: /it/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea layer vettoriale e imposta il sistema di riferimento spaziale del layer

## Introduzione
Nel vasto panorama dei sistemi informativi geografici (GIS), **Aspose.GIS for .NET** si distingue come uno strumento robusto e versatile per gli sviluppatori. In questo tutorial **creerai un layer vettoriale**, ne definirai il riferimento spaziale, aggiungerai una feature puntuale e recupererai il codice EPSG—tutto con indicazioni chiare passo‑passo. Che tu sia un ingegnere GIS esperto o alle prime armi, queste tecniche ti aiuteranno a impostare correttamente il sistema di coordinate dello shapefile e a migliorare l’affidabilità dei flussi di lavoro con dati spaziali.

## Risposte rapide
- **Cosa significa “creare layer vettoriale”?** Crea un nuovo layer GIS (ad es. uno Shapefile) in grado di memorizzare geometrie come punti, linee o poligoni.  
- **Quale codice EPSG è usato nell’esempio?** EPSG 26918 (NAD83 / UTM zona 18N).  
- **Posso aggiungere una feature puntuale dopo aver creato il layer?** Sì—usa `ConstructFeature()` e assegna una geometria `Point`.  
- **Come recupero il CRS del layer?** Leggi `layer.SpatialReferenceSystem.EpsgCode` o `.Name`.  
- **È necessaria una licenza per Aspose.GIS?** È disponibile una versione di prova gratuita; per l’uso in produzione è richiesta una licenza.

## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Conoscenza pratica della programmazione .NET.  
- Visual Studio installato sul tuo sistema.  
- Libreria Aspose.GIS for .NET, scaricabile [qui](https://releases.aspose.com/gis/net/).  
- Una comprensione di base dei sistemi di riferimento spaziale nei GIS.

## Importazione dei namespace
Nel tuo progetto .NET, inizia importando i namespace necessari per accedere alle funzionalità offerte da Aspose.GIS. Usa lo snippet di codice seguente:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Passo 1: Specifica la directory dei documenti
Inizia specificando il percorso della tua directory dei documenti. Questo sarà il luogo in cui verranno memorizzati i file dei dati spaziali.

```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Definisci il riferimento spaziale e imposta il sistema di coordinate dello shapefile
Definisci il percorso per lo Shapefile e **definisci il riferimento spaziale** usando il codice EPSG (26918 in questo esempio). Questo passo **imposta il sistema di coordinate dello shapefile** per il layer.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Passo 3: Crea layer vettoriale
Ora **crea il layer vettoriale** con il percorso Shapefile specificato, il tipo di driver (Shapefile) e il sistema di riferimento spaziale appena definito.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Passo 4: Aggiungi una feature puntuale al layer
Costruisci una nuova feature e **aggiungi la feature puntuale** impostando la sua geometria (un `Point` con coordinate 60, 24). Quindi aggiungi la feature al layer vettoriale.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Passo 5: Recupera le informazioni del sistema di riferimento spaziale (Recupera codice EPSG)
Apri il Vector Layer e recupera le informazioni sul sistema di riferimento spaziale, come il codice EPSG e il nome leggibile dall’uomo. Questo dimostra come **recuperare il codice EPSG** e **impostare il CRS del layer**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Ripeti questi passaggi secondo il tuo caso d’uso specifico, e sarai sulla buona strada per padroneggiare l’arte di **creare layer vettoriale** e gestire i riferimenti spaziali con Aspose.GIS for .NET.

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| **Il layer non si apre** | Driver errato o percorso del file corrotto | Verifica `Drivers.Shapefile` e assicurati che `path` punti a un file `.shp` esistente. |
| **Viene mostrato un CRS errato** | Uso di un codice EPSG sbagliato | Controlla nuovamente il codice EPSG con una fonte autorevole (ad es. EPSG.io). |
| **La feature non viene salvata** | Mancata chiamata a `layer.Add(feature)` all’interno del blocco `using` | Assicurati che il metodo `Add` venga eseguito prima che il layer venga eliminato. |

## Domande frequenti
### Aspose.GIS è compatibile con altre librerie GIS?
Sì, Aspose.GIS si integra bene con altre librerie GIS e può essere usato in combinazione con esse.

### Posso usare Aspose.GIS sia per applicazioni desktop che web?
Assolutamente! Aspose.GIS è versatile e può essere utilizzato sia in applicazioni desktop sia in applicazioni basate sul web.

### Quali opzioni di licenza sono disponibili per Aspose.GIS?
Sì, puoi esplorare le opzioni di licenza e effettuare un acquisto [qui](https://purchase.aspose.com/buy).

### È disponibile una versione di prova gratuita per Aspose.GIS?
Certamente! Puoi scaricare una versione di prova gratuita [qui](https://releases.aspose.com/).

### Dove posso richiedere supporto per domande relative ad Aspose.GIS?
Per qualsiasi supporto o domanda, visita il [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

## Altre domande frequenti
**D: Come cambio il CRS di uno Shapefile esistente?**  
R: Apri il layer, crea un nuovo `SpatialReferenceSystem` con il codice EPSG desiderato e assegnalo a `layer.SpatialReferenceSystem` prima di salvare.

**D: Posso aggiungere altri tipi di geometria (ad es. poligoni) con lo stesso approccio?**  
R: Sì—sostituisci `new Point(x, y)` con `new Polygon(...)` o `new LineString(...)` secondo necessità.

**D: È possibile lavorare con grandi dataset in modo efficiente?**  
R: Usa le API di streaming (`VectorLayer.Create` con `FeatureCollection`) e rilascia i layer tempestivamente per liberare le risorse.

**D: Aspose.GIS supporta la trasformazione delle coordinate?**  
R: Sì—usa `Geometry.Transform(targetSrs)` per riproiettare le geometrie tra diversi riferimenti spaziali.

**D: Quali versioni di .NET sono supportate?**  
R: Aspose.GIS funziona con .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Conclusione
In questo tutorial abbiamo esplorato come **creare un layer vettoriale**, definirne il riferimento spaziale, **aggiungere una feature puntuale** e **recuperare il codice EPSG** usando Aspose.GIS for .NET. Padroneggiando questi passaggi potrai impostare correttamente il sistema di coordinate dello shapefile, gestire il CRS del layer e costruire applicazioni GIS affidabili.

---

**Ultimo aggiornamento:** 2025-12-31  
**Testato con:** Aspose.GIS 24.11 for .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}