---
date: 2026-04-03
description: Scopri come creare un poligono con buco usando Aspose.GIS per .NET. Questa
  guida ti mostra come creare un buco in un poligono e lavorare con dati geospaziali.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: Crea poligono con geometria a buco
second_title: Aspose.GIS .NET API
title: Crea un poligono con geometria a foro usando Aspose.GIS
url: /it/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea geometria di poligono con foro usando Aspose.GIS

## Introduzione
In questo tutorial, **creerai un poligono con foro** usando Aspose.GIS per .NET. Che tu stia costruendo un'applicazione di mappatura, eseguendo analisi spaziali o preparando dati per servizi GIS, sapere come inserire un foro all'interno di un poligono è fondamentale. Ti guideremo passo‑a‑passo, dalla configurazione dell'ambiente alla generazione dell'oggetto poligono finale.

## Risposte rapide
- **Cosa significa “creare un poligono con foro”?** Significa costruire un poligono che contiene uno o più anelli interni (fori) esclusi dall'area.  
- **Quale libreria gestisce questo?** Aspose.GIS per .NET fornisce pieno supporto per anelli esterni e interni.  
- **È necessaria una licenza?** Una prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Quanto tempo richiede?** Tipicamente meno di 10 minuti per implementare e testare.

## Come aggiungere un foro a un poligono usando Aspose.GIS
Aggiungere un foro è semplicemente questione di definire un **anello interno** e collegarlo al poligono. La libreria si occupa dell'orientamento e della validità, così puoi concentrarti sulle coordinate che rappresentano il vuoto necessario.

## Cos'è “creare un poligono con foro”?
Creare un poligono con un foro comporta la definizione di un **anello esterno** che delinea il contorno esterno e uno o più **anelli interni** che rimuovono spazi vuoti. Gli anelli interni sono spesso chiamati *fori* perché rappresentano aree che non fanno parte della superficie del poligono.

## Perché creare un foro in un poligono usando Aspose.GIS?
- **Modellazione spaziale accurata:** Caratteristiche del mondo reale come laghi all'interno di lotti o cortili all'interno di edifici richiedono fori.  
- **Interoperabilità:** Formati come Shapefile, GeoJSON e GML supportano nativamente gli anelli interni; Aspose.GIS li preserva.  
- **Prestazioni:** La libreria gestisce la validità della geometria, così non devi scrivere codice di validazione personalizzato.

## Scenari reali per poligoni con fori
1. **Lotto di terreno con lago interno** – il lago è modellato come un foro così non viene conteggiato nell'area del lotto.  
2. **Impronte di edifici con cortili** – il cortile è escluso dall'impronta dell'edificio.  
3. **Zone protette all'interno di un'area di conservazione più ampia** – puoi escludere sezioni ristrette senza creare layer separati.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Libreria Aspose.GIS per .NET: puoi scaricarla da [here](https://releases.aspose.com/gis/net/).  
2. Ambiente di sviluppo: assicurati di avere un ambiente di sviluppo configurato con Visual Studio o qualsiasi altro IDE .NET installato.

## Importa spazi dei nomi
Per prima cosa, devi importare gli spazi dei nomi necessari per lavorare con le funzionalità di Aspose.GIS. Ecco come fare:

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ora, procediamo a creare una geometria di poligono con foro usando Aspose.GIS per .NET.

## Passo 1: Crea oggetto Polygon
Iniziamo istanziando un oggetto `Polygon` vuoto che conterrà successivamente sia l'anello esterno sia gli anelli interni.

```csharp
Polygon polygon = new Polygon();
```

## Passo 2: Definisci anello esterno
L'anello esterno definisce il contorno esterno del poligono. Aggiungi i punti in ordine orario per formare una forma chiusa.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Passo 3: Definisci anello interno (foro)
Successivamente, creiamo un anello interno—questo è il **foro** che verrà escluso dall'area del poligono. I punti sono tipicamente aggiunti in ordine antiorario, ma Aspose.GIS gestisce automaticamente l'orientamento.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Passo 4: Assegna anello esterno e aggiungi anello interno al poligono
Infine, collega l'anello esterno al poligono e poi aggiungi l'anello interno (il foro). Il metodo `AddInteriorRing` può essere chiamato più volte se hai bisogno di diversi fori.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Suggerimenti e migliori pratiche
- **L'orientamento è importante per la leggibilità** – mentre Aspose.GIS corregge automaticamente l'orientamento, mantenere gli anelli esterni in senso orario e gli interni in senso antiorario rende la geometria più facile da ispezionare nei visualizzatori GIS.  
- **Chiudi ogni anello** – ripeti sempre la prima coordinata come ultimo punto; questo garantisce una forma chiusa valida.  
- **Valida dopo la creazione** – puoi chiamare `polygon.IsValid` per assicurarti che la geometria rispetti gli standard OGC prima di salvare.

## Problemi comuni e soluzioni
| Problema | Motivo | Correzione |
|----------|--------|------------|
| Il foro non appare nel visualizzatore GIS | Orientamento dell'anello interno invertito | Assicurati che i punti siano aggiunti nella direzione opposta rispetto all'anello esterno (antiorario). |
| Errore di poligono non valido | Anelli non chiusi (primo ≠ ultimo punto) | Ripeti il primo punto come ultimo punto in ogni anello (come mostrato sopra). |
| Geometria vuota inaspettata | Dimenticato di assegnare `ExteriorRing` prima di aggiungere anelli interni | Imposta prima `polygon.ExteriorRing`, poi chiama `AddInteriorRing`. |

## Domande frequenti
### 1. Cos'è Aspose.GIS?
Aspose.GIS è una libreria .NET che consente agli sviluppatori di lavorare con dati geospaziali, permettendo di creare, leggere e manipolare vari formati di file geospaziali.

### 2. Posso usare Aspose.GIS per progetti commerciali?
Sì, puoi usare Aspose.GIS sia per progetti personali che commerciali acquistando una licenza. Visita [here](https://purchase.aspose.com/buy) per maggiori dettagli.

### 3. È disponibile una versione di prova gratuita per Aspose.GIS?
Sì, puoi usufruire di una prova gratuita di Aspose.GIS da [here](https://releases.aspose.com/).

### 4. Dove posso trovare supporto per Aspose.GIS?
Puoi trovare supporto per Aspose.GIS sul [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

### 5. Come posso ottenere una licenza temporanea per Aspose.GIS?
Puoi ottenere una licenza temporanea per Aspose.GIS da [here](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2026-04-03  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}