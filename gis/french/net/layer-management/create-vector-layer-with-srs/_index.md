---
date: 2026-01-15
description: Explorez Aspose.GIS pour .NET afin de créer une couche vectorielle avec
  un système de référence spatiale. Apprenez comment définir le SRS, créer une couche
  et gérer les données SIG. Téléchargez maintenant!
linktitle: Create Vector Layer with SRS
second_title: Aspose.GIS .NET API
title: Créer une couche vectorielle avec SRS
url: /fr/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une couche vectorielle avec SRS

## Introduction
Aspose.GIS for .NET est une bibliothèque puissante qui permet aux développeurs de **create vector layer** des objets et de travailler avec les données de système d'information géographique (GIS) de manière transparente dans les applications .NET. Dans ce tutoriel, nous allons parcourir la création d'une couche vectorielle avec un système de référence spatiale (SRS), expliquer pourquoi il est utile de définir une référence spatiale, et quels avantages cela apporte aux projets réels. À la fin de ce guide, vous serez capable d'intégrer les capacités GIS dans vos solutions .NET en toute confiance.

## Quick Answers
- **Quel est le but principal de ce tutoriel ?** Pour montrer comment créer vector layer avec un SRS spécifié en utilisant Aspose.GIS for .NET.  
- **Quelle projection est utilisée dans l'exemple ?** World Mercator (EPSG:3395).  
- **Ai-je besoin d'une licence pour exécuter le code ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis-je utiliser la même approche avec d'autres formats GIS ?** Oui, la même gestion du SRS s'applique aux Shapefile, GeoJSON, KML, etc.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is a vector layer and why set its spatial reference?
Une **vector layer** stocke des entités géométriques (points, lignes, polygones) ainsi que des données attributaires. L'attribution d'une **spatial reference** (SRS) indique au logiciel GIS comment interpréter ces coordonnées à la surface de la Terre. Définir le SRS correct garantit des mesures précises, une superposition correcte avec d'autres couches et des visualisations cartographiques fiables.

## Prerequisites
Avant de commencer, assurez-vous d'avoir :

- Connaissances de base en C# et développement .NET.  
- Bibliothèque Aspose.GIS for .NET installée. Vous pouvez la télécharger **[here](https://releases.aspose.com/gis/net/)**.  
- Un environnement de développement (Visual Studio, VS Code ou tout IDE C#).  

## Import Namespaces
Ensure you have the necessary namespaces imported at the top of your C# file:

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

## How to set spatial reference (SRS) – Step 1
Créons un **projected spatial reference system** en utilisant la projection World Mercator comme exemple. Cela montre **how to set srs** pour une couche.

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

## How to create layer – Step 2
Nous allons maintenant **create a vector layer** (un Shapefile) et ajouter des entités qui utilisent le SRS que nous venons de définir. Cette partie répond à **how to create layer** avec Aspose.GIS.

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

> **Astuce :** Vérifiez toujours que le `SpatialReferenceSystem` de la géométrie correspond au SRS de la couche avant de l'ajouter. Des valeurs SRS non concordantes déclenchent une `GisException`, comme indiqué ci‑dessus.

## Verify Spatial Reference System – Step 3
Enfin, ouvrez la couche et confirmez que le SRS a été correctement appliqué.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Si l'appel `IsEquivalent` renvoie `true`, vous avez réussi à **create vector layer** avec la référence spatiale souhaitée.

## Common Issues & Solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| `GisException` lors de l'ajout d'une entité | La géométrie utilise un SRS différent de la couche | Définir `feature.Geometry.SpatialReferenceSystem` sur le SRS de la couche avant l'ajout |
| La couche apparaît vide dans le logiciel GIS | Le shapefile a été créé sans fichier `.prj` adéquat | S'assurer que l'objet `projectedSrs` est passé lors de la création de la couche |
| Valeurs de coordonnées inattendues | Paramètres de projection incorrects (p. ex. méridien central) | Vérifier à nouveau les paramètres passés à `AddProjectionParameter` |

## FAQs
### Is Aspose.GIS compatible with all GIS file formats?
Aspose.GIS prend en charge divers formats GIS, y compris Shapefile, GeoJSON, KML, et plus encore. Consultez la **[documentation](https://reference.aspose.com/gis/net/)** pour la liste complète.

### Can I use Aspose.GIS in a web application?
Absolument ! Aspose.GIS for .NET est polyvalent et peut être utilisé dans des applications web, des applications de bureau, et même des applications mobiles.

### Where can I get support for Aspose.GIS?
Vous pouvez trouver une communauté utile sur le **[forum Aspose.GIS](https://forum.aspose.com/c/gis/33)** pour toute question ou problème que vous pourriez rencontrer.

### Is there a free trial available?
Oui, vous pouvez explorer les fonctionnalités d'Aspose.GIS en obtenant un essai gratuit **[here](https://releases.aspose.com/)**.

### How can I purchase a license for Aspose.GIS?
Pour acheter une licence, rendez‑vous sur la **[page d'achat](https://purchase.aspose.com/buy)**.

## Frequently Asked Questions (Additional)

**Q : Que se passe-t-il si j'essaie d'ajouter une géométrie avec un SRS différent ?**  
R : Aspose.GIS lance une `GisException`. Vous devez soit reprojeter la géométrie, soit vous assurer qu'elle partage le SRS de la couche.

**Q : Puis‑je changer le SRS d'une couche existante ?**  
R : Oui, vous pouvez créer une nouvelle couche avec le SRS souhaité et copier les entités en les reprojectant si nécessaire.

**Q : Est‑il possible de travailler avec des coordonnées 3D ?**  
R : Aspose.GIS prend en charge les coordonnées Z ; il suffit d'utiliser les constructeurs de géométrie qui acceptent une valeur Z.

**Q : La bibliothèque gère‑t‑elle automatiquement les transformations de datum ?**  
R : Lors du re‑projection des géométries avec `Geometry.Transform`, Aspose.GIS effectue le décalage de datum nécessaire.

**Q : Quelles versions de .NET sont officiellement testées ?**  
R : La bibliothèque est testée avec .NET Framework 4.5+, .NET Core 3.1+, et .NET 5/6/7.

## Conclusion
Vous avez maintenant appris comment **create vector layer** avec un système de référence spatiale personnalisé en utilisant Aspose.GIS for .NET. En définissant le SRS correct, en gérant les géométries de manière cohérente et en vérifiant les métadonnées de la couche, vous pouvez créer des applications robustes compatibles GIS qui interopèrent avec tout logiciel GIS standard.

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}