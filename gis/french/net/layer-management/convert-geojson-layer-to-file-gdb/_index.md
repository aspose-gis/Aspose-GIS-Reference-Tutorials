---
title: Conversion GeoJSON en fichier GDB démystifiée
linktitle: Convertir la couche GeoJSON en fichier GDB
second_title: API Aspose.GIS .NET
description: Débloquez des merveilles géospatiales avec Aspose.GIS pour .NET ! Convertissez sans effort les couches GeoJSON en géodatabases fichier. Essayez-le maintenant! #Aspose #SIG
weight: 17
url: /fr/net/layer-management/convert-geojson-layer-to-file-gdb/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Conversion GeoJSON en fichier GDB démystifiée

## Introduction
Dans le domaine dynamique des systèmes d’information géographique (SIG), la capacité de convertir de manière transparente les données entre différents formats est cruciale. Aspose.GIS pour .NET apparaît comme un allié puissant, offrant une suite complète d'outils pour gérer les données géospatiales sans effort. Dans ce didacticiel, nous aborderons le processus de conversion d'une couche GeoJSON en une géodatabase fichier (File GDB) à l'aide d'Aspose.GIS pour .NET.
## Conditions préalables
Avant de vous lancer dans ce voyage géospatial, assurez-vous d’avoir les conditions préalables suivantes en place :
- Une connaissance pratique de la programmation .NET.
-  Aspose.GIS pour .NET installé. Sinon, téléchargez-le depuis[ici](https://releases.aspose.com/gis/net/) et suivez les instructions d'installation.
## Importer des espaces de noms
Pour lancer le processus de conversion, commencez par importer les espaces de noms nécessaires :
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
Maintenant, décomposons le processus en un guide étape par étape :
## Étape 1 : Configurer la couche GeoJSON
Commencez par créer une couche GeoJSON avec les attributs et fonctionnalités pertinents. Voici un extrait pour vous guider :
```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Ajouter des attributs
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    //Construire et ajouter des fonctionnalités
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```
## Étape 2 : Copier l'ensemble de données de test
Pour préserver l'intégrité de vos données de test, créez une copie de l'ensemble de données. Utilisez l'extrait de code suivant :
```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```
## Étape 3 : Convertir GeoJSON en fichier GDB
Il est maintenant temps d'effectuer la conversion. Utilisez le code suivant :
```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copier les attributs
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Ajouter des fonctionnalités
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```
## Conclusion
Dans ce didacticiel, nous avons parcouru le terrain fascinant de la conversion d'une couche GeoJSON en géodatabase fichier à l'aide d'Aspose.GIS pour .NET. Fort de ces connaissances, vous êtes désormais équipé pour manipuler de manière transparente les données géospatiales dans vos applications .NET.
## FAQ
### Aspose.GIS est-il compatible avec le dernier framework .NET ?
Oui, Aspose.GIS est compatible avec les dernières versions du framework .NET.
### Puis-je convertir d'autres formats géospatiaux à l'aide d'Aspose.GIS ?
Absolument! Aspose.GIS prend en charge un large éventail de formats géospatiaux pour une manipulation polyvalente des données.
### Existe-t-il une version d'essai disponible pour Aspose.GIS ?
 Oui, vous pouvez explorer les fonctionnalités d'Aspose.GIS en téléchargeant la version d'essai[ici](https://releases.aspose.com/).
### Comment puis-je obtenir de l'aide pour les requêtes liées à Aspose.GIS ?
 Rendez-vous sur Aspose.GIS[forum](https://forum.aspose.com/c/gis/33) pour un soutien dédié.
### Puis-je obtenir une licence temporaire pour Aspose.GIS ?
 Oui, vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
