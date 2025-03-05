---
title: Crea un nuovo set di dati GDB del file
linktitle: Crea un nuovo set di dati GDB del file
second_title: API Aspose.GIS .NET
description: Esplora Aspose.GIS per .NET per creare e gestire facilmente set di dati GIS. Scaricalo ora per uno sviluppo geospaziale senza interruzioni. #Aspose #GIS
type: docs
weight: 10
url: /it/net/layer-management/create-new-file-gdb-dataset/
---
## introduzione
Nel regno dello sviluppo geospaziale, Aspose.GIS per .NET si distingue come un potente toolkit per la gestione e la manipolazione dei dati del Sistema Informativo Geografico (GIS). Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato il tuo viaggio nel GIS, questo tutorial ti guiderà attraverso il processo di creazione di un nuovo set di dati File Geodatabase (GDB) utilizzando Aspose.GIS per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
-  Aspose.GIS per .NET: assicurati di avere la libreria Aspose.GIS per .NET installata. Puoi scaricarlo da[Pagina di download di Aspose.GIS per .NET](https://releases.aspose.com/gis/net/).
- Ambiente di sviluppo: configura il tuo ambiente di sviluppo con un IDE compatibile, come Visual Studio, e acquisisci una conoscenza di base della programmazione .NET.
- Directory dei documenti: sostituisci "La tua directory dei documenti" nello snippet di codice con il percorso appropriato in cui desideri archiviare il set di dati GDB.
- Familiarità con C#: questo tutorial presuppone che tu abbia familiarità con il linguaggio di programmazione C#.
## Importa spazi dei nomi
Nei passaggi iniziali, importa gli spazi dei nomi necessari per sfruttare la funzionalità Aspose.GIS nella tua applicazione .NET:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Passaggio 1: crea un nuovo set di dati GDB su file
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Uscita: 0
    // Continua con i passaggi successivi...
}
```
 Spiegazione: in questo passaggio creiamo un nuovo set di dati GDB utilizzando il file`Dataset.Create` metodo. Specifichiamo il percorso e il driver (FileGdb) per creare un File Geodatabase. L'output della console mostra il conteggio dei livelli iniziale, che a questo punto è zero.
## Passaggio 2: crea e compila il livello_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Spiegazione: questo passaggio prevede la creazione di un livello denominato "livello_1" all'interno del set di dati. Definisce un attributo denominato "valore" di tipo intero e popola il layer con dieci feature, ciascuna avente una geometria puntuale.
## Passaggio 3: crea e popola il livello_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Spiegazione: qui creiamo un secondo layer denominato "layer_2" e aggiungiamo un singolo elemento con una geometria di stringa di linea.
## Passaggio 4: controlla il conteggio dei livelli aggiornati
```csharp
Console.WriteLine(dataset.LayersCount); // Uscita: 2
```
Spiegazione: infine, controlliamo il conteggio dei livelli aggiornati dopo aver aggiunto i due livelli. In questo caso, l'output dovrebbe essere 2.
## Conclusione
Congratulazioni! Hai creato con successo un nuovo set di dati File GDB e lo hai popolato con livelli utilizzando Aspose.GIS per .NET. Questa esercitazione fornisce una conoscenza fondamentale dell'uso dei dati geospaziali in un ambiente .NET.
## Domande frequenti
### D: Posso utilizzare Aspose.GIS per .NET con altre librerie GIS?
Aspose.GIS per .NET è un toolkit autonomo; è tuttavia possibile integrarlo con altre librerie .NET per migliorarne la funzionalità.
### D: Esiste un forum della community per il supporto di Aspose.GIS?
 Sì, puoi trovare supporto e discussioni su[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### D: Come posso ottenere una licenza temporanea per Aspose.GIS?
 Visitare il[Licenza temporanea](https://purchase.aspose.com/temporary-license/) pagina per informazioni su come ottenere una licenza temporanea.
### D: Sono disponibili ulteriori esempi e documentazione?
 Esplorare la[Documentazione Aspose.GIS](https://reference.aspose.com/gis/net/) per ulteriori esempi e informazioni dettagliate.
### D: Dove posso acquistare Aspose.GIS per .NET?
 È possibile acquistare Aspose.GIS per .NET su[pagina di acquisto](https://purchase.aspose.com/buy).