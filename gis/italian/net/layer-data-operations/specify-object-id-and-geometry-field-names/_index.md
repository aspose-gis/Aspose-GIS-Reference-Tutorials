---
date: 2026-01-02
description: Scopri come aggiungere una feature puntuale impostando i nomi dei campi
  e leggendo l'ID dell'oggetto con Aspose.GIS per .NET. Guida passo‑passo per gli
  sviluppatori.
linktitle: Specify Object ID and Geometry Field Names
second_title: Aspose.GIS .NET API
title: Aggiungi feature puntuale e specifica i nomi dei campi Object ID e Geometry
url: /it/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere una feature punto e specificare i nomi dei campi Object ID e Geometry

## Introduzione
Intraprendere un viaggio nel mondo dei Geographic Information Systems (GIS) utilizzando Aspose.GIS per .NET apre un mondo di possibilità per sviluppatori e appassionati. In questo tutorial, **imparerai come aggiungere una feature punto** impostando anche **i nomi dei campi** e **leggere i valori dell'object id**, offrendoti il pieno controllo sui tuoi dati spaziali.

## Risposte rapide
- **Qual è lo scopo principale di questa guida?** Mostrare come aggiungere una feature punto e configurare i nomi dei campi Object ID e Geometry.  
- **Quale libreria viene utilizzata?** Aspose.GIS per .NET.  
- **È necessaria una licenza?** È disponibile una versione di prova gratuita; è necessaria una licenza per la produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Posso leggere l'Object ID dopo l'inserimento?** Sì – il tutorial dimostra come leggere l'object id dal layer.

## Prerequisiti
- Aspose.GIS per .NET: Scarica e installa la libreria da [qui](https://releases.aspose.com/gis/net/).
- Directory dei documenti: Configura una cartella per i tuoi documenti per memorizzare i geodatabase.
- Ambiente .NET: Assicurati di avere un ambiente .NET funzionante.

## Importare gli spazi dei nomi
Per iniziare, è necessario importare gli spazi dei nomi necessari nel tuo progetto. Questi spazi dei nomi forniscono le classi e i metodi essenziali per interagire con Aspose.GIS per .NET.

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Passo 1: Aggiungere una feature punto e specificare i nomi dei campi Object ID e Geometry
In questo passo, imparerai come configurare i nomi dei campi Object ID e Geometry per i tuoi dati GIS. Questo è fondamentale per una gestione efficiente dei dati e per poter **leggere l'object id** in seguito.

### Passo 1.1: Impostare la directory dei documenti
Inizia definendo il percorso della tua directory dei documenti:

```csharp
string dataDir = "Your Document Directory";
```

### Passo 1.2: Creare un GeoDatabase e definire le opzioni
Crea un GeoDatabase con i **nomi dei campi** desiderati per Object ID e Geometry:

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

### Passo 1.3: Creare e aggiungere un layer
Crea un layer all'interno del GeoDatabase e aggiungi una feature che rappresenta una geometria punto:

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

### Passo 1.4: Aprire e recuperare i dati dal layer
Apri il layer e recupera la feature appena aggiunta. Questo dimostra come **leggere l'object id** dal dataset:

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Perché impostare nomi di campo personalizzati?
Personalizzare i nomi dei campi Object ID e Geometry ti offre flessibilità quando integri con database esistenti o quando rispetti le convenzioni di denominazione richieste dalle applicazioni a valle. Inoltre rende i dati più auto‑descrittivi, semplificando la manutenzione e la collaborazione.

## Problemi comuni e risoluzione
- **Directory mancante** – Assicurati che `dataDir` punti a una cartella esistente; altrimenti, `Dataset.Create` genererà un'eccezione.  
- **Conflitti di nome campo** – Se un campo con lo stesso nome esiste già nel geodatabase, la creazione fallirà. Scegli nomi unici.  
- **Mancata corrispondenza del riferimento spaziale** – Assicurati sempre che il sistema di riferimento spaziale (ad es., WGS84) corrisponda ai dati che intendi memorizzare.

## Conclusione
Congratulazioni! Hai appreso con successo come **aggiungere una feature punto**, **impostare i nomi dei campi** e **leggere l'object id** usando Aspose.GIS per .NET. Questa base ti permette di costruire applicazioni GIS robuste e gestire i dati spaziali con fiducia.

## Domande frequenti
### Q: Posso usare Aspose.GIS per .NET nelle mie applicazioni web?
A: Sì, Aspose.GIS per .NET è adatto sia per applicazioni desktop che web, fornendo capacità geospaziali versatili.

### Q: È disponibile una versione di prova prima dell'acquisto?
A: Sì, puoi esplorare le funzionalità di Aspose.GIS per .NET con una versione di prova gratuita disponibile [qui](https://releases.aspose.com/).

### Q: Come posso ottenere una licenza temporanea per Aspose.GIS per .NET?
A: Puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/) per scopi di valutazione.

### Q: Quali sistemi di riferimento spaziale supporta Aspose.GIS per .NET?
A: Aspose.GIS per .NET supporta vari sistemi di riferimento spaziale, offrendo flessibilità per diversi dataset geografici.

### Q: Dove posso cercare aiuto o discutere domande relative ad Aspose.GIS?
A: Visita il forum Aspose.GIS [qui](https://forum.aspose.com/c/gis/33) per supporto e discussioni.

## Ulteriori domande frequenti

**Q: Posso cambiare il campo Object ID dopo che il layer è stato creato?**  
A: No. Il nome del campo è definito al momento della creazione del layer; è necessario ricreare il layer con un nuovo oggetto `FileGdbOptions` per modificarlo.

**Q: Come recupero altri valori di attributo oltre all'Object ID?**  
A: Usa `feature.GetValue<T>("FieldName")` dove `FieldName` è il nome dell'attributo che desideri leggere.

**Q: È possibile aggiungere più feature punto in un unico batch?**  
A: Sì. Itera sui tuoi dati, costruisci una feature per ogni punto, imposta la sua geometria e chiama `layer.Add(feature)` all'interno dello stesso blocco `using`.

**Q: Aspose.GIS supporta altri tipi di geometria?**  
A: Assolutamente. Puoi lavorare con `LineString`, `Polygon`, `MultiPoint` e altri creando gli oggetti geometria appropriati.

**Q: Cosa succede se provo a leggere un Object ID che non esiste?**  
A: Accedere a un indice fuori intervallo (ad es., `layer[10]` quando esiste solo una feature) genererà un `IndexOutOfRangeException`. Controlla sempre prima `layer.Count`.

---

**Ultimo aggiornamento:** 2026-01-02  
**Testato con:** Aspose.GIS per .NET 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}