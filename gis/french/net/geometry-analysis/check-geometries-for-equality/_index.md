---
title: Vérifier les géométries pour l'égalité
linktitle: Vérifier les géométries pour l'égalité
second_title: API Aspose.GIS .NET
description: Apprenez à utiliser Aspose.GIS pour .NET pour vérifier l'égalité des géométries dans vos applications .NET avec ce didacticiel complet.
type: docs
weight: 10
url: /fr/net/geometry-analysis/check-geometries-for-equality/
---
## Introduction
Aspose.GIS for .NET est une bibliothèque puissante qui permet aux développeurs de travailler efficacement avec des données géospatiales dans leurs applications .NET. Que vous créiez des applications cartographiques, des outils d'analyse spatiale ou que vous intégriez des fonctionnalités géospatiales dans des logiciels existants, Aspose.GIS fournit les outils dont vous avez besoin pour accomplir votre travail.
## Conditions préalables
Avant de vous lancer dans l'utilisation d'Aspose.GIS pour .NET, assurez-vous d'avoir les conditions préalables suivantes en place :
### .NET Framework installé
Assurez-vous que le .NET Framework est installé sur votre système. Vous pouvez le télécharger sur le site Web de Microsoft.
### Aspose.GIS pour la bibliothèque .NET
 Téléchargez et installez la bibliothèque Aspose.GIS pour .NET à partir du[page de téléchargement](https://releases.aspose.com/gis/net/). Suivez les instructions d'installation fournies dans la documentation.
### Environnement de développement
Configurez votre environnement de développement préféré, tel que Visual Studio, pour le développement .NET.

## Importer des espaces de noms
Dans votre application .NET, importez les espaces de noms nécessaires pour utiliser la fonctionnalité Aspose.GIS :
```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Étape 1 : Définir les géométries
Tout d’abord, définissez les géométries que vous souhaitez comparer. Dans cet exemple, nous avons deux géométries :`geometry1` et`geometry2`.
```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```
## Étape 2 : Vérifier l'égalité des géométries
 Maintenant, vérifiez si les géométries sont spatialement égales à l'aide de la`SpatiallyEquals` méthode fournie par Aspose.GIS.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // Vrai
```
 Cela imprimera`True` à la console depuis`geometry1` et`geometry2` sont spatialement égaux.
## Étape 3 : Modifier la géométrie
 Ensuite, modifions`geometry2` en ajoutant un nouveau point.
```csharp
geometry2.AddPoint(3, 3);
```
## Étape 4 : Revérifier l'égalité
Maintenant, revérifiez l'égalité des géométries après la modification.
```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // FAUX
```
 Cette fois, le résultat sera`False` puisque les géométries ne sont plus spatialement égales en raison de la modification apportée à`geometry2`.

## Conclusion
En conclusion, Aspose.GIS pour .NET fournit des outils puissants pour travailler avec des données géospatiales dans les applications .NET. En suivant ce guide étape par étape, vous pouvez facilement vérifier l'égalité des géométries à l'aide des méthodes Aspose.GIS.
## FAQ
### Puis-je utiliser Aspose.GIS pour .NET avec d’autres frameworks .NET ?
Oui, Aspose.GIS pour .NET est compatible avec divers frameworks .NET, notamment .NET Core et .NET Standard.
### Existe-t-il un essai gratuit disponible pour Aspose.GIS pour .NET ?
 Oui, vous pouvez télécharger un essai gratuit à partir du[page des versions](https://releases.aspose.com/).
### Où puis-je trouver de la documentation pour Aspose.GIS pour .NET ?
 Vous pouvez trouver une documentation détaillée sur le[Page de documentation Aspose.GIS](https://reference.aspose.com/gis/net/).
### Comment puis-je obtenir de l'assistance pour Aspose.GIS pour .NET ?
 Vous pouvez obtenir de l'aide sur le forum de la communauté Aspose.GIS[ici](https://forum.aspose.com/c/gis/33).
### Puis-je acheter une licence temporaire pour Aspose.GIS pour .NET ?
 Oui, vous pouvez acheter une licence temporaire auprès du[page d'achat](https://purchase.aspose.com/temporary-license/).