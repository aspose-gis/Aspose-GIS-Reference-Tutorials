---
date: 2026-01-02
description: Scopri come scrivere GeoJSON su uno stream in C# usando Aspose.GIS per
  .NET. Visualizza esempi di GeoJSON in C# e potenzia le tue applicazioni geospaziali.
linktitle: Write GeoJSON to Stream
second_title: Aspose.GIS .NET API
title: Come scrivere GeoJSON su stream con Aspose.GIS per .NET
url: /it/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come scrivere GeoJSON su uno stream

## Introduzione
Se devi **scrivere GeoJSON** direttamente in un flusso di memoria o di file in un'applicazione .NET, sei nel posto giusto. In questo tutorial percorreremo passo passo le operazioni necessarie per scrivere GeoJSON su uno stream usando la libreria Aspose.GIS per .NET e ti mostreremo anche come **visualizzare l'output GeoJSON C#** nella console. Alla fine avrai un modello riutilizzabile da inserire in qualsiasi progetto geospaziale.

## Risposte rapide
- **Cosa significa “scrivere GeoJSON su uno stream”?** Significa serializzare un layer vettoriale nel formato GeoJSON e inviare i byte a un oggetto `Stream` (ad es., `MemoryStream`).  
- **Quale libreria gestisce questa operazione?** Aspose.GIS per .NET fornisce un driver GeoJSON integrato.  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Posso eseguirlo su Linux?** Sì – Aspose.GIS è cross‑platform e funziona su Windows, Linux e macOS.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Cos’è “scrivere GeoJSON” in .NET?
Aspose.GIS ti consente di creare un `VectorLayer`, aggiungere feature e poi serializzare il layer usando il driver `Drivers.GeoJson`. Il driver scrive il testo GeoJSON direttamente in qualsiasi `Stream`, offrendoti il pieno controllo sulla destinazione dei dati (memoria, file, rete, ecc.).

## Perché usare Aspose.GIS per questo compito?
- **Serializzazione a dipendenza zero** – non sono necessarie librerie JSON esterne.  
- **Conformità completa allo standard GeoJSON** – supporta FeatureCollections, proprietà e precisione delle coordinate.  
- **Cross‑platform** – funziona allo stesso modo su Windows, Linux e macOS.  
- **Ottimizzata per le prestazioni** – scrive direttamente sullo stream senza stringhe intermedie.

## Prerequisiti
1. **Aspose.GIS per .NET** – scaricalo [qui](https://releases.aspose.com/gis/net/).  
2. **Directory dei documenti** – scegli dove conservare i file temporanei o gli stream di output.

Ora, immergiamoci nel codice.

## Importare gli spazi dei nomi
Per prima cosa, includi gli spazi dei nomi che ti danno accesso alle classi Aspose.GIS e alle utility I/O standard di .NET:

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Passo 1: Configurare la Directory dei Documenti
Definisci la cartella che ospiterà eventuali file temporanei di cui potresti aver bisogno.

```csharp
string dataDir = "Your Document Directory";
```

Sostituisci `"Your Document Directory"` con il percorso reale sul tuo computer.

## Passo 2: Creare un Memory Stream
Un `MemoryStream` ti permette di tenere il GeoJSON in memoria, ideale per API o quando vuoi restituire i dati direttamente a un client.

```csharp
using (var memoryStream = new MemoryStream())
{
    // Subsequent steps will be placed inside this block
}
```

## Passo 3: Creare un Vector Layer con il driver GeoJSON
All'interno del blocco memory‑stream, crea un `VectorLayer` che utilizza il driver GeoJSON. Questo indica ad Aspose.GIS di serializzare il layer come GeoJSON.

```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Feature creation goes here
}
```

## Passo 4: Definire gli attributi delle Feature
Aggiungi le definizioni di attributi che appariranno come proprietà nell'output GeoJSON finale.

```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Passo 5: Costruire e aggiungere le Feature
Crea due punti di esempio, assegna i valori degli attributi e aggiungili al layer.

```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);

// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Passo 6: Visualizzare l'output GeoJSON C#
Dopo aver popolato il layer, converte i byte dello stream in una stringa UTF‑8 e la scrive sulla console. Questo dimostra come **visualizzare l'output GeoJSON C#**.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Dovresti vedere una FeatureCollection GeoJSON valida stampata nel terminale.

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|---------------|-----------|
| Output vuoto | La posizione dello stream è alla fine al momento della lettura | Imposta `memoryStream.Position = 0;` prima di convertire in stringa. |
| Geometria non valida | Le coordinate sono fuori dai range consentiti | Verifica che la latitudine sia compresa tra -90 e 90, la longitudine tra -180 e 180. |
| Eccezione di licenza | Esecuzione senza licenza valida in produzione | Applica una licenza temporanea o completa usando `License license = new License(); license.SetLicense("Aspose.GIS.lic");` |

## Domande frequenti
### Posso usare Aspose.GIS per .NET sia su Windows che su Linux?
Sì, Aspose.GIS per .NET è compatibile con entrambi i sistemi operativi.  

### È disponibile una versione di prova gratuita?
Assolutamente! Puoi provare la versione gratuita [qui](https://releases.aspose.com/).  

### Dove posso trovare la documentazione dettagliata?
Consulta la documentazione [qui](https://reference.aspose.com/gis/net/).  

### Come posso ottenere una licenza temporanea?
Le licenze temporanee sono disponibili [qui](https://purchase.aspose.com/temporary-license/).  

### Hai bisogno di assistenza o hai altre domande?
Visita il nostro forum di supporto [qui](https://forum.aspose.com/c/gis/33).

## FAQ
**D: Posso scrivere GeoJSON direttamente su un file invece che su un memory stream?**  
R: Sì—sostituisci `MemoryStream` con `FileStream` e fornisci un percorso file. Lo stesso driver funziona.

**D: Come controllo l'indentazione o la formattazione del GeoJSON generato?**  
R: Aspose.GIS scrive JSON compatto per impostazione predefinita. Per un output formattato, elabora la stringa con `JsonSerializerOptions { WriteIndented = true }`.

**D: È possibile aggiungere geometrie più complesse (ad es., poligoni) al layer?**  
R: Certamente. Crea un oggetto `Polygon` o `LineString`, assegnalo a `Feature.Geometry` e aggiungi la feature come mostrato sopra.

**D: I dataset di grandi dimensioni entrano in un `MemoryStream`?**  
R: Per collezioni molto grandi, considera lo streaming diretto su file o l'uso di un `BufferedStream` per evitare un consumo eccessivo di memoria.

**D: Il driver GeoJSON supporta le definizioni CRS (Coordinate Reference System)?**  
R: Sì—imposta la proprietà `SpatialReferenceSystem` del layer prima di aggiungere le feature se ti serve un CRS diverso da WGS84.

## Conclusione
Ora disponi di un modello completo e pronto per la produzione per **scrivere GeoJSON** su qualsiasi stream .NET usando Aspose.GIS. Che tu debba restituire GeoJSON da un'API web, salvarlo su disco o semplicemente visualizzarlo nella console, i passaggi sopra coprono l'intero flusso di lavoro. Esplora ulteriormente la libreria per lavorare con altri formati come Shapefile, KML o GML e continua a costruire applicazioni geospaziali più ricche.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-01-02  
**Testato con:** Aspose.GIS 24.11 per .NET  
**Autore:** Aspose  

---