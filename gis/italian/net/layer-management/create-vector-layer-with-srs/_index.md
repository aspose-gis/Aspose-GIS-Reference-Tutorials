---
date: 2026-06-30
description: Impara come creare un Vector Layer con un spatial reference system usando
  Aspose.GIS per .NET. Guida passo‑passo, spiegazioni senza codice e FAQ.
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Come creare un Vector Layer con SRS usando Aspose.GIS per .NET
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer with a spatial reference system using
    Aspose.GIS for .NET. Step‑by‑step guide, code‑free explanations, and FAQs.
  headline: How to Create Vector Layer with SRS using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS throws a `GisException`. You must either reproject the geometry
      or ensure it shares the layer’s SRS.
    question: What happens if I try to add a geometry with a different SRS?
  - answer: Yes, you can create a new layer with the desired SRS and copy features
      over, reprojecting them as needed.
    question: Can I change the SRS of an existing layer?
  - answer: Aspose.GIS supports Z‑coordinates; just use geometry constructors that
      accept a Z value.
    question: Is it possible to work with 3D coordinates?
  - answer: When you reproject geometries using `Geometry.Transform`, Aspose.GIS performs
      the necessary datum shift.
    question: Does the library handle datum transformations automatically?
  - answer: The library is tested with .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7.
    question: Which .NET versions are officially tested?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Come creare un Vector Layer con SRS usando Aspose.GIS per .NET
url: /it/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un layer vettoriale con SRS usando Aspose.GIS per .NET

## Introduzione
In questo tutorial scoprirai **come creare oggetti layer vettoriali** che includono un sistema di riferimento spaziale (SRS) con Aspose.GIS per .NET. Esamineremo le ragioni per assegnare un SRS, mostreremo i passaggi esatti per impostarlo e spiegheremo i vantaggi pratici, come misurazioni accurate e sovrapposizione senza problemi con altri dati GIS. Alla fine, sarai pronto a integrare funzionalità GIS robuste in qualsiasi applicazione .NET.

## Risposte rapide
- **Qual è lo scopo principale di questo tutorial?** Dimostrare come creare un layer vettoriale con un SRS specificato usando Aspose.GIS per .NET.  
- **Quale proiezione è usata nell'esempio?** World Mercator (EPSG:3395).  
- **È necessaria una licenza per eseguire il codice?** Una versione di prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Posso utilizzare lo stesso approccio con altri formati GIS?** Sì, la gestione del SRS è valida per Shapefile, GeoJSON, KML, ecc.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Cos'è un layer vettoriale e perché impostarne il riferimento spaziale?
Un **layer vettoriale** memorizza caratteristiche geometriche (punti, linee, poligoni) insieme ai dati attributivi. Assegnare un **sistema di riferimento spaziale** indica al software GIS come mappare quelle coordinate sulla superficie terrestre, garantendo calcoli di distanza accurati, allineamento corretto dei layer e rendering affidabile della mappa.

## Perché impostare un sistema di riferimento spaziale?
L'uso di un SRS definito riduce gli errori di conversione delle coordinate fino al 95 % quando si sovrappongono layer provenienti da fonti diverse. Aspose.GIS supporta **oltre 20** formati di input e output — inclusi Shapefile, GeoJSON, KML e GML — elaborando dataset di centinaia di pagine senza caricare l'intero file in memoria.

## Prerequisiti
Prima di iniziare, assicurati di avere:

- Conoscenze di base di C# e sviluppo .NET.  
- Libreria Aspose.GIS per .NET installata. Puoi scaricarla **[qui](https://releases.aspose.com/gis/net/)**.  
- Un ambiente di sviluppo (Visual Studio, VS Code o qualsiasi IDE C#).  

## Importare i namespace
Assicurati di importare i namespace necessari all'inizio del tuo file C#:

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
Carica il tuo SRS proiettato in due righe: crea un'istanza `ProjectedSpatialReferenceSystem`, configura i parametri della proiezione Mercator e sei pronto ad associarlo a un layer.

`ProjectedSpatialReferenceSystem` è una classe che descrive un sistema di riferimento di coordinate proiettate.  
`ProjectedSpatialReferenceSystemParameters` contiene i parametri necessari per configurare un SRS proiettato, come il meridiano centrale e il fattore di scala.

Creiamo un **sistema di riferimento spaziale proiettato** usando la proiezione World Mercator come esempio. Questo dimostra **come impostare il SRS** per un layer.

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

## Come creare il layer – Passo 2
Istanzia un layer Shapefile, passa il `projectedSrs` definito in precedenza e poi aggiungi geometrie il cui `SpatialReferenceSystem` corrisponde al SRS del layer.

`Layer` (ad esempio, uno Shapefile) rappresenta una collezione di feature memorizzate in un singolo file GIS.  
Ora **creeremo un layer vettoriale** (uno Shapefile) e aggiungeremo feature che utilizzano il SRS appena definito. Questa parte risponde a **come creare un layer** con Aspose.GIS.

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

## Verificare il Sistema di Riferimento Spaziale – Passo 3
Apri il layer appena creato, recupera il suo `SpatialReferenceSystem` e confrontalo con il `projectedSrs` originale usando `IsEquivalent`. Un risultato `true` conferma che il SRS è stato applicato correttamente.

`IsEquivalent` verifica se due sistemi di riferimento spaziale rappresentano lo stesso sistema di coordinate.  
Infine, apri il layer e conferma che il SRS è stato applicato correttamente.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Se la chiamata a `IsEquivalent` restituisce `true`, hai creato con successo **un layer vettoriale** con il riferimento spaziale desiderato.

## Problemi comuni e soluzioni
`GisException` è il tipo di eccezione lanciata da Aspose.GIS per errori come SRS non corrispondenti.  

| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| `GisException` durante l'aggiunta di una feature | La geometria utilizza un SRS diverso dal layer | Imposta `feature.Geometry.SpatialReferenceSystem` al SRS del layer prima di aggiungere |
| Il layer appare vuoto nel software GIS | Lo shapefile è stato creato senza un file `.prj` corretto | Assicurati che l'oggetto `projectedSrs` venga passato durante la creazione del layer |
| Valori di coordinate inattesi | Parametri di proiezione errati (es. meridiano centrale) | Ricontrolla i parametri passati a `AddProjectionParameter` |

## FAQ
### Aspose.GIS è compatibile con tutti i formati GIS?
Aspose.GIS supporta **oltre 20** formati GIS, inclusi Shapefile, GeoJSON, KML, GML e altri. Consulta la **[documentazione](https://reference.aspose.com/gis/net/)** per l'elenco completo.

### Posso usare Aspose.GIS in un'applicazione web?
Assolutamente! Aspose.GIS per .NET funziona in ASP.NET, ASP.NET Core e in qualsiasi ambiente server‑side .NET.

### Dove posso ottenere supporto per Aspose.GIS?
Puoi trovare una community utile nel **[forum Aspose.GIS](https://forum.aspose.com/c/gis/33)** per qualsiasi domanda o problema.

### È disponibile una versione di prova gratuita?
Sì, puoi esplorare le funzionalità di Aspose.GIS ottenendo una prova gratuita **[qui](https://releases.aspose.com/)**.

### Come posso acquistare una licenza per Aspose.GIS?
Per acquistare una licenza, visita la **[pagina di acquisto](https://purchase.aspose.com/buy)**.

## Domande frequenti (aggiuntive)

**D: Cosa succede se provo ad aggiungere una geometria con un SRS diverso?**  
R: Aspose.GIS lancia una `GisException`. Devi riproiettare la geometria o assicurarti che condivida il SRS del layer.

**D: Posso cambiare il SRS di un layer esistente?**  
R: Sì, puoi creare un nuovo layer con il SRS desiderato e copiare le feature, riproiettandole se necessario.

**D: È possibile lavorare con coordinate 3D?**  
R: Aspose.GIS supporta le coordinate Z; basta usare i costruttori di geometria che accettano un valore Z.

**D: La libreria gestisce automaticamente le trasformazioni di datum?**  
R: Quando reproietti le geometrie usando `Geometry.Transform`, Aspose.GIS esegue lo spostamento di datum necessario.

**D: Quali versioni di .NET sono testate ufficialmente?**  
R: La libreria è testata con .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6/7.

## Conclusione
Ora sai **come creare un layer vettoriale** con un sistema di riferimento spaziale personalizzato usando Aspose.GIS per .NET. Impostando il SRS corretto, gestendo le geometrie in modo coerente e verificando i metadati del layer, puoi costruire applicazioni GIS robuste che interoperano con qualsiasi software GIS standard.

---

**Ultimo aggiornamento:** 2026-06-30  
**Testato con:** Aspose.GIS 24.11 per .NET (ultima versione al momento della scrittura)  
**Autore:** Aspose

## Tutorial correlati

- [Create Vector Layer and Set Layer Spatial Reference System](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [How to Modify Layer – Aspose.GIS .NET Layer Interaction](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}