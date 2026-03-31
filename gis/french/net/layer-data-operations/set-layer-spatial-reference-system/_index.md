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
Dans le vaste paysage des Systèmes d’Information Géographique (GIS), **Aspose.GIS for .NET** se démarque comme un outil robuste et polyvalent pour les développeurs. Dans ce tutoriel, vous allez **créer une couche vectorielle**, définir sa référence spatiale, ajouter une entité ponctuelle et récupérer le code EPSG — le tout avec des instructions claires, étape par étape. Que vous soyez un ingénieur SIG chevronné ou que vous débutiez, ces techniques vous aideront à définir correctement le système de coordonnées du shapefile et à améliorer la fiabilité de vos flux de travail de données spatiales.

## Réponses rapides
- **Que signifie « créer une couche vectorielle » ?**Cela crée une nouvelle couche SIG (par exemple, un fichier Shape) qui peut stocker des géométries telles que des points, des lignes ou des polygones.
- **Quel code EPSG est utilisé dans l'exemple ?**EPSG26918 (NAD83 / UTM zone18N).
- **Puis-je ajouter une entité ponctuelle après avoir créé le calque ?**Oui : utilisez `ConstructFeature()` et attribuez une géométrie `Point`.
- **Comment récupérer le CRS de la couche ?**Lisez `layer.SpatialReferenceSystem.EpsgCode` ou `.Name`.
- **Ai-je besoin d'une licence pour Aspose.GIS ?**Un essai gratuit est disponible ; une licence est requise pour une utilisation en production.

## Prérequis
Avant de Sous-marin dans le tutoriel, assurez-vous d’avoir les prérequis suivants :
- Une connaissance pratique de la programmation .NET.
- Visual Studio installé sur votre système.
- La bibliothèque Aspose.GIS for .NET, que vous pouvez télécharger [ici](https://releases.aspose.com/gis/net/).
- Une compréhension de base des systèmes de référence spatiale en SIG.

## Importer des espaces de noms
Dans votre projet .NET, commencez par importer les espaces de noms nécessaires pour accéder aux fonctionnalités fournies par Aspose.GIS. Utilisez le fragment de code suivant :

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Étape 1 : Spécifiez le répertoire des documents
Commencez par préciser le chemin vers votre répertoire de documents. Ce sera l’emplacement où vos fichiers de données spatiales seront stockés.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : Définir la référence spatiale et définir le système de coordonnées du fichier de formes
Définissez le chemin du Shapefile, et **define spatial reference** en utilisant le code EPSG (26918 dans cet exemple). Cette étape **définit le système de coordonnées du shapefile** pour la couche.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Étape 3 : Créer une couche vectorielle
Maintenant **create vector layer** avec le chemin du Shapefile spécifié, le type de pilote (Shapefile) et le système de référence spatiale que vous venez de définir.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

## Étape 4 : Ajouter des entités ponctuelles à la couche
Construisez une nouvelle entité et **add point feature** en définissant sa géométrie (un `Point` avec les coordonnées 60, 24). Puis ajoutez l’entité à la couche vectorielle.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

## Étape 5 : Récupérer les informations du système de référence spatiale (code EPSG)
Ouvrez la couche vectorielle et récupérez les informations sur le système de référence spatiale, telles que le code EPSG et le nom lisible par l’homme. Cela montre comment **retrieve EPSG code** et **set layer CRS**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

Répétez ces étapes selon votre cas d’utilisation spécifique, et vous serez bien parti pour maîtriser l’art de **create vector layer** et gérer les références spatiales avec Aspose.GIS for .NET.

## Problèmes courants et solutions
| Problème | Cause | Solution |

|-------|----------------|-----|

| **Impossible d'ouvrir le calque** | Pilote incorrect ou chemin d'accès corrompu | Vérifiez `Drivers.Shapefile` et assurez-vous que `path` pointe vers un fichier `.shp` existant. |

| **Système de coordonnées de référence (SCR) affiché incorrect** | Utilisation d'un code EPSG incorrect | Vérifiez le code EPSG auprès d'une source fiable (par exemple, EPSG.io). |

| **Entité non enregistrée** | Absence d'appel à `layer.Add(feature)` dans le bloc `using` | Assurez-vous que la méthode `Add` est exécutée avant la suppression du calque. |

## Questions fréquentes supplémentaires
**Q : Comment modifier le SCR d’un fichier Shapefile existant ?**

R : Ouvrez la couche, créez un nouvel objet `SpatialReferenceSystem` avec le code EPSG souhaité et assignez-le à `layer.SpatialReferenceSystem` avant d’enregistrer.

**Q : Puis-je ajouter d’autres types de géométrie (par exemple, des polygones) en utilisant la même méthode ?**

R : Oui, remplacez `new Point(x, y)` par `new Polygon(...)` ou `new LineString(...)` selon vos besoins.

**Q : Est-il possible de travailler efficacement avec de grands jeux de données ?**

R : Utilisez les API de flux (`VectorLayer.Create` avec `FeatureCollection`) et supprimez rapidement les couches pour libérer des ressources.

**Q : Aspose.GIS prend-il en charge la transformation de coordonnées ?**
R : Oui : utilisez « Geometry.Transform(targetSrs) » pour reprojeter des géométries entre différentes références spatiales.

**Q : Quelles versions de .NET sont prises en charge ?**
R : Aspose.GIS fonctionne avec .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Conclusion
Dans ce tutoriel, nous avons exploré comment **créer une couche vectorielle**, définir sa référence spatiale, **ajouter une entité ponctuelle** et **récupérer le code EPSG** en utilisant Aspose.GIS pour .NET. En maîtrisant ces étapes, vous pourrez définir correctement le système de coordonnées du shapefile, gérer le CRS de la couche et créer des applications SIG fiables.

---

**Dernière mise à jour :** 31/12/2025
**Testé avec :** Aspose.GIS 24.11 pour .NET
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}