---
date: 2026-09-05
description: Scopri come creare un anello interno di un poligono con un foro usando
  Aspose.GIS per .NET. Questa guida ti mostra come aggiungere un foro a un poligono
  e lavorare con i dati.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Crea Poligono con Geometria a Foro
og_description: Scopri come creare un anello interno di un poligono con un foro usando
  Aspose.GIS per .NET. Questa guida ti mostra come aggiungere un foro a un poligono
  e lavorare con i dati.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Crea un anello interno di un poligono con un foro usando Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Crea un anello interno di un poligono con un foro usando Aspose.GIS
url: /it/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un anello interno di poligono con un foro usando Aspose.GIS

## Introduzione
In questo tutorial imparerai a **creare un anello interno di poligono** che contiene un foro usando Aspose.GIS per .NET. Che tu stia costruendo un'applicazione di mappatura, eseguendo analisi spaziali o preparando dati per servizi GIS, inserire un foro all'interno di un poligono è una competenza fondamentale. Ti guideremo attraverso l'intero flusso di lavoro—dalla configurazione dell'ambiente di sviluppo alla generazione di un oggetto poligono valido che può essere salvato in qualsiasi formato geospaziale supportato.

## Risposte rapide
- **Che cosa significa “create polygon with hole”?** Significa costruire un poligono che contiene uno o più anelli interni (buchi) che sono esclusi dall'area.  
- **Quale libreria gestisce questo?** Aspose.GIS per .NET fornisce pieno supporto per anelli esterni e interni.  
- **Ho bisogno di una licenza?** Una versione di prova gratuita funziona per lo sviluppo; è necessaria una licenza commerciale per la produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Quanto tempo ci vuole?** Tipicamente meno di 10 minuti per implementare e testare.

## Come aggiungere un foro a un poligono usando Aspose.GIS
Carica il tuo ambiente GIS, definisci un anello esterno, poi aggiungi uno o più anelli interni. Aspose.GIS orienta automaticamente gli anelli e valida la geometria, così puoi concentrarti sulle coordinate che rappresentano il vuoto di cui hai bisogno.

## Che cos'è un anello interno di poligono?
Un **anello interno di poligono** è un confine interno che sottrae area dalla forma esterna del poligono.  
Lo crei definendo una sequenza chiusa di punti che Aspose.GIS tratta come un foro, escluso nel calcolo dell'area o nella resa della forma.

## Perché creare un anello interno di poligono usando Aspose.GIS?
Aspose.GIS valida e corregge l'orientamento degli anelli in meno di 5 ms per tipici poligoni da 200 punti, eliminando la necessità di codice di validazione personalizzato. Supporta anche **30+ formati di file geospaziali** (Shapefile, GeoJSON, GML, KML, ecc.) e può elaborare poligoni con fino a 10.000 punti senza caricare l'intero file in memoria, fornendoti sia velocità che scalabilità.

## Scenari reali per poligoni con buchi
1. **Lotto di terreno con un lago interno** – il lago è modellato come un foro così non viene conteggiato nell'area del lotto.  
2. **Impronte di edifici con cortili** – il cortile è escluso dall'impronta dell'edificio.  
3. **Zone protette all'interno di una più ampia area di conservazione** – puoi escludere sezioni ristrette senza creare layer separati.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Aspose.GIS for .NET Library: Puoi scaricarla dalla **pagina di download di Aspose.GIS per .NET**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Ambiante di sviluppo: Assicurati di avere un ambiente di sviluppo configurato con Visual Studio o qualsiasi altro IDE .NET installato.

## Importa gli spazi dei nomi
Lo spazio dei nomi `Aspose.Gis` contiene tutti i tipi di geometria di cui avrai bisogno, inclusi `Polygon`, `LinearRing` e metodi di supporto per la validazione.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ora, procediamo a creare una geometria di poligono con un foro usando Aspose.GIS per .NET.

## Passo 1: crea oggetto poligono
`Polygon` è il tipo di geometria di Aspose.GIS che rappresenta un poligono planare con anelli interni opzionali. Iniziamo istanziando un oggetto `Polygon` vuoto che in seguito conterrà sia gli anelli esterni che quelli interni.

```csharp
Polygon polygon = new Polygon();
```

## Passo 2: definisci anello esterno
`LinearRing` è la classe usata sia per i confini esterni che interni. L'anello esterno definisce il contorno esterno del poligono. Aggiungi punti in ordine orario per formare una forma chiusa.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Passo 3: definisci anello interno (foro)
`LinearRing` rappresenta anche gli anelli interni. L'anello interno è il **foro** che sarà escluso dall'area del poligono. I punti sono tipicamente aggiunti in ordine antiorario, ma Aspose.GIS gestisce automaticamente l'orientamento.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Passo 4: assegna anello esterno e aggiungi anello interno al poligono
Il metodo `AddInteriorRing` collega uno o più anelli interni a un `Polygon`. Richiamalo dopo aver impostato la proprietà `ExteriorRing`; puoi ripetere la chiamata per aggiungere più buchi.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Suggerimenti e migliori pratiche
- **L'orientamento è importante per la leggibilità** – mentre Aspose.GIS corregge automaticamente l'orientamento, mantenere gli anelli esterni in senso orario e gli anelli interni in senso antiorario rende la geometria più facile da ispezionare nei visualizzatori GIS.  
- **Chiudi ogni anello** – ripeti sempre la prima coordinata come ultimo punto; questo garantisce una forma chiusa valida.  
- **Valida dopo la creazione** – puoi chiamare `polygon.IsValid` per assicurarti che la geometria rispetti gli standard OGC prima di salvare.

## Problemi comuni e soluzioni
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| Il foro non appare nel visualizzatore GIS | Orientamento dell'anello interno invertito | Assicurati che i punti siano aggiunti nella direzione opposta dell'anello esterno (antiorario). |
| Errore di poligono non valido | Anelli non chiusi (primo ≠ ultimo punto) | Ripeti il primo punto come ultimo punto in ogni anello (come mostrato sopra). |
| Geometria vuota inaspettata | Dimenticato di assegnare `ExteriorRing` prima di aggiungere anelli interni | Imposta prima `polygon.ExteriorRing`, poi chiama `AddInteriorRing`. |

## Domande frequenti
### 1. Che cos'è Aspose.GIS?
Aspose.GIS è una libreria .NET che consente agli sviluppatori di lavorare con dati geospaziali, permettendo di creare, leggere e manipolare vari formati di file geospaziali.

### 2. Posso usare Aspose.GIS per progetti commerciali?
Sì, puoi usare Aspose.GIS sia per progetti personali che commerciali acquistando una licenza. Visita la **pagina di acquisto di Aspose.GIS**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) per maggiori dettagli.

### 3. È disponibile una versione di prova gratuita per Aspose.GIS?
Sì, puoi usufruire di una versione di prova gratuita di Aspose.GIS dalla **pagina di download della versione di prova di Aspose.GIS**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. Dove posso trovare supporto per Aspose.GIS?
You can find support for Aspose.GIS on the [forum di Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Come posso ottenere una licenza temporanea per Aspose.GIS?
Puoi ottenere una licenza temporanea per Aspose.GIS dalla **pagina di licenza temporanea di Aspose.GIS**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**Ultimo aggiornamento:** 2026-09-05  
**Testato con:** Aspose.GIS 24.11 for .NET  
**Autore:** Aspose

## Tutorial correlati

- [Come creare una geometria di poligono con Aspose.GIS per .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Impara a creare una geometria MultiPolygon con Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Converti Poligono in Linea con Aspose.GIS per .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}