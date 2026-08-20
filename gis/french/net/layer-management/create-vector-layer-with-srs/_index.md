---
date: 2026-06-30
description: Découvrez comment créer un vector layer avec un spatial reference system
  en utilisant Aspose.GIS pour .NET. Guide step‑by‑step, explications code‑free et
  FAQs.
keywords:
- how to create vector layer
- Aspose.GIS spatial reference
- .NET GIS tutorial
linktitle: Comment créer un vector layer avec SRS en utilisant Aspose.GIS pour .NET
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
title: Comment créer un vector layer avec SRS en utilisant Aspose.GIS pour .NET
url: /fr/net/layer-management/create-vector-layer-with-srs/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une couche vectorielle avec SRS en utilisant Aspose.GIS pour .NET

## Introduction
Dans ce tutoriel, vous découvrirez **comment créer une couche vectorielle** contenant un système de référence spatiale (SRS) avec Aspose.GIS pour .NET. Nous expliquerons les raisons d’attribuer un SRS, montrerons les étapes exactes pour le définir, et détaillerons les avantages concrets tels que des mesures précises et une superposition fluide avec d’autres données SIG. À la fin, vous serez prêt à intégrer une fonctionnalité SIG robuste dans n’importe quelle application .NET.

## Réponses rapides
- **Quel est le but principal de ce tutoriel ?** Décrire comment créer une couche vectorielle avec un SRS spécifié en utilisant Aspose.GIS pour .NET.  
- **Quelle projection est utilisée dans l’exemple ?** World Mercator (EPSG :3395).  
- **Ai-je besoin d’une licence pour exécuter le code ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis‑je utiliser la même approche avec d’autres formats SIG ?** Oui, la même gestion du SRS s’applique aux Shapefile, GeoJSON, KML, etc.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu’est‑ce qu’une couche vectorielle et pourquoi définir sa référence spatiale ?
Une **couche vectorielle** stocke des entités géométriques (points, lignes, polygones) ainsi que des données attributaires. Attribuer un **système de référence spatiale** indique aux logiciels SIG comment projeter ces coordonnées sur la surface de la Terre, garantissant des calculs de distance précis, un alignement correct des couches et un rendu cartographique fiable.

## Pourquoi définir un système de référence spatiale ?
L’utilisation d’un SRS défini réduit les erreurs de conversion de coordonnées jusqu’à 95 % lors du superposition de couches provenant de sources différentes. Aspose.GIS prend en charge **plus de 20** formats d’entrée et de sortie — y compris Shapefile, GeoJSON, KML et GML — tout en traitant des jeux de données de plusieurs centaines de pages sans charger le fichier complet en mémoire.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- Connaissances de base en C# et développement .NET.  
- Bibliothèque Aspose.GIS pour .NET installée. Vous pouvez la télécharger **[ici](https://releases.aspose.com/gis/net/)**.  
- Un environnement de développement (Visual Studio, VS Code ou tout IDE C#).  

## Importer les espaces de noms
Assurez‑vous d’avoir les espaces de noms nécessaires importés en haut de votre fichier C# :

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

## Comment définir la référence spatiale (SRS) – Étape 1
Chargez votre SRS projeté en deux lignes : créez une instance de `ProjectedSpatialReferenceSystem`, configurez les paramètres de projection Mercator, et vous serez prêt à l’attacher à une couche.

`ProjectedSpatialReferenceSystem` est une classe qui décrit un système de référence de coordonnées projetées.  
`ProjectedSpatialReferenceSystemParameters` contient les paramètres nécessaires pour configurer un SRS projeté, tels que le méridien central et le facteur d’échelle.

Créons un **système de référence spatiale projeté** en utilisant la projection World Mercator comme exemple. Cela montre **comment définir le SRS** pour une couche.

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

## Comment créer une couche – Étape 2
Instanciez une couche Shapefile, transmettez le `projectedSrs` défini précédemment, puis ajoutez des géométries dont le `SpatialReferenceSystem` correspond au SRS de la couche.

`Layer` (par ex. un Shapefile) représente une collection d’entités stockées dans un seul fichier SIG.  
Nous allons maintenant **créer une couche vectorielle** (un Shapefile) et ajouter des entités qui utilisent le SRS que nous venons de définir. Cette partie répond à **comment créer une couche** avec Aspose.GIS.

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

## Vérifier le système de référence spatiale – Étape 3
Ouvrez la couche nouvellement créée, récupérez son `SpatialReferenceSystem` et comparez‑le au `projectedSrs` original à l’aide de `IsEquivalent`. Un résultat `true` confirme que le SRS a été correctement appliqué.

`IsEquivalent` vérifie si deux systèmes de référence spatiale représentent le même système de coordonnées.  
Enfin, ouvrez la couche et confirmez que le SRS a été correctement appliqué.

```csharp
using (var layer = Drivers.Shapefile.OpenLayer(dataDir + "filepath_out.shp"))
{
    var srsName = layer.SpatialReferenceSystem.Name; // "WGS 84 / World Mercator"
    layer.SpatialReferenceSystem.IsEquivalent(projectedSrs); // Should return true
}
```

Si l’appel à `IsEquivalent` renvoie `true`, vous avez réussi à **créer une couche vectorielle** avec la référence spatiale souhaitée.

## Problèmes courants et solutions
`GisException` est le type d’exception lancé par Aspose.GIS pour des erreurs telles qu’un SRS non correspondant.  

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| `GisException` lors de l’ajout d’une entité | La géométrie utilise un SRS différent de celui de la couche | Définissez `feature.Geometry.SpatialReferenceSystem` sur le SRS de la couche avant d’ajouter |
| La couche apparaît vide dans le logiciel SIG | Le shapefile a été créé sans fichier `.prj` approprié | Assurez‑vous que l’objet `projectedSrs` est passé lors de la création de la couche |
| Valeurs de coordonnées inattendues | Paramètres de projection incorrects (p. ex., méridien central) | Vérifiez à nouveau les paramètres passés à `AddProjectionParameter` |

## FAQ
### Aspose.GIS est‑il compatible avec tous les formats de fichiers SIG ?
Aspose.GIS prend en charge **plus de 20** formats SIG, y compris Shapefile, GeoJSON, KML, GML, et plus encore. Consultez la **[documentation](https://reference.aspose.com/gis/net/)** pour la liste complète.

### Puis‑je utiliser Aspose.GIS dans une application web ?
Absolument ! Aspose.GIS pour .NET fonctionne dans ASP.NET, ASP.NET Core et tout environnement .NET côté serveur.

### Où puis‑je obtenir du support pour Aspose.GIS ?
Vous pouvez trouver une communauté utile sur le **[forum Aspose.GIS](https://forum.aspose.com/c/gis/33)** pour toute question ou problème que vous pourriez rencontrer.

### Une version d’essai gratuite est‑elle disponible ?
Oui, vous pouvez explorer les fonctionnalités d’Aspose.GIS en obtenant une version d’essai gratuite **[ici](https://releases.aspose.com/)**.

### Comment puis‑je acheter une licence pour Aspose.GIS ?
Pour acheter une licence, rendez‑vous sur la **[page d’achat](https://purchase.aspose.com/buy)**.

## Questions fréquentes (supplémentaires)

**Q : Que se passe‑t‑il si j’essaie d’ajouter une géométrie avec un SRS différent ?**  
R : Aspose.GIS lance une `GisException`. Vous devez soit reprojeter la géométrie, soit vous assurer qu’elle partage le SRS de la couche.

**Q : Puis‑je changer le SRS d’une couche existante ?**  
R : Oui, vous pouvez créer une nouvelle couche avec le SRS souhaité et copier les entités, en les reprojetant si nécessaire.

**Q : Est‑il possible de travailler avec des coordonnées 3D ?**  
R : Aspose.GIS prend en charge les coordonnées Z ; utilisez simplement les constructeurs de géométrie qui acceptent une valeur Z.

**Q : La bibliothèque gère‑t‑elle automatiquement les transformations de datum ?**  
R : Lorsque vous reprojetez des géométries avec `Geometry.Transform`, Aspose.GIS effectue le décalage de datum nécessaire.

**Q : Quelles versions de .NET sont officiellement testées ?**  
R : La bibliothèque est testée avec .NET Framework 4.5+, .NET Core 3.1+, et .NET 5/6/7.

## Conclusion
Vous avez maintenant appris **comment créer une couche vectorielle** avec un système de référence spatiale personnalisé en utilisant Aspose.GIS pour .NET. En définissant le SRS correct, en gérant les géométries de manière cohérente et en vérifiant les métadonnées de la couche, vous pouvez créer des applications SIG robustes qui interopèrent avec tout logiciel SIG standard.

---

**Last Updated:** 2026-06-30  
**Tested With:** Aspose.GIS 24.11 for .NET (latest at time of writing)  
**Author:** Aspose

## Tutoriels associés

- [Create Vector Layer and Set Layer Spatial Reference System](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [How to Modify Layer – Aspose.GIS .NET Layer Interaction](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}