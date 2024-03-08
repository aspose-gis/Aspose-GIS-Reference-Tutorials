---
title: Spécifier la variante WKT lors de la traduction à l'aide d'Aspose.GIS
linktitle: Spécifier la variante WKT lors de la traduction
second_title: API Aspose.GIS .NET
description: Découvrez comment spécifier des variantes WKT dans Aspose.GIS pour .NET afin de contrôler efficacement le format et la précision de la représentation des données spatiales.
type: docs
weight: 19
url: /fr/net/geometry-processing/specify-wkt-variant-on-translation/
---
## Introduction
Aspose.GIS pour .NET est une bibliothèque puissante qui permet aux développeurs de travailler sans effort avec les données du système d'information géographique (SIG) dans leurs applications .NET. L'une des fonctionnalités essentielles fournies par Aspose.GIS est la possibilité de spécifier la variante Well-Known Text (WKT) lors de la traduction, permettant aux utilisateurs de contrôler le format et la précision des représentations de données spatiales. Dans ce didacticiel, nous explorerons comment spécifier les variantes WKT étape par étape à l'aide d'Aspose.GIS pour .NET.
## Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
1. Aspose.GIS pour .NET : téléchargez et installez Aspose.GIS pour .NET à partir du[page de téléchargement](https://releases.aspose.com/gis/net/).
2. Environnement de développement : assurez-vous d'avoir configuré un environnement de développement .NET.
3. Connaissances de base : Familiarité avec le langage de programmation C# et le framework .NET.

## Importer des espaces de noms
Avant d'utiliser la fonctionnalité Aspose.GIS dans votre code, importez les espaces de noms nécessaires :
```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```
## Étape 1 : Créer un objet ponctuel
 Tout d'abord, créez un`Point` objet avec des valeurs de latitude, de longitude et de mesure facultative (M) :
```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```
## Étape 2 : Définir le système de référence spatiale (SRS)
Attribuez un système de référence spatiale (SRS) à l’objet ponctuel. Dans cet exemple, nous utilisons le système de référence spatiale WGS84 :
```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```
## Étape 3 : Spécifiez la variante WKT
 Maintenant, spécifiez la variante WKT pour la traduction. Aspose.GIS prend en charge diverses variantes de WKT, notamment`Iso`, `SimpleFeatureAccessOutdated` , et`ExtendedPostGis`. Choisissez la variante appropriée en fonction de vos besoins :
```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINTE (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23,5732, 25,3421, 40,3)
```
## Étape 4 : Contrôler le format numérique
Vous pouvez contrôler le format numérique des coordonnées dans la représentation WKT. Aspose.GIS fournit des options pour spécifier la précision décimale :
```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.29999999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23,6 25,3 40,3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Conclusion
Dans ce didacticiel, nous avons appris à spécifier des variantes WKT lors de la traduction à l'aide d'Aspose.GIS pour .NET. En suivant les étapes décrites ci-dessus, les développeurs peuvent contrôler efficacement le format et la précision des représentations de données spatiales dans leurs applications .NET, améliorant ainsi la flexibilité et la convivialité des systèmes d'information géographique.
## FAQ
### Aspose.GIS est-il compatible avec toutes les versions de .NET ?
Oui, Aspose.GIS prend en charge .NET Framework 4.0 et versions ultérieures.
### Puis-je utiliser Aspose.GIS pour des projets commerciaux ?
Oui, Aspose.GIS peut être utilisé pour des projets personnels et commerciaux.
### Aspose.GIS prend-il en charge d'autres formats de données spatiales ?
Oui, Aspose.GIS prend en charge un large éventail de formats de données spatiales, notamment ESRI Shapefile, GeoJSON et KML.
### Existe-t-il un essai gratuit disponible pour Aspose.GIS ?
 Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.GIS à partir de[ici](https://releases.aspose.com/).
### Où puis-je obtenir de l'aide ou du support pour Aspose.GIS ?
 Vous pouvez publier vos requêtes ou demander de l'aide à la communauté Aspose.GIS à l'adresse[forum](https://forum.aspose.com/c/gis/33).