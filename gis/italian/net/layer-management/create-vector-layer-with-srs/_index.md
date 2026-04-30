---
date: 2026-01-15
description: Esplora Aspose.GIS per .NET per creare un layer vettoriale con un sistema
  di riferimento spaziale. Scopri come impostare il SRS, creare il layer e gestire
  i dati GIS. Scarica ora!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: Crea livello vettoriale con SRS
url: /it/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Creare un layer vettoriale con SRS

## Introduzione
Aspose.GIS for .NET è una libreria potente che consente agli sviluppatori di **create vector layer** oggetti e di lavorare con i dati di sistemi informativi geografici (GIS) in modo fluido nelle applicazioni .NET. In questo tutorial, illustreremo come creare un layer vettoriale con un sistema di riferimento spaziale (SRS), perché impostare il riferimento spaziale e quali vantaggi porta ai progetti reali. Alla fine di questa guida, sarai in grado di integrare le funzionalità GIS nelle tue soluzioni .NET con sicurezza.

## Risposte rapide
- **Qual è lo scopo principale di questo tutorial?** Mostrare come creare un vector layer con un SRS specificato usando Aspose.GIS per .NET.  
- **Quale proiezione è usata nell'esempio?** World Mercator (EPSG:3395).  
- **È necessaria una licenza per eseguire il codice?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Posso usare lo stesso approccio con altri formati GIS?** Sì, la gestione del SRS è la stessa per Shapefile, GeoJSON, KML, ecc.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Che cos'è un vector layer e perché impostare il suo riferimento spaziale?
Un **vector layer** memorizza caratteristiche geometriche (punti, linee, poligoni) insieme ai dati attributivi. Assegnare un **spatial reference** (SRS) indica al software GIS come interpretare quelle coordinate sulla superficie terrestre. Impostare il SRS corretto garantisce misurazioni accurate, sovrapposizioni corrette con altri layer e visualizzazioni cartografiche affidabili.

## Prerequisiti
- Conoscenza di base di C# e sviluppo .NET.  
- Libreria Aspose.GIS per .NET installata. Puoi scaricarla **[qui](https://releases.aspose.com/gis/net/)**.  
- Un ambiente di sviluppo (Visual Studio, VS Code o qualsiasi IDE C#).  

## Importare i namespace
Assicurati di avere i namespace necessari importati all'inizio del tuo file C#:

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

## Come impostare il riferimento spaziale (SRS) – Passo 1
Creiamo un **projected spatial reference system** usando la proiezione World Mercator come esempio. Questo dimostra **how to set srs** per un layer.

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

## Come creare un layer – Passo 2
Ora **creeremo un vector layer** (uno Shapefile) e aggiungeremo feature che usano il SRS appena definito. Questa parte risponde a **how to create layer** con Aspose.GIS.

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
        layer.Add(feature); // This will throw an exception as the geometry has a different SRS
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```

> **Consiglio professionale:** verifica sempre che il `SpatialReferenceSystem` della geometria corrisponda al SRS del layer prima di aggiungerla. Valori SRS non corrispondenti generano una `GisException`, come mostrato sopra.

## Verificare il Sistema di Riferimento Spaziale – Passo 3
Infine, apri il layer e conferma che il SRS sia stato applicato correttamente.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Se la chiamata `IsEquivalent` restituisce `true`, hai creato con successo **create vector layer** con il riferimento spaziale desiderato.

## Problemi comuni e soluzioni
| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| `GisException` durante l'aggiunta di una feature | La geometria usa un SRS diverso da quello del layer | Set `feature.Geometry.SpatialReferenceSystem` to the layer’s SRS before adding |
| Il layer appare vuoto nel software GIS | Lo shapefile è stato creato senza un file `.prj` corretto | Ensure the `projectedSrs` object is passed when creating the layer |
| Valori di coordinate inaspettati | Parametri di proiezione errati (es. meridiano centrale) | Double‑check the parameters passed to `AddProjectionParameter` |

## FAQ
### Aspose.GIS è compatibile con tutti i formati di file GIS?
Aspose.GIS supporta vari formati GIS, inclusi Shapefile, GeoJSON, KML e altri. Consulta la **[documentazione](https://reference.aspose.com/gis/net/)** per l'elenco completo.

### Posso usare Aspose.GIS in un'applicazione web?
Assolutamente! Aspose.GIS per .NET è versatile e può essere usato in applicazioni web, desktop e persino mobile.

### Dove posso ottenere supporto per Aspose.GIS?
Puoi trovare una community utile nel **[forum Aspose.GIS](https://forum.aspose.com/c/gis/33)** per qualsiasi domanda o problema.

### È disponibile una versione di prova gratuita?
Sì, puoi esplorare le funzionalità di Aspose.GIS ottenendo una versione di prova gratuita **[qui](https://releases.aspose.com/)**.

### Come posso acquistare una licenza per Aspose.GIS?
Per acquistare una licenza, visita la **[pagina di acquisto](https://purchase.aspose.com/buy)**.

## Domande frequenti (Aggiuntive)

**Q: Cosa succede se provo ad aggiungere una geometria con un SRS diverso?**  
A: Aspose.GIS genera una `GisException`. Devi o riproiettare la geometria o assicurarti che condivida il SRS del layer.

**Q: Posso cambiare il SRS di un layer esistente?**  
A: Sì, puoi creare un nuovo layer con il SRS desiderato e copiare le feature, riproiettandole se necessario.

**Q: È possibile lavorare con coordinate 3D?**  
A: Aspose.GIS supporta le coordinate Z; basta usare i costruttori di geometria che accettano un valore Z.

**Q: La libreria gestisce automaticamente le trasformazioni di datum?**  
A: Quando riproietti le geometrie usando `Geometry.Transform`, Aspose.GIS esegue lo spostamento di datum necessario.

**Q: Quali versioni di .NET sono testate ufficialmente?**  
A: La libreria è testata con .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6/7.

## Conclusione
Ora hai imparato come **create vector layer** con un sistema di riferimento spaziale personalizzato usando Aspose.GIS per .NET. Impostando il SRS corretto, gestendo le geometrie in modo coerente e verificando i metadati del layer, puoi costruire applicazioni GIS robuste che interoperano con qualsiasi software GIS standard.

---

**Ultimo aggiornamento:** 2026-01-15  
**Testato con:** Aspose.GIS 24.11 per .NET (ultima versione al momento della stesura)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}