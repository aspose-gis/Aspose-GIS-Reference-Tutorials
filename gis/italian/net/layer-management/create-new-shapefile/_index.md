---
title: Crea nuovo file di forma
linktitle: Crea nuovo file di forma
second_title: API Aspose.GIS .NET
description: Scopri come creare un nuovo shapefile utilizzando Aspose.GIS per .NET. Segui la nostra guida passo passo e sblocca il potere della manipolazione dei dati spaziali.
weight: 12
url: /it/net/layer-management/create-new-shapefile/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea nuovo file di forma

## introduzione
Se stai approfondendo lo sviluppo di sistemi informativi geografici (GIS) con .NET, Aspose.GIS è la soluzione ideale. Questa potente libreria consente agli sviluppatori di lavorare senza problemi con i dati spaziali e in questo tutorial ti guideremo attraverso il processo di creazione di un nuovo shapefile utilizzando Aspose.GIS per .NET.
## Prerequisiti
Prima di passare al tutorial, assicurati di disporre dei seguenti prerequisiti:
- Conoscenza base del linguaggio di programmazione C#.
- Visual Studio installato sul tuo computer.
-  Aspose.GIS per la libreria .NET. Puoi scaricarlo[Qui](https://releases.aspose.com/gis/net/).
## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari per sfruttare la funzionalità di Aspose.GIS:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Passaggio 1: imposta il tuo progetto
Inizia creando un nuovo progetto C# in Visual Studio e includi la libreria Aspose.GIS.
## Passaggio 2: definire la directory dei documenti
```csharp
string dataDir = "Your Document Directory";
```
Sostituisci "La tua directory dei documenti" con il percorso effettivo in cui desideri salvare il tuo nuovo shapefile.
## Passaggio 3: crea un vettoreLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //aggiungere attributi prima di aggiungere funzionalità
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Questo segmento di codice imposta il livello vettoriale e definisce gli attributi per le tue funzionalità.
## Passaggio 4: aggiungi funzionalità
### Caso 1: imposta i valori individualmente
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### Caso 2: imposta nuovi valori per tutti gli attributi
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Conclusione
 Congratulazioni! Hai creato con successo un nuovo shapefile utilizzando Aspose.GIS per .NET. Questo tutorial ha trattato le nozioni di base sulla configurazione del progetto, sulla definizione degli attributi e sull'aggiunta di funzionalità. Mentre esplori ulteriormente, fai riferimento a[documentazione](https://reference.aspose.com/gis/net/) per caratteristiche e funzionalità avanzate.
## Domande frequenti
### D: Posso utilizzare Aspose.GIS con altri linguaggi di programmazione?
Aspose.GIS supporta principalmente .NET, ma sono disponibili anche versioni per Java.
### D: È disponibile una prova gratuita?
 Sì, puoi accedere alla prova gratuita[Qui](https://releases.aspose.com/).
### D: Dove posso trovare supporto per Aspose.GIS?
 Visitare il[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per il supporto e le discussioni della comunità.
### D: Come posso ottenere una licenza temporanea?
 Ottieni la tua licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### D: Dove posso acquistare Aspose.GIS per .NET?
 Puoi acquistare la libreria[Qui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
