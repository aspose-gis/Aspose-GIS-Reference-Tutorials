---
title: Compter les géométries en géométrie avec Aspose.GIS
linktitle: Compter les géométries en géométrie
second_title: API Aspose.GIS .NET
description: Apprenez à compter les géométries dans une géométrie à l'aide d'Aspose.GIS pour .NET. Tutoriel étape par étape avec des exemples de code pour les développeurs.
type: docs
weight: 23
url: /fr/net/geometry-creation/count-geometries-in-geometry/
---
## Introduction
Aspose.GIS pour .NET est un outil puissant pour les développeurs cherchant à intégrer des fonctionnalités géospatiales dans leurs applications .NET. Que vous créiez un logiciel de cartographie, des services basés sur la localisation ou des outils d'analyse spatiale, Aspose.GIS fournit un ensemble complet de fonctionnalités pour répondre à vos besoins. Dans ce didacticiel, nous allons explorer comment compter les géométries au sein d'une géométrie à l'aide d'Aspose.GIS pour .NET.
## Conditions préalables
Avant de vous lancer dans ce didacticiel, assurez-vous d'avoir les prérequis suivants :
1. Visual Studio : assurez-vous que Visual Studio est installé sur votre système.
2. Aspose.GIS pour .NET : téléchargez et installez Aspose.GIS pour .NET à partir du[page de téléchargement](https://releases.aspose.com/gis/net/).
3. Connaissance de base de C# : Familiarisez-vous avec les bases du langage de programmation C#.

## Importer des espaces de noms
Avant de commencer le codage, vous devez importer les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.GIS.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Étape 2 : Créer une géométrie de points
```csharp
Point point = new Point(40.7128, -74.006);
```
 Ici, nous créons un`Point` géométrie avec latitude 40.7128 et longitude -74.006.
## Étape 3 : Créer une géométrie LineString
```csharp
LineString line = new LineString();
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```
 Cette étape crée un`LineString` géométrie et y ajoute deux points.
## Étape 4 : Créer une collection de géométries
```csharp
GeometryCollection geometryCollection = new GeometryCollection();
geometryCollection.Add(point);
geometryCollection.Add(line);
```
 Nous créons ensuite un`GeometryCollection` et ajoutez-y les géométries de points et de lignes précédemment créées.
## Étape 5 : Compter les géométries
```csharp
int geometriesCount = geometryCollection.Count;
```
 Cette étape compte le nombre de géométries dans le`GeometryCollection`.
## Étape 6 : Afficher le décompte
```csharp
Console.WriteLine(geometriesCount); // 2
```
 Enfin, nous imprimons le nombre de géométries, qui dans ce cas est`2`.

## Conclusion
Dans ce didacticiel, nous avons appris à compter les géométries au sein d'une géométrie à l'aide d'Aspose.GIS pour .NET. En suivant ces étapes, vous pouvez facilement intégrer des fonctionnalités géospatiales dans vos applications .NET.
## FAQ
### Aspose.GIS pour .NET est-il adapté aux applications de bureau et Web ?
Oui, Aspose.GIS pour .NET peut être utilisé de manière transparente dans les applications de bureau et Web.
### Puis-je effectuer des requêtes spatiales à l’aide d’Aspose.GIS pour .NET ?
Absolument, Aspose.GIS pour .NET fournit une prise en charge robuste pour effectuer des requêtes spatiales sur des géométries.
### Aspose.GIS pour .NET prend-il en charge différents formats de fichiers SIG ?
Oui, Aspose.GIS pour .NET prend en charge un large éventail de formats de fichiers SIG, notamment SHP, KML et GeoJSON.
### Existe-t-il un essai gratuit disponible pour Aspose.GIS pour .NET ?
 Oui, vous pouvez télécharger un essai gratuit à partir du[site web](https://releases.aspose.com/).
### Où puis-je trouver de l’assistance pour Aspose.GIS pour .NET ?
 Vous pouvez trouver de l'aide sur le[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).