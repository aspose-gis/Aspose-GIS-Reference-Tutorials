---
title: Crea un livello vettoriale con SRS
linktitle: Crea un livello vettoriale con SRS
second_title: API Aspose.GIS .NET
description: Esplora Aspose.GIS per .NET la tua chiave per una perfetta integrazione GIS. Crea livelli vettoriali senza sforzo con sistemi di riferimento spaziali specifici. Scarica ora!
type: docs
weight: 13
url: /it/net/layer-management/create-vector-layer-with-srs/
---
## introduzione
Aspose.GIS per .NET è una potente libreria che consente agli sviluppatori di lavorare senza problemi con i dati del sistema informativo geografico (GIS) nelle applicazioni .NET. In questo tutorial ci concentreremo sulla creazione di un layer vettoriale con un sistema di riferimento spaziale (SRS). Al termine di questa guida sarai in grado di integrare facilmente le funzionalità GIS nei tuoi progetti .NET.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di disporre dei seguenti prerequisiti:
- Conoscenza base dello sviluppo C# e .NET.
-  Aspose.GIS per la libreria .NET installata. Puoi scaricarlo[Qui](https://releases.aspose.com/gis/net/).
- Un ambiente di sviluppo configurato e pronto.
## Importa spazi dei nomi
Assicurati di aver importato gli spazi dei nomi necessari all'inizio del file C#:
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.Shapefile;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Passaggio 1: impostare il sistema di riferimento spaziale proiettato
Creiamo un sistema di riferimento spaziale proiettato (SRS) utilizzando la proiezione mondiale di Mercatore come esempio. Segui questi passi:
```csharp
var parameters = new ProjectedSpatialReferenceSystemParameters
{
    Name = "WGS 84 / World Mercator",
    Base = SpatialReferenceSystem.Wgs84,
    ProjectionMethodName = "Mercator_1SP",
    LinearUnit = Unit.Meter,
    XAxis = new Axis("Easting", AxisDirection.East),
    YAxis = new Axis("Northing", AxisDirection.North),
    AxisesOrder = ProjectedAxisesOrder.XY,
};
parameters.AddProjectionParameter("central_meridian", 0);
parameters.AddProjectionParameter("scale_factor", 1);
parameters.AddProjectionParameter("false_easting", 0);
parameters.AddProjectionParameter("false_northing", 0);
var projectedSrs = SpatialReferenceSystem.CreateProjected(parameters, Identifier.Epsg(3395));
```
## Passaggio 2: crea un livello vettoriale e aggiungi funzionalità
Ora creiamo uno shapefile e aggiungiamo funzionalità con l'SRS specificato:
```csharp
using (var layer = Drivers.Shapefile.CreateLayer(dataDir + "filepath_out.shp", new ShapefileOptions(), projectedSrs))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2);
    layer.Add(feature);
    feature = layer.ConstructFeature();
    feature.Geometry = new Point(1, 2) { SpatialReferenceSystem = SpatialReferenceSystem.Nad83 };
    try
    {
        layer.Add(feature); // Ciò genererà un'eccezione poiché la geometria ha un SRS diverso
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Passaggio 3: verificare il sistema di riferimento spaziale
Infine, apriamo il layer e verifichiamo il suo sistema di riferimento spaziale:
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / Mercatore mondiale"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Dovrebbe restituire vero
}
```
Seguendo questi passaggi, hai creato con successo un layer vettoriale con un sistema di riferimento spaziale specificato utilizzando Aspose.GIS per .NET.
## Conclusione
Integrare la funzionalità GIS nelle tue applicazioni .NET non è mai stato così facile, grazie ad Aspose.GIS. Con la possibilità di creare facilmente layer vettoriali e gestire sistemi di riferimento spaziale, puoi migliorare i tuoi progetti con potenti funzionalità geospaziali.
## Domande frequenti
### Aspose.GIS è compatibile con tutti i formati di file GIS?
 Aspose.GIS supporta vari formati GIS, inclusi Shapefile, GeoJSON, KML e altri. Controlla il[documentazione](https://reference.aspose.com/gis/net/) per l'elenco completo.
### Posso utilizzare Aspose.GIS in un'applicazione web?
Assolutamente! Aspose.GIS per .NET è versatile e può essere utilizzato in applicazioni Web, applicazioni desktop e persino app mobili.
### Dove posso ottenere supporto per Aspose.GIS?
 Puoi trovare una community utile su[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) per qualsiasi domanda o problema che potresti incontrare.
### È disponibile una prova gratuita?
 Sì, puoi esplorare le funzionalità di Aspose.GIS ottenendo una prova gratuita[Qui](https://releases.aspose.com/).
### Come posso acquistare una licenza per Aspose.GIS?
 Per acquistare una licenza, visitare il[pagina di acquisto](https://purchase.aspose.com/buy).