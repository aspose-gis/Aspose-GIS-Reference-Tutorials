---
title: Extraire les fonctionnalités vers GeoJSON
linktitle: Extraire les fonctionnalités vers GeoJSON
second_title: API Aspose.GIS .NET
description: Explorez le guide étape par étape sur l'utilisation d'Aspose.GIS pour .NET pour extraire des fonctionnalités vers GeoJSON. Exploitez facilement la puissance du SIG ! #Aspose #SIG
weight: 23
url: /fr/net/layer-management/extract-features-to-geojson/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extraire les fonctionnalités vers GeoJSON

## Introduction
Bienvenue dans notre didacticiel étape par étape sur l'extraction de fonctionnalités vers GeoJSON à l'aide d'Aspose.GIS pour .NET ! Que vous soyez un développeur chevronné ou que vous commenciez tout juste votre parcours dans la programmation SIG, ce guide vous guidera tout au long du processus, vous garantissant d'exploiter toute la puissance d'Aspose.GIS pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
-  Aspose.GIS pour .NET : assurez-vous que la bibliothèque est installée. Sinon, vous pouvez le télécharger depuis le[Page Aspose.GIS pour .NET](https://releases.aspose.com/gis/net/).
-  Données de fichier Shape : préparez un fichier Shape pour la saisie. Si vous avez besoin d'exemples de données, vous pouvez les trouver dans le[Documentation Aspose.GIS](https://reference.aspose.com/gis/net/).
- Environnement .NET : configurez un environnement .NET pour exécuter le code fourni.
- Répertoire de documents : définissez le chemin d'accès à votre répertoire de documents dans l'extrait de code.
Maintenant que tout est en place, commençons à extraire les fonctionnalités vers GeoJSON !
## Importer des espaces de noms
Tout d'abord, incluez les espaces de noms nécessaires dans votre code :
```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Ces espaces de noms sont essentiels pour travailler avec les fonctionnalités d'Aspose.GIS.
## Étape 1 : ouvrir le fichier de formes d'entrée
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Votre code pour traiter le fichier de formes d'entrée va ici
}
```
 Ouvrez le Shapefile d'entrée à l'aide du`VectorLayer.Open` méthode.
## Étape 2 : Créer une sortie GeoJSON
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Votre code pour créer la sortie GeoJSON va ici
}
```
 Créez la sortie GeoJSON à l'aide du`VectorLayer.Create` méthode.
## Étape 3 : Copier les attributs
```csharp
outputLayer.CopyAttributes(inputLayer);
```
 Copiez les attributs de la couche d'entrée vers la couche de sortie à l'aide du`CopyAttributes` méthode.
## Étape 4 : Caractéristiques du processus
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Votre code pour traiter chaque fonctionnalité d'entrée va ici
}
```
Parcourez chaque entité de la couche d’entrée et traitez-les individuellement.
## Étape 5 : Filtrer les fonctionnalités par date
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Filtrer les fonctionnalités en fonction d'une condition de date. Dans cet exemple, les fonctionnalités dont la date de naissance est antérieure à 1982 sont ignorées.
## Étape 6 : Construire une nouvelle fonctionnalité
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Construisez une nouvelle entité pour la couche de sortie, en copiant la géométrie et les valeurs de l’entité en entrée.
Toutes nos félicitations! Vous avez réussi à extraire des fonctionnalités vers GeoJSON à l'aide d'Aspose.GIS pour .NET.
## Conclusion
Dans ce didacticiel, nous avons exploré le processus d'extraction de fonctionnalités vers GeoJSON à l'aide d'Aspose.GIS pour .NET. Cette puissante bibliothèque ouvre un monde de possibilités pour le développement de SIG. Expérimentez avec différents ensembles de données et fonctionnalités pour libérer tout le potentiel d’Aspose.GIS.
## FAQ
### Q : Où puis-je trouver plus de documentation ?
 Visiter le[Documentation Aspose.GIS](https://reference.aspose.com/gis/net/) pour des informations détaillées.
### Q : Comment puis-je obtenir une licence temporaire ?
 Vous pouvez obtenir un permis temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Q : Où puis-je demander de l'aide ?
 Rejoins[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le soutien et les discussions de la communauté.
### Q : Existe-t-il un essai gratuit ?
 Oui, vous pouvez trouver l'essai gratuit[ici](https://releases.aspose.com/).
### Q : Où puis-je acheter Aspose.GIS pour .NET ?
 Vous pouvez acheter le produit[ici](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
