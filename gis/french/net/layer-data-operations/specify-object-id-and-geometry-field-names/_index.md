---
title: Spécifier l'ID d'objet et les noms de champs de géométrie
linktitle: Spécifier l'ID d'objet et les noms de champs de géométrie
second_title: API Aspose.GIS .NET
description: Explorez la magie des SIG avec Aspose.GIS pour .NET ! Gérez les données géospatiales sans effort. Téléchargez-le maintenant et libérez la puissance de l'intelligence spatiale.
type: docs
weight: 20
url: /fr/net/layer-data-operations/specify-object-id-and-geometry-field-names/
---
## Introduction
Se lancer dans un voyage dans le domaine des systèmes d'information géographique (SIG) à l'aide d'Aspose.GIS pour .NET ouvre un monde de possibilités aussi bien pour les développeurs que pour les passionnés. Cette puissante bibliothèque vous permet de gérer les données géospatiales sans effort. Dans ce didacticiel, nous vous guiderons tout au long du processus de spécification des noms de champs d'ID d'objet et de géométrie, jetant ainsi les bases de vos efforts SIG.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
-  Aspose.GIS pour .NET : téléchargez et installez la bibliothèque à partir de[ici](https://releases.aspose.com/gis/net/).
- Répertoire de documents : configurez un répertoire pour vos documents afin de stocker les géodatabases.
- Environnement .NET : assurez-vous de disposer d'un environnement .NET fonctionnel.
## Importer des espaces de noms
Pour démarrer, vous devez importer les espaces de noms nécessaires dans votre projet. Ces espaces de noms fournissent les classes et méthodes essentielles pour interagir avec Aspose.GIS pour .NET.
```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```
## Étape 1 : Spécifier l'ID d'objet et les noms de champs de géométrie
Dans cette étape, vous apprendrez à configurer les noms des champs ID d'objet et Géométrie pour vos données SIG. Ceci est crucial pour une gestion efficace des données.
## Étape 1.1 : Définir le répertoire des documents
Commencez par définir le chemin d'accès à votre répertoire de documents :
```csharp
string dataDir = "Your Document Directory";
```
## Étape 1.2 : Créer une géodatabase et définir les options
Créez une géodatabase avec les noms de champs d'ID d'objet et de géométrie spécifiés :
```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Spécifiez le nom du champ ID d'objet
        GeometryFieldName = "POINT",       // Spécifiez le nom du champ Géométrie
    };
```
## Étape 1.3 : Créer et ajouter un calque
Créez une couche dans la géodatabase et ajoutez une entité avec une géométrie spécifique :
```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  //Spécifiez la géométrie (dans ce cas, un point)
    layer.Add(feature);
}
```
## Étape 1.4 : Ouvrir et récupérer les données de la couche
Ouvrez la couche et récupérez les données en fonction de l'ID d'objet spécifié :
```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Sortie : 1
}
```
## Conclusion
Toutes nos félicitations! Vous avez parcouru avec succès le processus de spécification des noms de champs d'ID d'objet et de géométrie à l'aide d'Aspose.GIS pour .NET. Cela constitue une base solide pour vos projets SIG, vous permettant de gérer facilement les données géospatiales.
## Questions fréquemment posées
### Q : Puis-je utiliser Aspose.GIS pour .NET dans mes applications Web ?
R : Oui, Aspose.GIS pour .NET convient aux applications de bureau et Web, offrant des fonctionnalités géospatiales polyvalentes.
### Q : Existe-t-il une version d'essai disponible avant d'acheter ?
 R : Oui, vous pouvez explorer les fonctionnalités d'Aspose.GIS pour .NET avec un essai gratuit disponible.[ici](https://releases.aspose.com/).
### Q : Comment puis-je obtenir une licence temporaire pour Aspose.GIS pour .NET ?
 R : Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/) à des fins d’évaluation.
### Q : Quels systèmes de référence spatiale Aspose.GIS pour .NET prend-il en charge ?
R : Aspose.GIS pour .NET prend en charge divers systèmes de référence spatiale, offrant ainsi une flexibilité pour différents ensembles de données géographiques.
### Q : Où puis-je demander de l'aide ou discuter des requêtes liées à Aspose.GIS ?
 R : Visitez le forum Aspose.GIS[ici](https://forum.aspose.com/c/gis/33) pour du soutien et des discussions.