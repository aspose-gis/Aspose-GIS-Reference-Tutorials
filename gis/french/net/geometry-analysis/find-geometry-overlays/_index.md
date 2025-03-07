---
title: Maîtriser les superpositions géométriques avec Aspose.GIS pour .NET
linktitle: Rechercher des superpositions de géométrie
second_title: API Aspose.GIS .NET
description: Découvrez comment effectuer des opérations de superposition géométrique à l'aide d'Aspose.GIS pour .NET. Maîtrisez les opérations d’intersection, d’union, de différence et de différence symétrique.
weight: 16
url: /fr/net/geometry-analysis/find-geometry-overlays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maîtriser les superpositions géométriques avec Aspose.GIS pour .NET

## Introduction
Dans le domaine des systèmes d'information géographique (SIG), les opérations de superposition sont fondamentales pour l'analyse spatiale. Ils permettent de comparer et de combiner différents ensembles de données spatiales pour obtenir des informations précieuses. Aspose.GIS pour .NET fournit des fonctionnalités robustes pour effectuer efficacement des superpositions géométriques. Dans ce didacticiel, nous aborderons diverses opérations de superposition telles que l'intersection, l'union, la différence et la différence symétrique à l'aide d'Aspose.GIS pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
### 1. Environnement de développement .NET
Assurez-vous d'avoir un environnement de développement .NET configuré sur votre ordinateur. Vous pouvez télécharger et installer le SDK .NET à partir du site Web .NET.
### 2. Aspose.GIS pour la bibliothèque .NET
 Téléchargez et installez la bibliothèque Aspose.GIS pour .NET à partir du[site web](https://releases.aspose.com/gis/net/).
## Importer des espaces de noms
Avant de pouvoir commencer à utiliser Aspose.GIS pour .NET, vous devez importer les espaces de noms nécessaires dans votre projet.
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Étape 1 : Créer des objets polygones
Tout d’abord, nous allons définir deux objets polygones représentant des régions spatiales.
```csharp
var polygon1 = new Polygon();
polygon1.ExteriorRing = new LinearRing(new[]
{
	 new Point(0, 0),
	 new Point(0, 2),
	 new Point(2, 2),
	 new Point(2, 0),
	 new Point(0, 0),
 });
var polygon2 = new Polygon();
polygon2.ExteriorRing = new LinearRing(new[]
{
	new Point(1, 1),
	new Point(1, 3),
	new Point(3, 3),
	new Point(3, 1),
	new Point(1, 1),
});
```
## Étape 2 : Effectuer une opération d’intersection
Ensuite, trouvons l'intersection des deux polygones.
```csharp
var intersection = polygon1.Intersection(polygon2);
Console.WriteLine("Intersection type is {0}", intersection.GeometryType); // Polygone
```
## Étape 3 : Imprimer les points d'intersection
Nous allons imprimer les points du polygone d'intersection.
```csharp
PrintRing(((IPolygon)intersection).ExteriorRing);
```
## Étape 4 : Effectuer une opération d’union
Maintenant, trouvons l'union des deux polygones.
```csharp
var union = polygon1.Union(polygon2);
Console.WriteLine("Union type is {0}", union.GeometryType); // Polygone
```
## Étape 5 : Imprimer les points d'union
Imprimez les points du polygone d'union.
```csharp
PrintRing(((IPolygon)union).ExteriorRing);
```
## Étape 6 : Effectuer une opération de différence
Trouvons ensuite la différence entre les deux polygones.
```csharp
var difference = polygon1.Difference(polygon2);
Console.WriteLine("Difference type is {0}", difference.GeometryType); // Polygone
```
## Étape 7 : Imprimer les points de différence
Imprimez les points du polygone de différence.
```csharp
PrintRing(((IPolygon)difference).ExteriorRing);
```
## Étape 8 : Effectuer une opération de différence symétrique
Enfin, trouvons la différence symétrique entre les deux polygones.
```csharp
var symDifference = polygon1.SymDifference(polygon2);
Console.WriteLine("Symmetric Difference type is {0}", symDifference.GeometryType); // MultiPolygone
```
## Étape 9 : Imprimer les polygones de différence symétriques
Imprimez les points de chaque polygone dans la différence symétrique.
```csharp
var multiPolygon = (IMultiPolygon)symDifference;
Console.WriteLine("Polygons count is {0}", multiPolygon.Count); // 2
PrintRing(((IPolygon)multiPolygon[0]).ExteriorRing);
PrintRing(((IPolygon)multiPolygon[1]).ExteriorRing);
```
## Conclusion
La maîtrise des superpositions géométriques est cruciale dans l'analyse spatiale et Aspose.GIS pour .NET fournit un ensemble complet d'outils pour effectuer ces opérations efficacement. En suivant ce didacticiel, vous avez appris à utiliser Aspose.GIS pour .NET pour effectuer des opérations d'intersection, d'union, de différence et de différence symétrique sur des formes géométriques.
## FAQ
### Q : Puis-je utiliser Aspose.GIS pour .NET dans mes projets commerciaux ?
Oui, Aspose.GIS pour .NET peut être utilisé dans des projets commerciaux et non commerciaux.
### Q : Existe-t-il une version d'essai disponible pour Aspose.GIS pour .NET ?
 Oui, vous pouvez télécharger une version d'essai gratuite à partir de[ici](https://releases.aspose.com/).
### Q : Comment puis-je obtenir une assistance pour Aspose.GIS pour .NET ?
 Vous pouvez obtenir de l'aide sur le forum de la communauté Aspose.GIS[ici](https://forum.aspose.com/c/gis/33).
### Q : Existe-t-il des licences temporaires disponibles pour Aspose.GIS pour .NET ?
 Oui, des licences temporaires sont disponibles à des fins de test et d'évaluation. Vous pouvez les obtenir auprès de[ici](https://purchase.aspose.com/temporary-license/).
### Q : Puis-je acheter Aspose.GIS pour .NET directement ?
 Oui, vous pouvez acheter Aspose.GIS pour .NET sur le site Web[ici](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
