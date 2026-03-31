---
date: 2025-12-21
description: Scopri come creare un layer vettoriale, impostare la tolleranza di linearizzazione
  e aggiungere una feature al layer usando Aspose.GIS per .NET. Segui questa guida
  passo‑passo per esportare file GeoJSON.
linktitle: Set Linearization Tolerance
second_title: Aspose.GIS .NET API
title: Creare un layer vettoriale e impostare la tolleranza di linearizzazione usando
  Aspose.GIS per .NET
url: /it/net/geometry-processing/set-linearization-tolerance/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea Vector Layer e imposta Tolleranza di linearizzazione utilizzando Aspose.GIS per .NET

## Introduzione
Se hai bisogno di **creare file vettoriale layer**, controllare la precisione delle curve ed esportare il risultato come documento GeoJSON, Aspose.GIS per .NET lo rende semplice. Codice pulito e pronto per la produzione.

## Risposte rapide
- **Cosa significa “crea layer vettoriale”?** Crea un nuovo dataset GIS vettoriale (ad es., un file GeoJSON) che può memorizzare geometrie e attributi.
- **Come impostare la tolleranza?** Usa la proprietà `LinearizationTolerance` di `GeoJsonOptions`.
- **Posso esportare un file GeoJSON?** Sì—basta creare un `VectorLayer` con il driver `Drivers.GeoJson`.
- **Ho bisogno di una licenza?** Uso non autorizzato della licenza.
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Cos'è "crea livello vettoriale"?
Crea un significato di livello vettoriale nel nuovo contenitore GIS (come un file GeoJSON) che può contenere funzionalità geometriche come punti, linee e poligoni. Questo layer divent il target per qualsiasi geometria che costruisci e per qualsiasi attributo che aggiungi.

## Perché configurare le opzioni GeoJSON?
Configurando geoJSON—linearizzazione tolleranza**—assicura geometria curva (ad es., `CircularString`) siano approssimate e una precisione soddisfa i requisiti di accuratezza della tua applicazione. Questo passaggio è cruciale quando successivamente **export GeoJSON file** per l'uso in mappe web o analisi spaziali.

## Prerequisiti
1. **Visual Studio** installato (qualsiasi versione recente).
2. **Licenza Aspose.GIS** (O una chiave di valutazione temporanea).
3. Libreria **Aspose.GIS for .NET** scaricata e referenziata nel tuo progetto.
4. Familiarità di base con **C#**.

## Importa spazi dei nomi
Per prima cosa, importa gli spazi dei nomi ricchi cosìil compilatore sa dove trovare le classi GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.GeoJson;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Guida passo passo

### Passaggio 1: Configurare le opzioni GeoJSON (come impostare la tolleranza)
Creeremo un oggetto `GeoJsonOptions` e diremo ad Aspose.GIS quanto deve essere vicina la geometria linearizzata alla curva originale.

```csharp
var options = new GeoJsonOptions
{
    // linearized geometry must be within 1e-4 from curve geometry
    LinearizationTolerance = 1e-4,
};
```

### Passaggio 2: Definire il percorso di output (come esportare GeoJSON)
Specifica dove verrà salvato il file risultante. Sostituisci il segnaposto con la tua cartella reale.

```csharp
string path = "Your Document Directory" + "SpecifyLinearizationTolerance_out.json";
```

### Passaggio 3: **Creare un layer vettoriale** con le opzioni configurate
Ora **Create Vector Layer** usando il metodo `VectorLayer.Create`. Il blocco `using` garantisce il corretto rilascio delle risorse.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.GeoJson, options))
{
    // Your code here
}
```

### Passaggio 4: Costruire una geometria (ad esempio, una stringa circolare)
Qui costruiamo una geometria di esempio—un `CircularString`. Puoi sostituirla con qualsiasi WKT valido.

```csharp
var curveGeometry = Geometry.FromText("CircularString (0 0, 1 1, 2 0)");
```

### Passaggio 5: **Aggiungere una feature al layer** e salvare
Infine, creiamo una feature, assegniamo la geometria e la aggiungiamo al layer. Questo è il nucleo dell'operazione **Add Feature to Layer**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = curveGeometry;
layer.Add(feature);
```

Quando il blocco `using` termina, il layer viene scritto automaticamente nel file definito in `path`, fornendoti un file GeoJSON pronto all'uso.

## Problemi e suggerimenti comuni
- **Percorso errato** – Assicurati che la directory esista e che tu abbia i permessi di scrittura.
- **Tolleranza troppo bassa** – Impostare `LinearizationTolerance` a un valore molto piccolo può aumentare drasticamente la dimensione del file. Regola in base alle tue esigenze di accuratezza.
- **Errori di licenza** – Se vedi avvisi di licenza, verifica che il file di licenza sia caricato correttamente prima di qualsiasi chiamata a Aspose.GIS.

## Domande frequenti

**D: Aspose.GIS per .NET è compatibile con altri framework .NET?**
R: Sì, funziona e .NET Framework, .NET Core e .NET 5/6/7.

**D: Posso usare Aspose.GIS in progetti commerciali?**
R: Assolutamente. Una licenza commerciale rimuove tutte le restrizioni di valutazione.

**D: Aspose.GIS supporta altri formati GIS oltre a GeoJSON?**
R: Sì, supporta Shapefile, KML, GML e molti altri.

**D: È un problema?**
A: È il posto migliore dove stare ad Aspose.

**D: Dove posso ottenere supporto?**
A: Usa il tuo forum come guida.

##Conclusione
Seguendo questi passaggi ora sai come **creare layer vettoriale**, configurare la tolleranza Aggiungi funzionalità al layer e crea nuove funzionalità in **esporta file GeoJSON**. Geometrie e geometrie riconducibili a massimo Aspose.GIS nei tuoi progetti GIS .NET.

---

**Ultimo aggiornamento:** 21-12-2025
**Testato con:** Aspose.GIS 24.11 per .NET
**Autore:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
