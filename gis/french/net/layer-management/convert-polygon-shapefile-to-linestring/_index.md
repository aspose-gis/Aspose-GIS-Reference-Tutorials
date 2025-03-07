---
title: Convertir un fichier de formes de polygone en chaîne de lignes
linktitle: Convertir un fichier de formes de polygone en chaîne de lignes
second_title: API Aspose.GIS .NET
description: Explorez la puissance d'Aspose.GIS pour .NET et convertissez sans effort les fichiers de formes de polygones en chaînes de lignes. Boostez votre développement SIG dès aujourd'hui !
weight: 18
url: /fr/net/layer-management/convert-polygon-shapefile-to-linestring/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir un fichier de formes de polygone en chaîne de lignes

## Introduction
Si vous travaillez avec des systèmes d'information géographique (SIG) dans .NET, Aspose.GIS est une bibliothèque puissante qui peut simplifier vos tâches. Dans ce didacticiel, nous vous guiderons tout au long du processus de conversion d'un fichier de formes polygonales en chaîne de lignes à l'aide d'Aspose.GIS. Cela peut être particulièrement utile lorsque vous devez extraire des entités linéaires à partir de données polygonales pour diverses applications telles que la planification d'itinéraires ou l'analyse de réseau.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants en place :
-  Bibliothèque Aspose.GIS : téléchargez et installez la bibliothèque Aspose.GIS à partir du[site web](https://releases.aspose.com/gis/net/).
- Données de fichier de formes : préparez un fichier de formes de polygones pour la conversion. Si vous n'en avez pas, vous pouvez trouver des exemples de données ou créer les vôtres.
- Environnement de développement : configurez votre environnement de développement .NET avec les outils nécessaires.
## Importer des espaces de noms
Dans votre code C#, vous devez importer les espaces de noms Aspose.GIS pour accéder aux classes et méthodes requises. Ajoutez les espaces de noms suivants au début de votre fichier de code :
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Étape 1 : Définir le répertoire des documents
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
```
Remplacez « Votre répertoire de documents » par le chemin d'accès au répertoire où se trouve votre Shapefile.
## Étape 2 : ouvrez le fichier de formes source
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Le reste du code ira ici
}
```
Cette étape ouvre le Polygon Shapefile source pour la lecture.
## Étape 3 : Créer le fichier de formes de chaîne de ligne de destination
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Le reste du code ira ici
}
```
Ici, nous créons un nouveau Linestring Shapefile pour écrire les données converties.
## Étape 4 : Parcourir les fonctionnalités sources
```csharp
foreach (Feature sourceFeature in source)
{
    // Le reste du code ira ici
}
```
Cette boucle parcourt chaque entité du fichier Polygon Shapefile source.
## Étape 5 : Convertir le polygone en chaîne de lignes et écrire dans la destination
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Au cours de cette étape, chaque entité Polygon est convertie en Linestring et l'entité Linestring résultante est écrite dans le Shapefile de destination.
## Conclusion
En suivant ces étapes, vous pouvez facilement convertir un fichier de formes de polygone en chaîne de lignes à l'aide d'Aspose.GIS pour .NET. Ce processus ouvre de nouvelles possibilités d'analyse et de visualisation des données dans les applications SIG.

## FAQ
### Aspose.GIS est-il compatible avec toutes les versions de .NET ?
Oui, Aspose.GIS prend en charge différentes versions de .NET, garantissant la compatibilité avec votre environnement de développement.
### Puis-je utiliser Aspose.GIS pour des projets commerciaux ?
 Oui, vous pouvez. Pour utiliser Aspose.GIS dans des projets commerciaux, envisagez d'acheter une licence[ici](https://purchase.aspose.com/buy).
### Existe-t-il des exemples ou de la documentation disponible ?
 Oui, vous pouvez trouver une documentation complète et des exemples sur le[page de documentation](https://reference.aspose.com/gis/net/).
### Existe-t-il une version d'essai disponible ?
 Oui, vous pouvez explorer Aspose.GIS avec un essai gratuit en visitant[ce lien](https://releases.aspose.com/).
### Où puis-je demander de l’aide ou du soutien ?
 Visiter le[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour toute assistance ou question relative au support.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
