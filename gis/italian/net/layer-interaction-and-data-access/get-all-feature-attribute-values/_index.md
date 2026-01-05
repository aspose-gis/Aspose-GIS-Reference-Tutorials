---
date: 2026-01-05
description: Scopri come leggere shapefile in C# usando Aspose.GIS per .NET, recuperare
  tutti i valori degli attributi delle feature e esportare gli attributi in modo efficiente.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Leggi Shapefile C# – Ottieni tutti i valori degli attributi delle feature
url: /it/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Recupera tutti i valori degli attributi delle feature

## Introduzione
Benvenuti nel mondo dello sviluppo geospaziale con Aspose.GIS per .NET! In questo tutorial imparerete **come leggere shapefile C#** e recuperare ogni valore di attributo dalle sue feature. Che stiate creando un'app di mappatura o elaborando dati spaziali in batch, padroneggiare l'estrazione degli attributi è fondamentale. Immergiamoci e vediamo il codice in azione.

## Risposte rapide
- **Cosa fa questo codice?** Apre un Shapefile e legge tutti, diversi o i valori degli attributi esportati da ogni feature.  
- **Quale libreria è necessaria?** Aspose.GIS per .NET (compatibile con .NET Framework e .NET Core).  
- **È necessaria una licenza?** Una licenza temporanea funziona per i test; è necessaria una licenza completa per la produzione.  
- **Posso leggere altri formati?** Sì – la stessa API supporta GeoJSON, KML e molti altri.  
- **Come esportare gli attributi?** Usa `feature.GetValuesDump()` per ottenere un array di oggetti flessibile.

## Cos'è “read shapefile C#”?
Leggere uno Shapefile in C# significa aprire il file .shp con una libreria GIS, iterare sulle sue feature vettoriali e accedere ai dati di attributo memorizzati nel file .dbf associato. Aspose.GIS astrae la gestione a basso livello dei file, consentendovi di concentrarvi sui valori di attributo di cui avete bisogno.

## Perché usare Aspose.GIS per leggere gli attributi?
- **API semplice** – metodi intuitivi come `GetValues` e `GetValuesDump`.  
- **Cross‑platform** – funziona su Windows, Linux e macOS con .NET Core.  
- **Supporto ricco di formati** – gestisce Shapefile, GeoJSON, GML e molto altro senza plugin aggiuntivi.  
- **Ottimizzato per le prestazioni** – iterazione veloce su grandi dataset.

## Prerequisiti
Prima di intraprendere questo entusiasmante percorso, assicuratevi di avere i seguenti prerequisiti:
- Aspose.GIS per .NET: scaricate e installate la libreria dalla [pagina di download di Aspose.GIS per .NET](https://releases.aspose.com/gis/net/).
- Ambiente di sviluppo: configurate un ambiente di sviluppo .NET, ad esempio Visual Studio.
- Shapefile: disponete di un Shapefile di esempio (ad es. "InputShapeFile.shp") pronto nella vostra directory dei documenti.

## Importare gli spazi dei nomi
Nel vostro codice C#, iniziate importando gli spazi dei nomi necessari per sfruttare le funzionalità di Aspose.GIS:
```csharp
using System;
using Aspose.Gis;
```

## Passo 1: Impostare la directory dei documenti
```csharp
string dataDir = "Your Document Directory";
```
Sostituite "Your Document Directory" con il percorso effettivo in cui si trova il vostro Shapefile.

## Passo 2: Aprire il VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Questo passaggio consiste nell'aprire lo Shapefile usando Aspose.GIS, specificando il percorso del file e il formato (in questo caso, Shapefile).

## Passo 3: Recuperare tutti i valori degli attributi delle feature
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
Il frammento mostra **come leggere gli attributi** per ogni feature caricandoli in un array a dimensione fissa.

## Passo 4: Recuperare diversi valori degli attributi delle feature
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Qui dimostriamo **come leggere valori di attributi specifici** quando è necessario solo un sottoinsieme di campi.

## Passo 5: Recuperare i valori degli attributi come dump di oggetti
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Questo passaggio finale mostra **come esportare gli attributi** usando `GetValuesDump()`, che restituisce una collezione flessibile che potete ispezionare o serializzare.

## Problemi comuni e soluzioni
- **Mancata corrispondenza della dimensione dell'array** – Assicuratevi che l'array passato a `GetValues` corrisponda al numero di attributi attesi; altrimenti otterrete voci `null`.  
- **File non trovato** – Verificate che `dataDir` punti alla cartella corretta e che il nome dello Shapefile sia scritto esattamente.  
- **Eccezione di licenza** – Se visualizzate un errore di licenza, applicate una licenza temporanea o completa prima di chiamare qualsiasi metodo API.

## Domande frequenti
### Aspose.GIS è compatibile con .NET Core?
Sì, Aspose.GIS è pienamente compatibile con .NET Core, consentendovi di creare applicazioni cross‑platform.

### Posso lavorare con diversi formati di file GIS usando Aspose.GIS?
Assolutamente! Aspose.GIS supporta vari formati, tra cui Shapefile, GeoJSON e molti altri.

### Esiste un forum della community per il supporto di Aspose.GIS?
Sì, potete trovare assistenza e interagire con la community di Aspose.GIS sul [forum di supporto](https://forum.aspose.com/c/gis/33).

### Come posso ottenere una licenza temporanea per Aspose.GIS?
Potete acquisire una licenza temporanea per scopi di test [qui](https://purchase.aspose.com/temporary-license/).

### Dove posso trovare la documentazione dettagliata per Aspose.GIS?
La documentazione completa è disponibile [qui](https://reference.aspose.com/gis/net/).

### Come recupero solo l'attributo “Name” da ogni feature?
Usate `GetValues` con un array di dimensione uno e passate l'indice del campo “Name”, oppure chiamate direttamente `feature["Name"]`.

### Qual è la differenza tra `GetValues` e `GetValuesDump`?
`GetValues` riempie un array pre‑allocato con valori grezzi, mentre `GetValuesDump` restituisce un array di oggetti che può essere enumerato senza conoscere lo schema in anticipo.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-05  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

---