---
date: 2026-01-13
description: Scopri come aggiungere un layer a un dataset File GDB utilizzando Aspose.GIS,
  con supporto al riferimento spaziale WGS84. Segui questa guida passo‑passo per aggiungere
  un layer a GDB in .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: Riferimento spaziale wgs84 – Aggiungi livello a GDB usando Aspose.GIS
url: /it/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# riferimento spaziale wgs84 – Aggiungere un layer a GDB usando Aspose.GIS

## Introduzione
Pronto a potenziare il tuo flusso di lavoro GIS con Aspose.GIS per .NET? In questo tutorial imparerai **come aggiungere un layer a un dataset File GDB** lavorando con il sistema di coordinate **spatial reference wgs84**. Ti guideremo passo passo, dalla preparazione della cartella dei dati alla convalida del layer appena creato, così potrai iniziare a manipolare i dati geografici con sicurezza.

## Risposte rapide
- **Qual è il sistema di coordinate principale utilizzato?** spatial reference wgs84 (WGS 84)  
- **Quale libreria fornisce l'API?** Aspose.GIS per .NET  
- **Ho bisogno di una licenza per i test?** Sì – è disponibile una licenza temporanea Aspose.  
- **Posso aggiungere attributi al nuovo layer?** Assolutamente, puoi definire qualsiasi numero di attributi delle feature.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Cos'è spatial reference wgs84?
Il spatial reference wgs84 (World Geodetic System 1984) è il sistema di coordinate geografiche più ampiamente utilizzato. Definisce latitudine e longitudine in gradi e funge da CRS predefinito per molti dataset GIS, incluso quello che creeremo in questa guida.

## Perché usare Aspose.GIS per aggiungere un layer?
- **Nessuna dipendenza esterna:** Funziona subito fuori dalla scatola con codice .NET puro.  
- **Controllo totale sullo schema:** Puoi definire attributi personalizzati e tipi di geometria.  
- **Cross‑platform:** Compatibile con runtime Windows, Linux e macOS.  
- **Licenza robusta:** Le licenze temporanee ti consentono di valutare rapidamente prima di impegnarti.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Libreria Aspose.GIS per .NET: Scarica e installa la libreria dalla [Documentazione Aspose.GIS per .NET](https://reference.aspose.com/gis/net/).  
- Directory dei documenti: Crea una cartella dedicata sul tuo computer per memorizzare i file GIS.

## Importare gli spazi dei nomi
Aggiungi le istruzioni `using` necessarie al tuo progetto C# così da poter accedere alle classi Aspose.GIS:

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Copia della directory
Per prima cosa, duplica la cartella che contiene il dataset GDB originale. Mantenere una copia protegge i dati sorgente mentre sperimenti.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Step 2: Apri il dataset e verifica la capacità di creazione
Apri il dataset appena copiato e conferma che può creare nuovi layer. La proprietà `CanCreateLayers` dovrebbe restituire **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Step 3: Crea e popola un nuovo layer con spatial reference wgs84
Ora creiamo un layer chiamato **data** e impostiamo esplicitamente il suo riferimento spaziale su **Wgs84**. Aggiungiamo anche un semplice attributo chiamato **Name** e inseriamo una feature punto.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Step 4: Apri e valida il layer aggiunto
Infine, apri il layer appena creato e verifica il suo contenuto. La console mostrerà che il layer contiene una feature e che l'attributo **Name** corrisponde a quanto impostato.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Problemi comuni e suggerimenti
- **Percorso errato:** Assicurati che `dataDir` termini con un separatore di percorso (`/` o `\`) in modo che le stringhe concatenate formino percorsi file validi.  
- **Errori di licenza:** Se visualizzi avvisi di licenza, applica una licenza temporanea dal portale Aspose prima di eseguire il codice.  
- **Mancata corrispondenza CRS:** Quando apri il layer in un altro strumento GIS, verifica che lo strumento riconosca WGS 84 (EPSG:4326) come sistema di coordinate.

## Domande frequenti
### Q: Posso usare Aspose.GIS per .NET con altre librerie GIS?
Aspose.GIS per .NET è progettato per funzionare in modo indipendente, ma può essere integrato con altre librerie per funzionalità aggiuntive.  

### Q: È disponibile una licenza temporanea per scopi di test?
Sì, puoi ottenere una licenza temporanea da [qui](https://purchase.aspose.com/temporary-license/) per test e valutazione.  

### Q: Quali sistemi di riferimento spaziale supporta Aspose.GIS per .NET?
Aspose.GIS per .NET supporta un'ampia gamma di sistemi di riferimento spaziale, offrendo flessibilità nella gestione dei dati geografici.  

### Q: Posso contribuire alla community di Aspose.GIS?
Assolutamente! Partecipa alle discussioni e condividi le tue esperienze sul [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).  

### Q: Dove posso trovare la documentazione dettagliata per Aspose.GIS per .NET?
Esplora la documentazione completa [qui](https://reference.aspose.com/gis/net/) per informazioni approfondite su Aspose.GIS per .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-01-13  
**Testato con:** Aspose.GIS per .NET (ultima versione stabile)  
**Autore:** Aspose