---
title: Converti il file di forma poligonale in una stringa di linee
linktitle: Converti il file di forma poligonale in una stringa di linee
second_title: API Aspose.GIS .NET
description: Esplora la potenza di Aspose.GIS per .NET e converti facilmente i file di forma poligonale in stringhe di linea. Potenzia il tuo sviluppo GIS oggi stesso!
weight: 18
url: /it/net/layer-management/convert-polygon-shapefile-to-linestring/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti il file di forma poligonale in una stringa di linee

## introduzione
Se lavori con sistemi di informazione geografica (GIS) in .NET, Aspose.GIS è una potente libreria che può semplificare le tue attività. In questo tutorial, ti guideremo attraverso il processo di conversione di un file di forma poligonale in una stringa di linea utilizzando Aspose.GIS. Ciò può essere particolarmente utile quando è necessario estrarre elementi lineari da dati poligonali per varie applicazioni come la pianificazione del percorso o l'analisi della rete.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere a disposizione quanto segue:
-  Libreria Aspose.GIS: scarica e installa la libreria Aspose.GIS dal file[sito web](https://releases.aspose.com/gis/net/).
- Dati Shapefile: avere uno Shapefile poligonale pronto per la conversione. Se non ne hai uno, puoi trovare dati di esempio o crearne di tuoi.
- Ambiente di sviluppo: configura il tuo ambiente di sviluppo .NET con gli strumenti necessari.
## Importa spazi dei nomi
Nel codice C#, devi importare gli spazi dei nomi Aspose.GIS per accedere alle classi e ai metodi richiesti. Aggiungi i seguenti spazi dei nomi all'inizio del file di codice:
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Passaggio 1: impostare la directory dei documenti
```csharp
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
```
Sostituisci "Your Document Directory" con il percorso della directory in cui si trova il tuo Shapefile.
## Passaggio 2: aprire lo shapefile di origine
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Il resto del codice andrà qui
}
```
Questo passaggio apre il Polygon Shapefile di origine per la lettura.
## Passaggio 3: creare il file di forma della stringa di linea di destinazione
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Il resto del codice andrà qui
}
```
Qui creiamo un nuovo Linestring Shapefile per scrivere i dati convertiti.
## Passaggio 4: scorrere le funzionalità di origine
```csharp
foreach (Feature sourceFeature in source)
{
    // Il resto del codice andrà qui
}
```
Questo ciclo scorre ciascuna funzionalità nel Polygon Shapefile di origine.
## Passaggio 5: converti il poligono in una stringa lineare e scrivi nella destinazione
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
In questo passaggio, ciascuna funzionalità Polygon viene convertita in una stringa di linea e la funzionalità di stringa di linea risultante viene scritta nello Shapefile di destinazione.
## Conclusione
Seguendo questi passaggi, puoi convertire facilmente un file di forma poligonale in una stringa di linea utilizzando Aspose.GIS per .NET. Questo processo apre nuove possibilità per l'analisi e la visualizzazione dei dati nelle applicazioni GIS.

## Domande frequenti
### Aspose.GIS è compatibile con tutte le versioni di .NET?
Sì, Aspose.GIS supporta varie versioni di .NET, garantendo la compatibilità con il tuo ambiente di sviluppo.
### Posso utilizzare Aspose.GIS per progetti commerciali?
 Si, puoi. Per utilizzare Aspose.GIS in progetti commerciali, considera l'acquisto di una licenza[Qui](https://purchase.aspose.com/buy).
### Sono disponibili esempi o documentazione?
 Sì, puoi trovare documentazione completa ed esempi su[pagina della documentazione](https://reference.aspose.com/gis/net/).
### È disponibile una versione di prova?
 Sì, puoi esplorare Aspose.GIS con una prova gratuita visitando[questo link](https://releases.aspose.com/).
### Dove posso cercare aiuto o supporto?
 Visitare il[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per qualsiasi assistenza o domanda relativa al supporto.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
