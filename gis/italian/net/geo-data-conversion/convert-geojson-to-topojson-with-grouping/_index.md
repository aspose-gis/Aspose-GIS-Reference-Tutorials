---
date: 2025-12-06
description: Scopri come convertire GeoJSON in TopoJSON con raggruppamento, impostare
  l'attributo del nome dell'oggetto e raggruppare le feature GeoJSON utilizzando Aspose.GIS
  per .NET.
language: it
linktitle: How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS
second_title: Aspose.GIS .NET API
title: Come convertire GeoJSON in TopoJSON con raggruppamento usando Aspose.GIS
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come convertire GeoJSON in TopoJSON con raggruppamento usando Aspose.GIS

## Introduzione

In questo tutorial passo‑a‑passo imparerai **come convertire file GeoJSON** in TopoJSON raggruppando le feature in base a un attributo scelto. Utilizzare l'API Aspose.GIS .NET rende la conversione veloce, affidabile e completamente controllabile dal tuo codice C#. Che tu stia costruendo un servizio di conversione GeoJSON in ASP.NET o uno strumento GIS desktop, questa guida ti mostra esattamente cosa fare.

## Risposte rapide
- **Quale libreria gestisce la conversione?** Aspose.GIS per .NET  
- **Quanto tempo richiede l'implementazione?** Tipicamente 5‑10 minuti per una configurazione di base  
- **È necessaria una licenza per la produzione?** Sì, è richiesta una licenza commerciale (disponibile prova gratuita)  
- **Posso raggruppare le feature per qualsiasi attributo?** Sì – imposta `ObjectNameAttribute` sul campo che desideri usare per il raggruppamento  
- **.NET Core è supportato?** Assolutamente – l'API funziona con .NET Core, .NET 5/6 e il classico .NET Framework  

## Cos'è GeoJSON e TopoJSON?

GeoJSON è un formato JSON ampiamente usato per codificare elementi geografici come punti, linee e poligoni. TopoJSON estende GeoJSON memorizzando la topologia (segmenti di linea condivisi), riducendo le dimensioni del file e migliorando le prestazioni di rendering per mappe complesse. Convertire tra i due è un passaggio comune quando hai bisogno di dati cartografici compatti per visualizzazioni web.

## Perché raggruppare le feature di GeoJSON?

Il raggruppamento (`group geojson features`) ti consente di organizzare geometrie correlate sotto un unico oggetto nominato nel TopoJSON risultante. Questo è particolarmente utile quando:
- Vuoi creare livelli separati per diverse regioni amministrative.  
- La tua libreria di mappatura front‑end si aspetta oggetti nominati per lo styling o l'interazione.  
- Hai bisogno di ridurre la duplicazione condividendo i confini tra feature adiacenti.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. **Aspose.GIS per .NET** – scarica e installa dal sito ufficiale [qui](https://releases.aspose.com/gis/net/).  
2. **Ambiente di sviluppo** – Visual Studio, Visual Studio Code o qualsiasi IDE che supporti C#.  
3. **File GeoJSON di esempio** – un file contenente le feature che desideri convertire.  

## Importare gli spazi dei nomi

Per prima cosa, includi gli spazi dei nomi necessari nel tuo progetto:

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Guida passo‑a‑passo

### Passo 1: Definire i percorsi dei file

Specifica dove si trova il GeoJSON di origine e dove scrivere il TopoJSON:

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **Suggerimento:** Usa `Path.Combine` per costruire percorsi multipiattaforma se il tuo target è .NET Core.

### Passo 2: Configurare le opzioni di conversione (Impostare l'attributo del nome dell'oggetto)

Crea un'istanza di `ConversionOptions` e indica ad Aspose.GIS come raggruppare le feature:

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

Sostituisci `"group"` con il nome effettivo della proprietà nel tuo GeoJSON che vuoi usare per il **raggruppamento delle feature GeoJSON**. `DefaultObjectName` garantisce che ogni feature finisca in un oggetto TopoJSON, anche se l'attributo è mancante.

### Passo 3: Eseguire la conversione (Convertire GeoJSON in TopoJSON)

Esegui la conversione con una singola chiamata API:

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Al termine, `convertedSampleWithGrouping_out.topojson` conterrà la rappresentazione TopoJSON, con le feature raggruppate secondo l'attributo specificato.

## Problemi comuni e risoluzione

| Sintomo | Causa Probabile | Soluzione |
|---------|----------------|-----------|
| **Tutte le feature finiscono in “unnamed”** | `ObjectNameAttribute` non corrisponde a nessuna proprietà nel GeoJSON | Verifica il nome esatto della proprietà (case‑sensitive) e aggiorna l'opzione |
| **Il file di output è vuoto** | Percorso file errato o permessi di lettura mancanti | Usa percorsi assoluti o assicurati che l'app abbia accesso al file system |
| **La conversione genera `NotSupportedException`** | Tentativo di convertire un GeoJSON con tipi di geometria non supportati (es. GeometryCollection) | Semplifica i dati di origine o aggiorna alla versione più recente di Aspose.GIS |

## Domande frequenti

**D: Posso raggruppare le feature in base a più attributi?**  
R: Sì, puoi concatenare diversi campi in un unico attributo virtuale o eseguire più passaggi di conversione con valori diversi di `ObjectNameAttribute`.

**D: Aspose.GIS è compatibile con ASP.NET Core?**  
R: Assolutamente – la libreria funziona con ASP.NET Core, .NET 5, .NET 6 e il classico .NET Framework.

**D: Posso convertire altri formati geografici oltre a GeoJSON?**  
R: Sì, Aspose.GIS supporta Shapefile, KML, GML, CSV e molti altri formati sia per l'importazione che per l'esportazione.

**D: Aspose.GIS offre una prova gratuita?**  
R: Sì, puoi ottenere una prova gratuita di Aspose.GIS [qui](https://releases.aspose.com/).

**D: Dove posso ottenere supporto per Aspose.GIS?**  
R: Puoi ottenere supporto dal forum della community di Aspose.GIS [qui](https://forum.aspose.com/c/gis/33).

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Ultimo aggiornamento:** 2025-12-06  
**Testato con:** Aspose.GIS per .NET (ultima release)  
**Autore:** Aspose  

---