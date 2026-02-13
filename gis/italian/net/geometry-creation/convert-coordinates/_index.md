---
date: 2026-02-13
description: Scopri come convertire le coordinate in DMS con Aspose.GIS per .NET.
  Questa guida passo‑passo in C# mostra come convertire latitudine e longitudine,
  gradi decimali in DMS e altro.
linktitle: Convert Coordinates
second_title: Aspose.GIS .NET API
title: Come convertire le coordinate in DMS con Aspose.GIS per .NET
url: /it/net/geometry-creation/convert-coordinates/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come Convertire le Coordinate in DMS con Aspose.GIS

## Introduzione
In questo tutorial imparerai **come convertire le coordinate** in DMS (gradi, minuti, secondi) usando la potente libreria Aspose.GIS per .NET. Che tu abbia bisogno di **c# convert lat long**, generare stringhe di posizione leggibili dall'uomo, o semplicemente esplorare diversi formati di coordinate, questa guida ti accompagna passo passo con spiegazioni chiare e codice C# pronto da eseguire.

## Risposte Rapide
- **Che cosa significa “convert coordinates to DMS”?** Trasforma i valori numerici di latitudine/longitudine nella notazione tradizionale gradi‑minuti‑secondi.  
- **Quale libreria gestisce la conversione?** Aspose.GIS per .NET fornisce la classe `GeoConvert` con supporto integrato ai formati.  
- **È necessaria una licenza per provarla?** È disponibile una versione di prova gratuita; è richiesta una licenza commerciale per l'uso in produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6+.  
- **Posso usare lo stesso codice per altri formati?** Sì—basta cambiare il valore dell'enumerazione `PointFormats` (ad es., `DecimalDegrees`, `GeoRef`).  

## Come Convertire le Coordinate in DMS
Prima di immergersi nel codice, chiariamo perché il DMS è ancora utile. Cartografi, piloti e molti fornitori di dati GIS si affidano al DMS perché è leggibile dall'uomo e si allinea alle mappe tradizionali. Aspose.GIS elimina la necessità di calcoli manuali, permettendoti di concentrarti sulla logica della tua applicazione.

## Che cos'è la conversione di coordinate in DMS?
Convertire le coordinate in DMS riscrive i valori decimali di latitudine e longitudine in un formato come `25°30'00"N 45°30'00"E`. Questa rappresentazione è ampiamente usata in cartografia, navigazione e scambio di dati GIS.

## Perché usare Aspose.GIS per la conversione di coordinate?
- **API tutto‑in‑uno** – Nessuna libreria esterna o calcoli complessi; Aspose.GIS gestisce l'analisi e la formattazione internamente.  
- **Alta precisione** – Gestione accurata dei casi limite come valori negativi e designatori emisferici.  
- **Cross‑platform** – Funziona allo stesso modo su runtime .NET Windows, Linux e macOS.  
- **Estensibile** – Cambia facilmente tra DMS, gradi decimali, gradi‑minuti‑decimali e formati GeoRef.  

## Prerequisiti
Prima di iniziare, assicurati di avere:

1. **Conoscenza di base di C#** – Familiarità con variabili, chiamate di metodo e output console.  
2. **Aspose.GIS installato** – Scarica l'ultimo pacchetto dal [sito web di Aspose.GIS](https://releases.aspose.com/gis/net/).

## Importare gli Spazi dei Nomi
Per prima cosa, importa gli spazi dei nomi necessari per le operazioni GIS:

```csharp
using System;
using Aspose.Gis;
```

## Guida passo‑passo

### Passo 1: Avviare il processo di conversione
Stampiamo un messaggio amichevole così sai che la demo è iniziata.

```csharp
Console.WriteLine($"\n== Start: {nameof(ConvertCoordinate)}");
```

### Passo 2: Convertire in Gradi Decimali  
Anche se l'obiettivo finale è DMS, iniziamo mostrando la rappresentazione decimale originale. Questo dimostra anche il percorso **decimal degrees to dms** che seguirai più tardi.

```csharp
var decimalDegrees = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DecimalDegrees);
Console.WriteLine(decimalDegrees);
```

### Passo 3: Convertire in Gradi Minuti Decimali  
Questo formato (`DD°MM.m'`) è un passaggio intermedio comune quando è necessario *convert lat long degree minutes*.

```csharp
var degreeDecimalMinutes = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeDecimalMinutes);
Console.WriteLine(degreeDecimalMinutes);
```

### Passo 4: Convertire in Gradi Minuti Secondi (DMS)  
Ecco il cuore del nostro tutorial—**convert coordinates to DMS**.

```csharp
var degreeMinutesSeconds = GeoConvert.AsPointText(25.5, 45.5, PointFormats.DegreeMinutesSeconds);
Console.WriteLine(degreeMinutesSeconds);
```

### Passo 5: Convertire in GeoRef  
Per completezza, dimostriamo anche il formato `GeoRef`, utile nei flussi di lavoro di telerilevamento.

```csharp
var geoRef = GeoConvert.AsPointText(25.5, 45.5, PointFormats.GeoRef);
Console.WriteLine(geoRef);
```

## Problemi Comuni e Soluzioni
- **Lettere emisferiche errate** – Assicurati di passare valori positivi per nord/est e negativi per sud/ovest; l'API aggiunge automaticamente il suffisso corretto.  
- **Output vuoto inaspettato** – Verifica che l'assembly `Aspose.Gis` sia referenziato correttamente e che il progetto punti a una versione .NET supportata.  
- **Licenza non trovata** – Posiziona il file di licenza nella radice dell'applicazione o impostalo programmaticamente con `License license = new License(); license.SetLicense("Aspose.GIS.lic");`.  

## Domande Frequenti

**Q: Aspose.GIS è compatibile con altri linguaggi di programmazione?**  
A: Aspose.GIS è principalmente destinato agli sviluppatori .NET, ma è disponibile anche una versione Java.

**Q: Posso provare Aspose.GIS prima di acquistarlo?**  
A: Sì, puoi accedere a una prova gratuita di Aspose.GIS dal [sito web](https://releases.aspose.com/).

**Q: Come posso ottenere supporto per Aspose.GIS?**  
A: Puoi richiedere assistenza dal forum della community Aspose.GIS [qui](https://forum.aspose.com/c/gis/33).

**Q: Sono disponibili licenze temporanee per Aspose.GIS?**  
A: Sì, le licenze temporanee possono essere ottenute dalla [pagina delle licenze temporanee](https://purchase.aspose.com/temporary-license/).

**Q: Dove posso acquistare Aspose.GIS?**  
A: Puoi acquistare Aspose.GIS dalla [pagina di acquisto](https://purchase.aspose.com/buy).

## Conclusione
Seguendo questi passaggi, ora sai come **convertire le coordinate in DMS** e altri formati GIS comuni usando Aspose.GIS per .NET. Questa capacità ti permette di integrare senza sforzo stringhe di posizione leggibili dall'uomo in applicazioni di mappatura, report o qualsiasi flusso di lavoro di dati spaziali. Sentiti libero di sperimentare con diversi valori di latitudine/longitudine ed esplorare gli altri formati offerti dalla classe `GeoConvert`.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}