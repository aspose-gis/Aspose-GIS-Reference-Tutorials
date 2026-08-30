---
date: 2026-08-18
description: Converti i decimal degrees in dms usando Aspose.GIS for .NET. Questa
  guida passo‑passo in C# mostra come convertire latitude/longitude, decimal degrees
  in dms e altro.
keywords:
- decimal degrees to dms
- convert coordinates dms
- gis coordinate conversion
- convert lat long dms
- c# convert lat long
lastmod: 2026-08-18
linktitle: Converti coordinate
og_description: Conversione da decimal degrees a dms semplificata con Aspose.GIS for
  .NET. Scopri come trasformare i valori latitude‑longitude in formato DMS in minuti.
og_image_alt: Guide showing decimal degrees to DMS conversion using Aspose.GIS in
  C#
og_title: Converti i decimal degrees in dms con Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  headline: How to convert decimal degrees to dms with Aspose.GIS for .NET
  type: TechArticle
- description: Convert decimal degrees to dms using Aspose.GIS for .NET. This step‑by‑step
    C# guide shows how to convert latitude/longitude, decimal degrees to dms and more.
  name: How to convert decimal degrees to dms with Aspose.GIS for .NET
  steps:
  - name: start the conversion process
    text: We print a friendly message so you know the demo has begun.
  - name: convert to decimal degrees
    text: Even though the final goal is DMS, we start by showing the original decimal
      representation. This also demonstrates the **decimal degrees to dms** path you’ll
      later follow.
  - name: convert to degree decimal minutes
    text: This format (`DD°MM.m'`) is a common intermediate step when you need to
      **convert lat long degree minutes**.
  - name: convert to degree minutes seconds (dms)
    text: Here’s the core of our tutorial—**convert coordinates to dms**.
  - name: convert to GeoRef
    text: For completeness, we also demonstrate the `GeoRef` format, useful in remote‑sensing
      workflows.
  type: HowTo
- questions:
  - answer: Aspose.GIS primarily targets .NET developers, but a Java version is also
      available.
    question: Is Aspose.GIS compatible with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.GIS from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.GIS before purchasing?
  - answer: You can seek assistance from the Aspose.GIS community forum [here](https://forum.aspose.com/c/gis/33).
    question: How can I get support for Aspose.GIS?
  - answer: Yes, temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.GIS?
  - answer: You can purchase Aspose.GIS from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert coordinates
- Aspose.GIS
- .NET GIS processing
title: Come convertire i decimal degrees in dms con Aspose.GIS for .NET
url: /it/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come convertire gradi decimali in dms con Aspose.GIS

## Introduzione
In questo tutorial imparerai **come convertire gradi decimali in dms** usando la potente libreria Aspose.GIS per .NET. Che tu abbia bisogno di **c# convert lat long**, generare stringhe di posizione leggibili per report, o semplicemente esplorare diversi formati di coordinate, questa guida ti accompagna passo dopo passo con spiegazioni chiare e snippet C# pronti all'uso.

## Risposte rapide
- **Cosa significa “convertire coordinate in dms”?** Trasforma i valori numerici di latitudine/longitudine in notazione tradizionale gradi‑minuti‑secondi.  
- **Quale libreria gestisce la conversione?** Aspose.GIS per .NET fornisce la classe `GeoConvert` con supporto integrato ai formati.  
- **È necessaria una licenza per provarla?** È disponibile una prova gratuita; per l'uso in produzione è richiesta una licenza commerciale.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6+.  
- **Posso usare lo stesso codice per altri formati?** Sì—basta cambiare il valore dell'enum `PointFormats` (ad es., `DecimalDegrees`, `GeoRef`).  

## Che cos’è la conversione di coordinate in dms?
Convertire le coordinate in DMS riscrive i valori decimali di latitudine e longitudine in un formato come `25°30'00"N 45°30'00"E`. Il processo suddivide ogni grado decimale in gradi interi, minuti (un sessantesimo di grado) e secondi (un sessantesimo di minuto), aggiungendo poi l’indicatore di emisfero appropriato (N, S, E, W). Questa forma leggibile è essenziale per molti dataset legacy e per comunicare posizioni precise senza ricorrere alla notazione decimale.

## Perché usare Aspose.GIS per la conversione di coordinate?
Aspose.GIS supporta **oltre 50 formati di input e output** e può elaborare file GIS di centinaia di pagine senza caricare l’intero dataset in memoria. L'API garantisce precisione sub‑millimetrica per casi particolari come valori negativi e designatori emisferici, ed è eseguita in modo coerente su runtime .NET Windows, Linux e macOS.

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Conoscenza di base di C#** – familiarità con variabili, chiamate di metodo e output su console.  
2. **Aspose.GIS installato** – scarica il pacchetto più recente dal [sito web di Aspose.GIS](https://releases.aspose.com/gis/net/). Puoi anche esplorare il sito principale delle release di Aspose al [sito delle release di Aspose](https://releases.aspose.com/).  

## Importa spazi dei nomi
Prima, importa gli spazi dei nomi richiesti per le operazioni GIS:

Il segnaposto Import Namespaces rimane invariato.

## Guida passo‑paso

### Che cos’è la classe GeoConvert?
La classe `GeoConvert` fornisce metodi statici per convertire tra formati di coordinate come gradi decimali, DMS e GeoRef. Include overload che accettano valori numerici grezzi o oggetti `Point` e restituiscono stringhe formattate o nuove istanze `Point`. Gestendo casi limite come coordinate negative e arrotondamenti, la classe garantisce che l'output rispetti le specifiche GIS standard, semplificando l'integrazione in qualsiasi applicazione di mappatura .NET.

### Passo 1: avviare il processo di conversione
Stampiamo un messaggio amichevole così sai che la demo è iniziata.

```csharp
using System;
using Aspose.Gis;
```

### Passo 2: convertire in gradi decimali
Anche se l’obiettivo finale è DMS, iniziamo mostrando la rappresentazione decimale originale. Questo dimostra anche il percorso **decimal degrees to dms** che seguirai successivamente.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Passo 3: convertire in gradi minuti decimali
Questo formato (`DD°MM.m'`) è un passaggio intermedio comune quando devi **convert lat long degree minutes**.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Passo 4: convertire in gradi minuti secondi (dms)
Ecco il cuore del nostro tutorial—**convert coordinates to dms**.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Passo 5: convertire in GeoRef
Per completezza, dimostriamo anche il formato `GeoRef`, utile nei flussi di lavoro di telerilevamento.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

## Problemi comuni e soluzioni
- **Lettere emisferiche errate** – Assicurati di passare valori positivi per nord/est e negativi per sud/ovest; l'API aggiunge automaticamente il suffisso corretto.  
- **Output vuoto inatteso** – Verifica che l'assembly `Aspose.Gis` sia referenziato correttamente e che il progetto punti a una versione .NET supportata.  
- **Licenza non trovata** – Posiziona il file di licenza nella radice dell'applicazione o impostalo programmaticamente con `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.

## Domande frequenti

**D: Aspose.GIS è compatibile con altri linguaggi di programmazione?**  
R: Aspose.GIS è principalmente rivolto a sviluppatori .NET, ma è disponibile anche una versione Java.

**D: Posso provare Aspose.GIS prima di acquistarlo?**  
R: Sì, puoi accedere a una prova gratuita di Aspose.GIS dal [sito web](https://releases.aspose.com/).

**D: Come posso ottenere supporto per Aspose.GIS?**  
R: Puoi chiedere assistenza nel forum della community di Aspose.GIS [qui](https://forum.aspose.com/c/gis/33).

**D: Sono disponibili licenze temporanee per Aspose.GIS?**  
R: Sì, le licenze temporanee possono essere ottenute dalla [pagina delle licenze temporanee](https://purchase.aspose.com/temporary-license/).

**D: Dove posso acquistare Aspose.GIS?**  
R: Puoi acquistare Aspose.GIS dalla [pagina di acquisto](https://purchase.aspose.com/buy).

## Conclusione
Seguendo questi passaggi, ora sai **come convertire gradi decimali in dms** e altri formati GIS comuni usando Aspose.GIS per .NET. Questa capacità ti consente di integrare senza sforzo stringhe di posizione leggibili in applicazioni di mappatura, report o qualsiasi flusso di lavoro di dati spaziali. Sentiti libero di sperimentare con diversi valori di latitudine/longitudine ed esplorare gli altri formati offerti dalla classe `GeoConvert`.

---

**Ultimo aggiornamento:** 2026-08-18  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose  

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Tutorial correlati

- [Come creare la geometria Point e ottenere il tipo di geometria con Aspose.GIS per .NET](/gis/net/geometry-analysis/get-geometry-type/)
- [Come convertire GeoJSON – Aspose.GIS per .NET](/gis/net/geo-data-conversion/)
- [Creare geometria MultiPoint .NET con Aspose.GIS](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}