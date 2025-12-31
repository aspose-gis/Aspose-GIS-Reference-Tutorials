---
date: 2025-12-31
description: Apprenez à créer une couche vectorielle et à définir le système de référence
  spatiale de la couche avec Aspose.GIS pour .NET. Maîtrisez la définition de la référence
  spatiale, l’ajout d’une entité ponctuelle et la récupération du code EPSG.
linktitle: Set Layer Spatial Reference System
second_title: Aspose.GIS .NET API
title: Créer une couche vectorielle et définir le système de référence spatiale de
  la couche
url: /fr/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une couche vectorielle et définir le système de référence spatiale de la couche

## Introduction
Dans le vaste paysage des Systèmes d’Information Géographique (GIS), **Aspose.GIS for .NET** se démarque comme un outil robuste et polyvalent pour les développeurs. Dans ce tutoriel, vous allez **create vector layer**, définir sa référence spatiale, ajouter une entité ponctuelle et récupérer le code EPSG — le tout avec des instructions claires, étape par étape. Que vous soyez un ingénieur GIS chevronné ou que vous débutiez, ces techniques vous aideront à définir correctement le système de coordonnées du shapefile et à améliorer la fiabilité de vos flux de travail de données spatiales.

## Quick Answers
- **What does “create vector layer” mean?** It creates a new GIS layer (e.g., a Shapefile) that can store geometries such as points, lines, or polygons.  
- **Which EPSG code is used in the example?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **Can I add a point feature after creating the layer?** Yes—use `ConstructFeature()` and assign a `Point` geometry.  
- **How do I retrieve the layer’s CRS?** Read `layer.SpatialReferenceSystem.EpsgCode` or `.Name`.  
- **Do I need a license for Aspose.GIS?** A free trial is available; a license is required for production use.

## Prerequisites
Avant de plonger dans le tutoriel, assurez‑vous d’avoir les prérequis suivants :
- Une connaissance pratique de la programmation .NET.  
- Visual Studio installé sur votre système.  
- La bibliothèque Aspose.GIS for .NET, que vous pouvez télécharger [ici](https://releases.aspose.com/gis/net/).  
- Une compréhension de base des systèmes de référence spatiale en GIS.

## Import Namespaces
Dans votre projet .NET, commencez par importer les espaces de noms nécessaires pour accéder aux fonctionnalités fournies par Aspose.GIS. Utilisez le fragment de code suivant :

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Step 1: Specify the Document Directory
Commencez par spécifier le chemin vers votre répertoire de documents. Ce sera l’emplacement où vos fichiers de données spatiales seront stockés.

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Define Spatial Reference and Set Shapefile Coordinate System
Définissez le chemin du Shapefile, et **define spatial reference** en utilisant le code EPSG (26918 dans cet exemple). Cette étape **sets the shapefile coordinate system** pour la couche.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Step 3: Create Vector Layer
Maintenant **create vector layer** avec le chemin du Shapefile spécifié, le type de pilote (Shapefile) et le système de référence spatiale que vous venez de définir.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Step 4: Add Point Feature to the Layer
Construisez une nouvelle entité et **add point feature** en définissant sa géométrie (un `Point` avec les coordonnées 60, 24). Puis ajoutez l’entité à la couche vectorielle.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Step 5: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
Ouvrez la couche vectorielle et récupérez les informations sur le système de référence spatiale, telles que le code EPSG et le nom lisible par l’homme. Cela montre comment **retrieve EPSG code** et **set layer CRS**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Répétez ces étapes selon votre cas d’utilisation spécifique, et vous serez bien parti pour maîtriser l’art de **create vector layer** et gérer les références spatiales avec Aspose.GIS for .NET.

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Layer fails to open** | Wrong driver or corrupted file path | Verify `Drivers.Shapefile` and ensure `path` points to an existing `.shp` file. |
| **Incorrect CRS displayed** | Using the wrong EPSG code | Double‑check the EPSG code with an authoritative source (e.g., EPSG.io). |
| **Feature not saved** | Not calling `layer.Add(feature)` inside the `using` block | Ensure the `Add` method is executed before the layer is disposed. |

## Frequently Asked Questions
### Is Aspose.GIS compatible with other GIS libraries?
Yes, Aspose.GIS integrates well with other GIS libraries and can be used in conjunction with them.

### Can I use Aspose.GIS for both desktop and web applications?
Absolutely! Aspose.GIS is versatile and can be utilized in both desktop and web‑based applications.

### Are there any licensing options available for Aspose.GIS?
Yes, you can explore licensing options and make a purchase [here](https://purchase.aspose.com/buy).

### Is there a free trial available for Aspose.GIS?
Certainly! You can download a free trial version [here](https://releases.aspose.com/).

### Where can I seek support for Aspose.GIS‑related queries?
For any support or queries, visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33).

## Additional Frequently Asked Questions
**Q: How do I change the CRS of an existing Shapefile?**  
A: Open the layer, create a new `SpatialReferenceSystem` with the desired EPSG code, and assign it to `layer.SpatialReferenceSystem` before saving.

**Q: Can I add other geometry types (e.g., polygons) using the same approach?**  
A: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)` as needed.

**Q: Is it possible to work with large datasets efficiently?**  
A: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and dispose layers promptly to free resources.

**Q: Does Aspose.GIS support coordinate transformation?**  
A: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between different spatial references.

**Q: What .NET versions are supported?**  
A: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Conclusion
Dans ce tutoriel, nous avons exploré comment **create vector layer**, définir sa référence spatiale, **add point feature**, et **retrieve EPSG code** en utilisant Aspose.GIS for .NET. En maîtrisant ces étapes, vous pourrez définir correctement le système de coordonnées du shapefile, gérer le CRS de la couche et créer des applications GIS fiables.

---

**Last Updated:** 2025-12-31  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}