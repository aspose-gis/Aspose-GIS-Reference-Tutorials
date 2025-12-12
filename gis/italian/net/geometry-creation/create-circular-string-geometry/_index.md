---
date: 2025-12-12
description: Scopri come creare un livello vettoriale e aggiungere geometria a stringa
  circolare usando Aspose.GIS per .NET – un modo rapido per creare applicazioni GIS.
linktitle: Create Circular String Geometry
second_title: Aspose.GIS .NET API
title: Crea livello vettoriale e stringa circolare in Aspose.GIS per .NET
url: /it/net/geometry-creation/create-circular-string-geometry/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un layer vettoriale e una geometria Circular String con Aspose.GIS per .NET

## Introduzione
Se stai creando un'applicazione GIS sulla piattaforma .NET, il primo passo è spesso **to create vector layer** oggetti che memorizzano le tue feature spaziali. Aspose.GIS per .NET rende questo processo semplice e ti consente di arricchire quei layer con geometrie avanzate come le circular strings. In questo tutorial imparerai esattamente come creare un vector layer, aggiungere una geometria circular string e salvare il risultato come Shapefile—tutto con codice C# pulito e pronto per la produzione.

## Risposte rapide
- **What does “create vector layer” mean?** Crea un nuovo contenitore (layer) che può contenere feature spaziali come punti, linee o poligoni.  
- **Which class represents a circular string?** La classe `CircularString` di `Aspose.Gis.Geometries`.  
- **Can I save the layer as a Shapefile?** Sì – usa `Drivers.Shapefile` quando crei il layer.  
- **Do I need a license for development?** Una licenza temporanea è sufficiente per la valutazione; è necessaria una licenza completa per la produzione.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Che cos'è “create vector layer”?
Un layer vettoriale è un raggruppamento logico di feature vettoriali (punti, linee, poligoni) memorizzate in una singola fonte dati. In Aspose.GIS istanzi un layer chiamando `VectorLayer.Create`, passando il percorso del file di destinazione e il driver desiderato (ad esempio, Shapefile). Una volta che il layer esiste, puoi aggiungere feature, assegnare geometrie ed eseguire operazioni spaziali.

## Perché aggiungere una circular string?
Le circular strings sono un tipo di **geometria lineare** che approssima archi usando una sequenza di punti. Sono utili per rappresentare strade curve, curve di fiumi o qualsiasi feature in cui è necessaria una curva fluida senza ricorrere a molti piccoli segmenti di linea.

## Prerequisiti
- **.NET Framework o .NET Core** installati sulla tua macchina.  
- Libreria **Aspose.GIS for .NET** – scaricala dal sito ufficiale **[here](https://releases.aspose.com/gis/net/)**.  
- Un IDE come **Visual Studio** o **JetBrains Rider**.  
- Familiarità di base con la programmazione **C#**.

## Importa gli spazi dei nomi
Add the required namespaces to your C# file:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Guida passo‑passo

### Passo 1: Definisci il percorso del file di output
Imposta la posizione in cui verrà scritto lo Shapefile.

```csharp
string path = "Your Document Directory" + "CreateCircularString_out.shp";
```

Sostituisci `"Your Document Directory"` con il percorso reale della cartella sul tuo sistema.

### Passo 2: **Create vector layer**
Apri un `VectorLayer` usando il metodo `Create`. Questo è il nucleo dell'operazione **create vector layer**.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile))
{
```

### Passo 3: Costruisci una nuova feature
Una feature rappresenta un singolo record spaziale all'interno del layer.

```csharp
    var feature = layer.ConstructFeature();
```

### Passo 4: Costruisci la geometria circular string
Aggiungi i punti che definiscono la forma curva. La sequenza di punti crea un arco che inizia e termina nella stessa posizione, formando una circular string chiusa.

```csharp
    var circularString = new CircularString();
    circularString.AddPoint(0, 0);
    circularString.AddPoint(1, 1);
    circularString.AddPoint(2, 0);
    circularString.AddPoint(1, -1);
    circularString.AddPoint(0, 0);
```

### Passo 5: Assegna la geometria e aggiungi la feature al layer
Collega la geometria alla feature e memorizzala nel layer.

```csharp
    feature.Geometry = circularString;
    layer.Add(feature);
}
```

Quando il blocco `using` termina, il layer viene automaticamente scritto nello Shapefile su disco.

## Problemi comuni e soluzioni
| Problema | Soluzione |
|----------|-----------|
| **File path invalid** | Assicurati che la directory esista e che tu abbia i permessi di scrittura. |
| **CircularString appears as a straight line** | Verifica che i punti siano aggiunti nell'ordine corretto; il primo e l'ultimo punto dovrebbero essere identici per una forma chiusa. |
| **License exception** | Applica una licenza temporanea durante lo sviluppo o acquista una licenza completa per l'uso in produzione. |

## Domande frequenti

### Aspose.GIS per .NET è compatibile con tutte le versioni del .NET Framework?
Sì, Aspose.GIS per .NET è progettato per funzionare con un'ampia gamma di versioni .NET, dal Framework 4.5 fino alle ultime versioni .NET 8.

### Posso integrare Aspose.GIS per .NET con altre librerie GIS?
Assolutamente! Puoi leggere dati con altre librerie, manipolarli con Aspose.GIS e poi riscriverli, grazie alla sua API flessibile.

### Aspose.GIS per .NET supporta la visualizzazione di dati spaziali?
Sì, la libreria include utilità di rendering che ti permettono di generare mappe e rappresentazioni visive delle tue geometrie.

### Esiste un forum della community dove posso chiedere assistenza su Aspose.GIS per .NET?
Sì, puoi visitare il forum Aspose.GIS **[here](https://forum.aspose.com/c/gis/33)** per fare domande e condividere esperienze.

### Posso ottenere una licenza temporanea per valutare Aspose.GIS per .NET?
Certamente! Una licenza temporanea di valutazione è disponibile **[here](https://purchase.aspose.com/temporary-license/)**.

### Come aggiungo geometrie più complesse (ad esempio, MultiLineString) allo stesso layer?
Crea l'oggetto geometria appropriato (ad esempio, `MultiLineString`), popolalo con oggetti `LineString` individuali, assegnalo a `feature.Geometry` e aggiungi la feature come abbiamo fatto con la circular string.

## Conclusione
Seguendo questi passaggi ora sai come **create vector layer** oggetti e arricchirli con una geometria circular string usando Aspose.GIS per .NET. Questa base ti consente di costruire soluzioni GIS più avanzate—che tu stia mappando reti di trasporto, visualizzando dati ambientali o sviluppando strumenti di analisi spaziale personalizzati.

---

**Ultimo aggiornamento:** 2025-12-12  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}