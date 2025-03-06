---
title: Vérifier que la géométrie en contient une autre
linktitle: Vérifier que la géométrie en contient une autre
second_title: API Aspose.GIS .NET
description: Explorez Aspose.GIS pour .NET, une bibliothèque robuste pour une intégration transparente des données géospatiales dans vos applications .NET.
weight: 14
url: /fr/net/geometry-analysis/check-geometry-contains-another/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vérifier que la géométrie en contient une autre

## Introduction
Aspose.GIS for .NET est une bibliothèque puissante qui permet aux développeurs de travailler de manière transparente avec des données géospatiales au sein de leurs applications .NET. Que vous créiez une application de cartographie, effectuiez une analyse géospatiale ou intégriez des fonctionnalités basées sur la localisation dans votre logiciel, Aspose.GIS simplifie le processus en fournissant des API intuitives et des fonctionnalités robustes.
## Conditions préalables
Avant de vous lancer dans l'utilisation d'Aspose.GIS pour .NET, assurez-vous de disposer des conditions préalables suivantes :
### 1. Configuration de l'environnement de développement .NET
Assurez-vous de disposer d'un environnement de développement .NET fonctionnel configuré sur votre ordinateur. Cela inclut l'installation et la configuration correctes du SDK .NET.
### 2. Installation d'Aspose.GIS
 Installez Aspose.GIS pour .NET en téléchargeant la bibliothèque à partir de la page de version[ici](https://releases.aspose.com/gis/net/) . Suivez les instructions d'installation fournies dans la documentation[ici](https://reference.aspose.com/gis/net/)pour intégrer Aspose.GIS dans votre projet.
### 3. Compréhension de base de C#
Familiarisez-vous avec le langage de programmation C# car Aspose.GIS pour .NET est principalement utilisé avec C#.

## Importer des espaces de noms
Dans votre projet C#, importez les espaces de noms nécessaires pour utiliser les fonctionnalités d'Aspose.GIS :
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Étape 1 : Définir les objets géométriques
Tout d'abord, définissez les objets géométriques à l'aide des classes Aspose.GIS :
```csharp
var geometry1 = new Polygon();
geometry1.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 4),
    new Point(4, 4),
    new Point(4, 0),
    new Point(0, 0),
});
geometry1.AddInteriorRing(new LinearRing(new[]
{
    new Point(1, 1),
    new Point(1, 3),
    new Point(3, 3),
    new Point(3, 1),
    new Point(1, 1),
}));
var geometry2 = new Point(2, 2);
```
## Étape 2 : Vérifier le confinement spatial
Ensuite, vérifiez si une géométrie en contient une autre :
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry2)); // FAUX
```
## Étape 3 : Définir une autre géométrie
Définissez un autre objet géométrique :
```csharp
var geometry3 = new Point(0.5, 0.5);
```
## Étape 4 : Vérifiez à nouveau le confinement spatial
Vérifiez si la géométrie nouvellement définie est contenue dans la première géométrie :
```csharp
Console.WriteLine(geometry1.SpatiallyContains(geometry3)); // Vrai
```
## Étape 5 : Fonctionnalité équivalente
 Comprendre que`a.SpatiallyContains(b)` est équivalent à`b.Within(a)`:
```csharp
Console.WriteLine(geometry3.Within(geometry1)); // Vrai
```

## Conclusion
En conclusion, Aspose.GIS pour .NET fournit des outils puissants pour gérer les données géospatiales dans les applications .NET. En suivant ce guide et en utilisant l'exemple fourni, vous pouvez effectuer efficacement des contrôles de confinement spatial et exploiter d'autres fonctionnalités géospatiales au sein de vos projets.
## FAQ
### Q1 : Aspose.GIS est-il compatible avec .NET Core ?
R : Oui, Aspose.GIS prend entièrement en charge .NET Core, vous permettant de développer des applications géospatiales sur différentes plates-formes.
### Q2 : Puis-je effectuer une analyse géospatiale à l’aide d’Aspose.GIS ?
R : Absolument, Aspose.GIS offre diverses fonctionnalités pour l'analyse géospatiale, notamment des requêtes spatiales, des calculs de distance et des manipulations géométriques.
### Q3 : À quelle fréquence les mises à jour sont-elles publiées pour Aspose.GIS ?
R : Aspose.GIS publie régulièrement des mises à jour pour améliorer les performances, ajouter de nouvelles fonctionnalités et résoudre tout problème signalé. Vous pouvez rester à jour en visitant la page de publication.
### Q4 : Existe-t-il un forum communautaire pour les utilisateurs d'Aspose.GIS ?
 : Oui, vous pouvez rejoindre le forum de la communauté Aspose.GIS[ici](https://forum.aspose.com/c/gis/33) pour vous connecter avec d'autres utilisateurs, poser des questions et partager vos expériences.
### Q5 : Puis-je essayer Aspose.GIS avant d’acheter ?
 R : Vous pouvez certainement explorer Aspose.GIS en téléchargeant la version d'essai gratuite à partir de[ici](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
