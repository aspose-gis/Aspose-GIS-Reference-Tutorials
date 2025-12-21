---
date: 2025-12-21
description: Scopri come linearizzare la geometria con Aspose.GIS per .NET, consentendo
  un'elaborazione efficiente dei dati geospaziali, l'analisi spaziale e la manipolazione
  della geometria nelle tue app .NET.
linktitle: Linearize a Geometry
second_title: Aspose.GIS .NET API
title: Come linearizzare la geometria usando Aspose.GIS per .NET
url: /it/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Linearizzare una Geometria

## Introduzione
Se hai bisogno di **come linearizzare una geometria** per la mappatura, l'analisi spaziale o attività di scambio dati, Aspose.GIS per .NET ti offre un modo pulito e programmatico per farlo. In questo tutorial percorreremo un esempio completo e reale che mostra come prendere una geometria complessa — contenente curve e forme composte — e trasformarla in una semplice rappresentazione lineare che funziona con qualsiasi sistema GIS.

## Risposte Rapide
- **Che cosa significa linearizzare una geometria?** Conversione di curve e forme complesse in segmenti di linea retti.  
- **Perché usare Aspose.GIS?** Supporta decine di formati GIS e gestisce la conversione delle geometrie senza strumenti esterni.  
- **Prerequisiti?** .NET Framework o .NET Core, Visual Studio e la libreria Aspose.GIS.  
- **Quanto tempo richiede l'esempio?** Meno di cinque minuti per l'esecuzione una volta installata la libreria.  
- **Posso salvare in altri formati?** Sì — sostituisci il driver KML con Shapefile, GeoJSON, ecc.

## Che cos'è la Linearizzazione della Geometria?
Linearizzare una geometria significa suddividere qualsiasi forma curva o composita in una serie di segmenti di linea retti (una “geometria lineare”). Questo semplifica il rendering, l'analisi e l'interoperabilità con strumenti che comprendono solo linee e punti.

## Perché Linearizzare la Geometria?
- **Prestazioni:** Le geometrie lineari sono più veloci da renderizzare e interrogare.  
- **Compatibilità:** Molte piattaforme GIS (ad esempio servizi di mappe più vecchi) accettano solo feature lineari.  
- **Semplificazione:** Utile per creare miniature, anteprime rapide o fornire dati a algoritmi che richiedono input lineare.

## Prerequisiti
Prima di immergerti nel codice, assicurati di avere:

1. **Aspose.GIS per .NET** – scaricalo dal [sito web Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (o .NET Core) installato sulla tua macchina di sviluppo.  
3. **Visual Studio** (o qualsiasi IDE compatibile con C#) per scrivere ed eseguire il campione.

## Importare gli Spazi dei Nomi
Per iniziare a utilizzare le funzionalità di Aspose.GIS, importa gli spazi dei nomi richiesti.

### Passo 1: Importare gli Spazi dei Nomi Core di Aspose.GIS
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Passo 2: Importare il Driver per il Formato di Destinazione
Per questo esempio scriveremo il risultato in un file KML:
```csharp
using Aspose.GIS.Kml;
```

## Come Linearizzare la Geometria – Guida Passo‑per‑Passo
Di seguito trovi una descrizione dettagliata di ogni riga di codice, spiegando **come linearizzare una geometria** e perché ogni passaggio è importante.

### Passo 1: Definire il Percorso di Output
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Sostituisci `"Your Document Directory"` con la cartella in cui desideri salvare il file KML.

### Passo 2: Creare un Layer per il File di Output
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
Un *layer* è un contenitore per le feature geografiche. Qui creiamo un nuovo layer KML che conterrà la nostra geometria linearizzata.

### Passo 3: Costruire una Nuova Feature
```csharp
var feature = layer.ConstructFeature();
```
Una *feature* rappresenta un singolo oggetto geografico (punto, linea, poligono, ecc.). Allegheremo la nostra geometria lineare a questa feature.

### Passo 4: Definire la Geometria Complessa Originale
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Creiamo una geometria da una stringa Well‑Known Text (WKT). Questo esempio include un `LineString`, un `CompoundCurve` e un `CircularString` — perfetto per dimostrare la linearizzazione.

### Passo 5: Linearizzare la Geometria
```csharp
var linear = geometry.ToLinearGeometry();
```
Il metodo `ToLinearGeometry()` converte tutte le curve in segmenti di linea retti, producendo una versione *lineare* della geometria originale.

### Passo 6: Assegnare la Geometria Lineare alla Feature
```csharp
feature.Geometry = linear;
```
Ora la feature contiene la geometria lineare semplificata.

### Passo 7: Aggiungere la Feature al Layer
```csharp
layer.Add(feature);
```
Infine, aggiungiamo la feature al layer KML, che scrive la geometria lineare nel file di output al termine del blocco `using`.

## Problemi Comuni & Consigli
- **Separatori di percorso:** Usa `Path.Combine` per la costruzione di percorsi cross‑platform.  
- **Geometrie grandi:** Linearizzare forme molto complesse può produrre molti vertici; considera l'uso di `Simplify()` dopo la linearizzazione se ti servono meno punti.  
- **Selezione del driver:** Se ti serve un formato di output diverso, sostituisci `Drivers.Kml` con `Drivers.Shapefile`, `Drivers.GeoJson`, ecc., e regola l'estensione del file di conseguenza.

## Conclusione
In questo tutorial abbiamo coperto **come linearizzare una geometria** usando Aspose.GIS per .NET, dalla configurazione dell'ambiente alla scrittura del risultato linearizzato in un file KML. Ora puoi integrare questo flusso di lavoro in applicazioni di mappatura, pipeline di elaborazione dati o qualsiasi progetto GIS che richieda geometrie semplificate.

## FAQ's
### Q: Aspose.GIS per .NET è compatibile con .NET Core?
Sì, Aspose.GIS per .NET è compatibile con .NET Core, consentendo di creare applicazioni cross‑platform.

### Q: Posso lavorare con diversi formati di file GIS usando Aspose.GIS per .NET?
Assolutamente! Aspose.GIS supporta vari formati di file GIS, inclusi KML, Shapefile, GeoJSON e altri.

### Q: Aspose.GIS offre supporto per operazioni e analisi spaziali?
Sì, Aspose.GIS offre un'ampia gamma di operazioni e capacità di analisi spaziale per gestire compiti geospaziali complessi.

### Q: È disponibile una versione di prova gratuita per Aspose.GIS per .NET?
Sì, puoi scaricare una versione di prova gratuita dal [sito web Aspose](https://releases.aspose.com/).

### Q: Dove posso trovare aiuto e supporto per Aspose.GIS?
Puoi visitare il [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per assistenza dalla community e dallo staff di supporto di Aspose.

## Domande Frequenti (Aggiuntive)

**Q: Posso linearizzare geometrie che contengono coordinate 3D (Z)?**  
A: Sì, `ToLinearGeometry()` funziona con geometrie 2D e 3D; i valori Z sono preservati nei segmenti di linea risultanti.

**Q: Come influisce la linearizzazione sulla dimensione del file di output?**  
A: Convertire curve in molti segmenti di linea brevi può aumentare la dimensione del file. Usa `Simplify()` dopo la linearizzazione se la dimensione del file è un problema.

**Q: È possibile controllare la lunghezza del segmento durante la linearizzazione?**  
A: Il metodo predefinito utilizza una tolleranza interna. Per una segmentazione personalizzata, puoi tessellare manualmente le curve prima di chiamare `ToLinearGeometry()`.

---

**Ultimo aggiornamento:** 2025-12-21  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}