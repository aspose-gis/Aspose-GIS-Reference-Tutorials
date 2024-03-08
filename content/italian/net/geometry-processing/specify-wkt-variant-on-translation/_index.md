---
title: Specificare la variante WKT sulla traduzione utilizzando Aspose.GIS
linktitle: Specificare la variante WKT nella traduzione
second_title: API Aspose.GIS .NET
description: Scopri come specificare le varianti WKT in Aspose.GIS per .NET per controllare in modo efficace il formato e la precisione della rappresentazione dei dati spaziali.
type: docs
weight: 19
url: /it/net/geometry-processing/specify-wkt-variant-on-translation/
---
## introduzione
Aspose.GIS per .NET è una potente libreria che consente agli sviluppatori di lavorare senza sforzo con i dati del sistema informativo geografico (GIS) nelle loro applicazioni .NET. Una delle funzionalità essenziali fornite da Aspose.GIS è la possibilità di specificare la variante Well-Known Text (WKT) durante la traduzione, consentendo agli utenti di controllare il formato e la precisione delle rappresentazioni dei dati spaziali. In questo tutorial, esploreremo come specificare le varianti WKT passo dopo passo utilizzando Aspose.GIS per .NET.
## Prerequisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
1. Aspose.GIS per .NET: scaricare e installare Aspose.GIS per .NET da[pagina di download](https://releases.aspose.com/gis/net/).
2. Ambiente di sviluppo: assicurati di avere un ambiente di sviluppo .NET configurato.
3. Conoscenze di base: familiarità con il linguaggio di programmazione C# e il framework .NET.

## Importa spazi dei nomi
Prima di utilizzare la funzionalità Aspose.GIS nel tuo codice, importa gli spazi dei nomi necessari:
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## Passaggio 1: crea un oggetto punto
 Per prima cosa, crea un file`Point` oggetto con valori di latitudine, longitudine e misura opzionale (M):
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Passaggio 2: impostare il sistema di riferimento spaziale (SRS)
Assegnare un sistema di riferimento spaziale (SRS) all'oggetto punto. In questo esempio utilizziamo il sistema di riferimento spaziale WGS84:
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Passaggio 3: specificare la variante WKT
 Ora specifica la variante WKT per la traduzione. Aspose.GIS supporta varie varianti WKT, incluse`Iso`, `SimpleFeatureAccessOutdated` , E`ExtendedPostGis`. Scegli la variante appropriata in base alle tue esigenze:
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // PUNTO M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // PUNTO (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;PUNTOTM (23.5732, 25.3421, 40.3)
```
## Passaggio 4: controllo del formato numerico
Puoi controllare il formato numerico delle coordinate nella rappresentazione WKT. Aspose.GIS fornisce opzioni per specificare la precisione decimale:
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // PUNTO M (23.5732 25.342099999999999 40.2999999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // PUNTO M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // PUNTO M (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // PUNTO M (23.573 25.342 40.3)
```

## Conclusione
In questo tutorial, abbiamo imparato come specificare le varianti WKT sulla traduzione utilizzando Aspose.GIS per .NET. Seguendo i passaggi sopra descritti, gli sviluppatori possono controllare efficacemente il formato e la precisione delle rappresentazioni dei dati spaziali nelle loro applicazioni .NET, migliorando la flessibilità e l'usabilità dei sistemi di informazione geografica.
## Domande frequenti
### Aspose.GIS è compatibile con tutte le versioni di .NET?
Sì, Aspose.GIS supporta .NET Framework 4.0 e versioni successive.
### Posso utilizzare Aspose.GIS per progetti commerciali?
Sì, Aspose.GIS può essere utilizzato sia per progetti personali che commerciali.
### Aspose.GIS fornisce supporto per altri formati di dati spaziali?
Sì, Aspose.GIS supporta un'ampia gamma di formati di dati spaziali, inclusi ESRI Shapefile, GeoJSON e KML.
### È disponibile una prova gratuita per Aspose.GIS?
 Sì, puoi scaricare una versione di prova gratuita di Aspose.GIS da[Qui](https://releases.aspose.com/).
### Dove posso ottenere aiuto o supporto per Aspose.GIS?
 Puoi pubblicare le tue domande o chiedere assistenza alla comunità Aspose.GIS all'indirizzo[Forum](https://forum.aspose.com/c/gis/33).