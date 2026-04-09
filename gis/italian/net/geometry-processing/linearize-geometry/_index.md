---
date: 2026-04-09
description: Scopri come convertire le curve in linee (linearizzare la geometria)
  usando Aspose.GIS per .NET, consentendo un'elaborazione e un'analisi geospaziale
  efficienti nelle tue applicazioni .NET.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
linktitle: Linearizzare una geometria
second_title: Aspose.GIS .NET API
title: Come convertire curve in linee con Aspose.GIS per .NET
url: /it/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti curve in linee (Linearizza geometria) con Aspose.GIS per .NET

## Introduzione
Se hai bisogno di **convert curves to lines** per la mappatura, l'analisi spaziale o attività di scambio dati, Aspose.GIS per .NET ti offre un modo pulito e programmatico per farlo. In questo tutorial percorreremo un esempio completo e reale che mostra come prendere una geometria complessa—contenente curve e forme composte—e trasformarla in una semplice rappresentazione lineare che funziona con qualsiasi sistema GIS.

## Risposte rapide
- **Che cosa significa “convert curves to lines”?** Trasforma le geometrie curve in segmenti di linea retti.  
- **Perché scegliere Aspose.GIS?** La libreria supporta decine di formati GIS e gestisce la conversione della geometria senza strumenti esterni.  
- **Cosa serve in anticipo?** .NET Framework o .NET Core, Visual Studio (o qualsiasi IDE C#), e il pacchetto NuGet Aspose.GIS.  
- **Quanto tempo impiega l'esempio?** Meno di cinque minuti una volta installata la libreria.  
- **Posso esportare in altri formati?** Assolutamente—sostituisci il driver KML con Shapefile, GeoJSON, ecc.

## Cosa significa “convert curves to lines”?
Convertire curve in linee (chiamato anche **linearizing geometry**) scompone qualsiasi forma curva o composita in una serie di segmenti di linea retti, noti come “geometria lineare”. Questa semplificazione rende il rendering più veloce, migliora la compatibilità con i servizi GIS più vecchi e riduce la complessità degli algoritmi spaziali.

## Perché convertire curve in linee?
- **Prestazioni:** Le geometrie lineari vengono renderizzate e interrogate molto più velocemente.  
- **Compatibilità:** Molte piattaforme GIS (soprattutto servizi legacy) accettano solo feature lineari.  
- **Semplificazione:** Ideale per miniature, anteprime rapide o per fornire dati ad algoritmi che richiedono input lineare.

## Prerequisiti
Prima di immergerti nel codice, assicurati di avere:

1. **Aspose.GIS for .NET** – scaricalo dal [Aspose.GIS website](https://releases.aspose.com/gis/net/).  
2. **Framework .NET** (o .NET Core) installato sulla tua macchina di sviluppo.  
3. **Visual Studio** (o qualsiasi IDE compatibile C#) per scrivere ed eseguire l'esempio.

## Importa spazi dei nomi
Per iniziare a utilizzare le funzionalità di Aspose.GIS, importa gli spazi dei nomi richiesti.

### Passo 1: Spazi dei nomi principali di Aspose.GIS
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Passo 2: Driver per il formato di destinazione
Per questo esempio scriveremo il risultato in un file KML:
```csharp
using Aspose.GIS.Kml;
```

## Guida passo‑passo per convertire curve in linee
Di seguito è riportata una guida dettagliata riga per riga del codice, spiegando **how to convert curves to lines** e perché ogni passaggio è importante.

### Passo 1: Definisci il percorso di output
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Sostituisci `"Your Document Directory"` con la cartella in cui desideri salvare il file KML. Si consiglia di usare `Path.Combine` per la compatibilità cross‑platform.

### Passo 2: Crea un layer per il file di output
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
*Un layer* è un contenitore per le feature geografiche. Qui creiamo un nuovo layer KML che conterrà la nostra geometria linearizzata.

### Passo 3: Costruisci una nuova feature
```csharp
var feature = layer.ConstructFeature();
```
*Una feature* rappresenta un singolo oggetto geografico (punto, linea, poligono, ecc.). Allegheremo la nostra geometria lineare a questa feature.

### Passo 4: Definisci la geometria complessa originale
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Creiamo una geometria da una stringa Well‑Known Text (WKT). Questo esempio include un `LineString`, un `CompoundCurve` e un `CircularString`—perfetto per dimostrare **convert curves to lines**.

### Passo 5: Converti curve in linee
```csharp
var linear = geometry.ToLinearGeometry();
```
Il metodo `ToLinearGeometry()` converte tutte le curve in segmenti di linea retti, producendo una versione *lineare* della geometria originale.

### Passo 6: Assegna la geometria lineare alla feature
```csharp
feature.Geometry = linear;
```
Ora la feature contiene la geometria lineare semplificata.

### Passo 7: Aggiungi la feature al layer
```csharp
layer.Add(feature);
```
Infine, aggiungiamo la feature al layer KML, che scrive la geometria lineare nel file di output al termine del blocco `using`.

## Problemi comuni e consigli professionali
- **Separatori di percorso:** Usa `Path.Combine` per evitare problemi su Windows vs. Linux.  
- **Geometrie molto grandi:** Linearizzare forme complesse può generare migliaia di vertici; considera di chiamare `Simplify()` dopo la linearizzazione per ridurre il numero di punti.  
- **Selezione del driver:** Se ti serve un formato di output diverso, sostituisci `Drivers.Kml` con `Drivers.Shapefile`, `Drivers.GeoJson`, ecc., e modifica l'estensione del file di conseguenza.  
- **Preservare i valori Z:** `ToLinearGeometry()` mantiene le coordinate 3‑D (Z), così non perdi i dati di elevazione.

## Domande frequenti (FAQ)

**Q: Aspose.GIS per .NET è compatibile con .NET Core?**  
A: Sì, Aspose.GIS funziona con .NET Core, consentendo applicazioni cross‑platform.

**Q: Posso lavorare con diversi formati di file GIS usando Aspose.GIS per .NET?**  
A: Assolutamente! La libreria supporta KML, Shapefile, GeoJSON e molti altri formati.

**Q: Aspose.GIS offre operazioni e analisi spaziali?**  
A: Sì, fornisce un'ampia gamma di funzioni spaziali, dal buffering alle join spaziali.

**Q: È disponibile una versione di prova gratuita?**  
A: Sì, puoi scaricare una versione di prova gratuita dal [Aspose website](https://releases.aspose.com/).

**Q: Dove posso ottenere supporto se riscontro problemi?**  
A: Visita il [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per supporto della community e del personale.

### Domande comuni aggiuntive

**Q: Posso linearizzare geometrie che contengono coordinate 3D (Z)?**  
A: Sì, `ToLinearGeometry()` funziona sia con geometrie 2D che 3D; i valori Z sono preservati.

**Q: Come influisce la linearizzazione sulla dimensione del file?**  
A: Convertire curve in molti segmenti di linea brevi può aumentare la dimensione del file. Usa `Simplify()` dopo la linearizzazione se la dimensione è un problema.

**Q: Posso controllare la lunghezza del segmento quando converto curve in linee?**  
A: Il metodo predefinito utilizza una tolleranza interna. Per una segmentazione personalizzata puoi tessellare manualmente le curve prima di chiamare `ToLinearGeometry()`.

## Conclusione
In questo tutorial abbiamo coperto **how to convert curves to lines** (linearizzare geometria) usando Aspose.GIS per .NET, dalla configurazione dell'ambiente alla scrittura del risultato linearizzato in un file KML. Ora puoi integrare questo flusso di lavoro in applicazioni di mappatura, pipeline di elaborazione dati o qualsiasi progetto GIS che richieda geometrie semplificate.

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}