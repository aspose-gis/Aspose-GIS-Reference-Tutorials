---
title: Estrai funzionalità in GeoJSON
linktitle: Estrai funzionalità in GeoJSON
second_title: API Aspose.GIS .NET
description: Esplora la guida passo passo sull'utilizzo di Aspose.GIS per .NET per estrarre funzionalità in GeoJSON. Sfrutta la potenza del GIS con facilità! #Aspose #GIS
weight: 23
url: /it/net/layer-management/extract-features-to-geojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Estrai funzionalità in GeoJSON

## introduzione
Benvenuti nel nostro tutorial passo passo sull'estrazione di funzionalità in GeoJSON utilizzando Aspose.GIS per .NET! Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato il tuo viaggio nella programmazione GIS, questa guida ti guiderà attraverso il processo, assicurandoti di sfruttare tutta la potenza di Aspose.GIS per .NET.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere i seguenti prerequisiti:
-  Aspose.GIS per .NET: assicurati di avere la libreria installata. In caso contrario, puoi scaricarlo da[Aspose.GIS per la pagina .NET](https://releases.aspose.com/gis/net/).
-  Dati Shapefile: avere uno Shapefile pronto per l'input. Se hai bisogno di dati di esempio, puoi trovarli nel file[Documentazione Aspose.GIS](https://reference.aspose.com/gis/net/).
- Ambiente .NET: configura un ambiente .NET per eseguire il codice fornito.
- Directory dei documenti: definisci il percorso della directory dei documenti nello snippet di codice.
Ora che hai tutto a posto, iniziamo a estrarre le funzionalità in GeoJSON!
## Importa spazi dei nomi
Innanzitutto, includi gli spazi dei nomi necessari nel tuo codice:
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Questi spazi dei nomi sono essenziali per lavorare con le funzionalità Aspose.GIS.
## Passaggio 1: aprire il file di forma di input
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Il tuo codice per l'elaborazione dello shapefile di input va qui
}
```
 Aprire lo Shapefile di input utilizzando il file`VectorLayer.Open` metodo.
## Passaggio 2: crea GeoJSON di output
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Il tuo codice per creare l'output GeoJSON va qui
}
```
 Crea l'output GeoJSON utilizzando il file`VectorLayer.Create` metodo.
## Passaggio 3: copiare gli attributi
```csharp
outputLayer.CopyAttributes(inputLayer);
```
 Copia gli attributi dal livello di input al livello di output utilizzando il file`CopyAttributes` metodo.
## Passaggio 4: funzionalità del processo
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Il tuo codice per l'elaborazione di ciascuna funzione di input va qui
}
```
Scorri ciascuna funzionalità nel livello di input ed elaborale individualmente.
## Passaggio 5: filtra le funzionalità per data
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Filtra le funzionalità in base a una condizione di data. In questo esempio vengono saltati gli elementi con data di nascita precedente al 1982.
## Passaggio 6: costruire una nuova funzionalità
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Costruisci una nuova feature per il layer di output, copiando la geometria e i valori dalla feature di input.
Congratulazioni! Hai estratto con successo le funzionalità in GeoJSON utilizzando Aspose.GIS per .NET.
## Conclusione
In questo tutorial, abbiamo esplorato il processo di estrazione delle funzionalità in GeoJSON utilizzando Aspose.GIS per .NET. Questa potente libreria apre un mondo di possibilità per lo sviluppo GIS. Sperimenta diversi set di dati e funzionalità per sbloccare tutto il potenziale di Aspose.GIS.
## Domande frequenti
### D: Dove posso trovare ulteriore documentazione?
 Visitare il[Documentazione Aspose.GIS](https://reference.aspose.com/gis/net/) per informazioni approfondite.
### D: Come posso ottenere una licenza temporanea?
 È possibile ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### D: Dove posso chiedere supporto?
 Aderire al[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per il supporto e le discussioni della comunità.
### D: È disponibile una prova gratuita?
 Sì, puoi trovare la prova gratuita[Qui](https://releases.aspose.com/).
### D: Dove posso acquistare Aspose.GIS per .NET?
 Puoi acquistare il prodotto[Qui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
