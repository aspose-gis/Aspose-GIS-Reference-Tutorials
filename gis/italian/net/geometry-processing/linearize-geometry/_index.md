---
date: 2026-04-06
description: Scopri come convertire le curve in linee e linearizzare la geometria
  con Aspose.GIS per .NET, consentendo una rapida elaborazione e analisi geospaziale
  nelle tue applicazioni .NET.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS linearize geometry
linktitle: Linearizzare una geometria
second_title: Aspose.GIS .NET API
title: Converti curve in linee usando Aspose.GIS per .NET
url: /it/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti curve in linee usando Aspose.GIS per .NET

## Introduzione
Se hai bisogno di **convertire curve in linee** per mappatura, analisi spaziale o attività di scambio dati, Aspose.GIS per .NET ti offre un modo pulito e programmatico per farlo. In questo tutorial percorreremo un esempio completo e reale che mostra come prendere una geometria complessa—contenente curve e forme composte—e trasformarla in una semplice rappresentazione lineare che funziona con qualsiasi sistema GIS.

## Risposte rapide
- **Cosa significa linearizzare una geometria?** Convertire curve e forme complesse in segmenti di linea retta.  
- **Perché usare Aspose.GIS?** Supporta decine di formati GIS e gestisce la conversione della geometria senza strumenti esterni.  
- **Prerequisiti?** .NET Framework o .NET Core, Visual Studio e la libreria Aspose.GIS.  
- **Quanto tempo richiede l'esempio?** Meno di cinque minuti per l'esecuzione una volta installata la libreria.  
- **Posso salvare in altri formati?** Sì—sostituisci il driver KML con Shapefile, GeoJSON, ecc.

## Cos'è la linearizzazione della geometria?
Linearizzare una geometria significa scomporre qualsiasi forma curva o composita in una serie di segmenti di linea retta (una “geometria lineare”). Questo semplifica il rendering, l'analisi e l'interoperabilità con strumenti che comprendono solo linee e punti.

## Perché convertire curve in linee?
- **Prestazioni:** Le geometrie lineari sono più veloci da renderizzare e interrogare.  
- **Compatibilità:** Molte piattaforme GIS (ad esempio servizi di mappe più vecchi) accettano solo feature lineari.  
- **Semplificazione:** Utile per creare miniature, anteprime rapide o per alimentare algoritmi che richiedono input lineare.

## Prerequisiti
Prima di immergerti nel codice, assicurati di avere:

1. **Aspose.GIS per .NET** – scaricalo dal [sito web di Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (o .NET Core) installato sulla tua macchina di sviluppo.  
3. **Visual Studio** (o qualsiasi IDE compatibile con C#) per scrivere ed eseguire il campione.

## Importa spazi dei nomi
Per iniziare a utilizzare le funzionalità di Aspose.GIS, importa gli spazi dei nomi richiesti.

### Passo 1: Importa gli spazi dei nomi principali di Aspose.GIS
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Passo 2: Importa il driver per il formato di destinazione
Per questo esempio scriveremo il risultato in un file KML:
```csharp
using Aspose.GIS.Kml;
```

## Come convertire curve in linee – Guida passo‑passo
Di seguito trovi una spiegazione dettagliata di ogni riga di codice, che illustra **come convertire curve in linee** e perché ogni passaggio è importante.

### Passo 1: Definisci il percorso di output
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Sostituisci `"Your Document Directory"` con la cartella in cui desideri salvare il file KML.

### Passo 2: Crea un layer per il file di output
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
Un *layer* è un contenitore per le feature geografiche. Qui creiamo un nuovo layer KML che conterrà la nostra geometria linearizzata.

### Passo 3: Costruisci una nuova feature
```csharp
var feature = layer.ConstructFeature();
```
Una *feature* rappresenta un singolo oggetto geografico (punto, linea, poligono, ecc.). Allegheremo la nostra geometria lineare a questa feature.

### Passo 4: Definisci la geometria complessa originale
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Creiamo una geometria da una stringa Well‑Known Text (WKT). Questo esempio include un `LineString`, un `CompoundCurve` e un `CircularString`—perfetto per dimostrare la conversione di curve in linee.

### Passo 5: Linearizza la geometria
```csharp
var linear = geometry.ToLinearGeometry();
```
Il metodo `ToLinearGeometry()` converte tutte le curve in segmenti di linea retta, producendo una versione *lineare* della geometria originale.

### Passo 6: Assegna la geometria lineare alla feature
```csharp
feature.Geometry = linear;
```
Ora la feature contiene la geometria semplificata e lineare.

### Passo 7: Aggiungi la feature al layer
```csharp
layer.Add(feature);
```
Infine, aggiungiamo la feature al layer KML, che scrive la geometria lineare nel file di output quando termina il blocco `using`.

## Problemi comuni e consigli
- **Separatori di percorso:** Usa `Path.Combine` per costruire percorsi compatibili con più piattaforme.  
- **Geometrie grandi:** Linearizzare forme molto complesse può generare molti vertici; considera l'uso di `Simplify()` dopo la linearizzazione se ti servono meno punti.  
- **Selezione del driver:** Se ti serve un formato di output diverso, sostituisci `Drivers.Kml` con `Drivers.Shapefile`, `Drivers.GeoJson`, ecc., e adegua l'estensione del file di conseguenza.

## Domande frequenti (migliorate)

**D: Aspose.GIS per .NET è compatibile con .NET Core?**  
R: Sì, Aspose.GIS per .NET funziona con .NET Core, consentendo di creare applicazioni cross‑platform.

**D: Posso lavorare con diversi formati di file GIS usando Aspose.GIS per .NET?**  
R: Assolutamente! Aspose.GIS supporta KML, Shapefile, GeoJSON e molti altri formati.

**D: Aspose.GIS offre supporto per operazioni e analisi spaziali?**  
R: Sì, fornisce un'ampia gamma di operazioni e capacità di analisi spaziale per gestire compiti geospaziali complessi.

**D: È disponibile una versione di prova gratuita per Aspose.GIS per .NET?**  
R: Sì, puoi scaricare una prova gratuita dal [sito web di Aspose](https://releases.aspose.com/).

**D: Dove posso trovare aiuto e supporto per Aspose.GIS?**  
R: Visita il [forum di Aspose.GIS](https://forum.aspose.com/c/gis/33) per assistenza dalla community e dallo staff di supporto Aspose.

**Domande aggiuntive**

**D: Posso linearizzare geometrie che contengono coordinate 3D (Z)?**  
R: Sì, `ToLinearGeometry()` funziona sia con geometrie 2D che 3D; i valori Z sono preservati nei segmenti di linea risultanti.

**D: Come influisce la linearizzazione sulla dimensione del file di output?**  
R: Convertire curve in molti segmenti di linea brevi può aumentare la dimensione del file. Usa `Simplify()` dopo la linearizzazione se la dimensione è un problema.

**D: È possibile controllare la lunghezza dei segmenti durante la linearizzazione?**  
R: Il metodo predefinito utilizza una tolleranza interna. Per una segmentazione personalizzata, puoi tessellare manualmente le curve prima di chiamare `ToLinearGeometry()`.

## Conclusione
In questo tutorial abbiamo coperto **come convertire curve in linee** usando Aspose.GIS per .NET, dalla configurazione dell'ambiente alla scrittura del risultato linearizzato in un file KML. Ora puoi integrare questo flusso di lavoro in applicazioni di mappatura, pipeline di elaborazione dati o qualsiasi progetto GIS che richieda geometrie semplificate.

---

**Last Updated:** 2026-04-06  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}