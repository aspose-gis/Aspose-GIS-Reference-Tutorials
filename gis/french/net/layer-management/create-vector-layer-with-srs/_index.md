---
title: Créer une couche vectorielle avec SRS
linktitle: Créer une couche vectorielle avec SRS
second_title: API Aspose.GIS .NET
description: Explorez Aspose.GIS pour .NET - votre clé pour une intégration SIG transparente. Créez facilement des couches vectorielles avec des systèmes de référence spatiale spécifiés. Télécharger maintenant!
type: docs
weight: 13
url: /fr/net/layer-management/create-vector-layer-with-srs/
---
## Introduction
Aspose.GIS pour .NET est une bibliothèque puissante qui permet aux développeurs de travailler de manière transparente avec les données du système d'information géographique (SIG) dans les applications .NET. Dans ce didacticiel, nous nous concentrerons sur la création d'une couche vectorielle avec un système de référence spatiale (SRS). À la fin de ce guide, vous serez en mesure d'intégrer sans effort les fonctionnalités SIG dans vos projets .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Connaissance de base du développement C# et .NET.
-  Bibliothèque Aspose.GIS pour .NET installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/gis/net/).
- Un environnement de développement configuré et prêt.
## Importer des espaces de noms
Assurez-vous d'avoir importé les espaces de noms nécessaires au début de votre fichier C# :
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
## Étape 1 : Configurer le système de référence spatiale projeté
Créons un système de référence spatiale projeté (SRS) en utilisant la projection World Mercator comme exemple. Suivez ces étapes:
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
## Étape 2 : créer une couche vectorielle et ajouter des fonctionnalités
Maintenant, créons un fichier de formes et ajoutons des fonctionnalités avec le SRS spécifié :
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
        layer.Add(feature); // Cela générera une exception car la géométrie a un SRS différent
    }
    catch (GisException e)
    {
        Console.WriteLine(e.Message);
    }
}
```
## Étape 3 : Vérifier le système de référence spatiale
Enfin, ouvrons la couche et vérifions son système de référence spatiale :
```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / Mercator mondial"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Devrait renvoyer vrai
}
```
En suivant ces étapes, vous avez réussi à créer une couche vectorielle avec un système de référence spatiale spécifié à l'aide d'Aspose.GIS pour .NET.
## Conclusion
L'intégration des fonctionnalités SIG dans vos applications .NET n'a jamais été aussi simple, grâce à Aspose.GIS. Avec la possibilité de créer sans effort des couches vectorielles et de gérer des systèmes de référence spatiale, vous pouvez améliorer vos projets grâce à de puissantes capacités géospatiales.
## FAQ
### Aspose.GIS est-il compatible avec tous les formats de fichiers SIG ?
 Aspose.GIS prend en charge divers formats SIG, notamment Shapefile, GeoJSON, KML, etc. Vérifier la[Documentation](https://reference.aspose.com/gis/net/) pour la liste complète.
### Puis-je utiliser Aspose.GIS dans une application Web ?
Absolument! Aspose.GIS pour .NET est polyvalent et peut être utilisé dans des applications Web, des applications de bureau et même des applications mobiles.
### Où puis-je obtenir de l'aide pour Aspose.GIS ?
 Vous pouvez trouver une communauté utile sur le[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour toute question ou problème que vous pourriez rencontrer.
### Existe-t-il un essai gratuit disponible ?
 Oui, vous pouvez explorer les fonctionnalités d'Aspose.GIS en obtenant un essai gratuit[ici](https://releases.aspose.com/).
### Comment puis-je acheter une licence pour Aspose.GIS ?
 Pour acheter une licence, visitez le[page d'achat](https://purchase.aspose.com/buy).