---
title: Maîtrise SIG - Ajouter des couches à GDB avec Aspose.GIS pour .NET
linktitle: Ajouter une couche au fichier de l'ensemble de données GDB
second_title: API Aspose.GIS .NET
description: Libérez la puissance du SIG avec Aspose.GIS pour .NET ! Découvrez comment ajouter des couches aux ensembles de données File GDB dans ce didacticiel étape par étape. #données géographiques #Aspose #SIG
type: docs
weight: 16
url: /fr/net/layer-management/add-layer-to-file-gdb-dataset/
---
## Introduction
Êtes-vous prêt à améliorer vos capacités SIG à l'aide d'Aspose.GIS pour .NET ? Dans ce guide étape par étape, nous vous guiderons tout au long du processus d'ajout d'une couche à un jeu de données de géodatabase fichier (GDB). Aspose.GIS pour .NET fournit des fonctionnalités puissantes pour manipuler les informations géographiques, et avec ce didacticiel, vous pourrez intégrer de manière transparente des couches supplémentaires dans vos ensembles de données.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
-  Bibliothèque Aspose.GIS pour .NET : téléchargez et installez la bibliothèque à partir du[Documentation Aspose.GIS pour .NET](https://reference.aspose.com/gis/net/).
- Répertoire de documents : créez un répertoire de documents dédié sur votre ordinateur pour stocker et gérer les fichiers liés au SIG.
## Importer des espaces de noms
Dans votre projet .NET, assurez-vous d'importer les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.GIS. Utilisez l'extrait de code suivant :
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
## Étape 1 : Copier le répertoire
Avant de continuer, dupliquez le répertoire contenant votre jeu de données GDB. Cette étape garantit que l’ensemble de données d’origine reste intact. Utilisez l'extrait de code fourni :
```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```
## Étape 2 : Ouvrir l'ensemble de données et vérifier la capacité de création
 Ouvrez l'ensemble de données dupliqué et vérifiez s'il peut créer des couches. Ceci est confirmé par la présence de`True` dans la sortie de la console.
```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // Vrai
```
## Étape 3 : Créer et remplir un nouveau calque
Créez une nouvelle couche dans l'ensemble de données, en définissant son système de référence spatiale, ses attributs et un exemple d'entité. Cet extrait de code illustre le processus :
```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```
## Étape 4 : ouvrir et valider le calque ajouté
Ouvrez le calque que vous venez de créer et validez son contenu. Vérifiez le nombre et récupérez les valeurs d'attribut à l'aide du code suivant :
```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Nom_1"
}
```
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment ajouter une couche à un ensemble de données File GDB à l'aide d'Aspose.GIS pour .NET. Grâce à ces nouvelles compétences, vous pouvez manipuler efficacement les données géographiques dans vos projets SIG.
## Questions fréquemment posées
### Q : Puis-je utiliser Aspose.GIS pour .NET avec d’autres bibliothèques SIG ?
Aspose.GIS pour .NET est conçu pour fonctionner de manière indépendante, mais il peut être intégré à d'autres bibliothèques pour des fonctionnalités améliorées.
### Q : Une licence temporaire est-elle disponible à des fins de test ?
 Oui, vous pouvez obtenir une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/) pour les tests et l'évaluation.
### Q : Quels systèmes de référence spatiale Aspose.GIS pour .NET prend-il en charge ?
Aspose.GIS pour .NET prend en charge un large éventail de systèmes de référence spatiale, offrant une flexibilité dans la gestion des données géographiques.
### Q : Puis-je contribuer à la communauté Aspose.GIS ?
 Absolument! Rejoignez les discussions et partagez vos expériences sur le[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### Q : Où puis-je trouver une documentation détaillée pour Aspose.GIS pour .NET ?
 Explorez la documentation complète[ici](https://reference.aspose.com/gis/net/) pour des informations détaillées sur Aspose.GIS pour .NET.