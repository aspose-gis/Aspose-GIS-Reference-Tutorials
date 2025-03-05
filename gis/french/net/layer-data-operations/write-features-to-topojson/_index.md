---
title: Écrire des fonctionnalités dans TopoJSON
linktitle: Écrire des fonctionnalités dans TopoJSON
second_title: API Aspose.GIS .NET
description: Maîtrisez l'écriture de fonctionnalités TopoJSON avec Aspose.GIS pour .NET. Suivez notre tutoriel étape par étape. Élevez vos applications SIG.
type: docs
weight: 24
url: /fr/net/layer-data-operations/write-features-to-topojson/
---
## Introduction
Dans le domaine du développement de systèmes d'information géographique (SIG), Aspose.GIS pour .NET se distingue comme une boîte à outils puissante, offrant une multitude de fonctionnalités pour manipuler les données spatiales. Parmi ses nombreuses fonctionnalités, ce didacticiel se concentre sur une tâche spécifique : l'écriture de fonctionnalités au format TopoJSON à l'aide d'Aspose.GIS pour .NET. Si vous souhaitez améliorer vos applications SIG avec la prise en charge de TopoJSON, suivez-nous pour découvrir un guide étape par étape.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
-  Aspose.GIS pour .NET : assurez-vous que la bibliothèque Aspose.GIS est installée. Vous pouvez trouver la documentation et télécharger la bibliothèque[ici](https://reference.aspose.com/gis/net/).
- Environnement .NET : assurez-vous d'avoir configuré un environnement de développement .NET.
-  Répertoire de documents : choisissez un répertoire pour vos documents. Ceci sera appelé`Your Document Directory` dans les exemples de code.
## Importer des espaces de noms
Dans votre application .NET, incluez les espaces de noms nécessaires pour travailler avec Aspose.GIS et d'autres fonctionnalités requises.
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
```
Maintenant, décomposons l'exemple de code en plusieurs étapes pour une compréhension claire.
## 1. Définir le répertoire des documents
```csharp
string dataDir = "Your Document Directory";
```
 Remplacer`"Your Document Directory"` avec le chemin réel vers votre répertoire de documents.
## 2. Spécifiez le chemin de sortie
```csharp
var outputPath = dataDir + "sample_out.topojson";
```
Définissez le chemin du fichier TopoJSON de sortie.
## 3. Créez un VectorLayer avec le pilote TopoJSON
```csharp
using (VectorLayer layer = VectorLayer.Create(outputPath, Drivers.TopoJson))
```
Initialisez un VectorLayer à l'aide du pilote TopoJSON.
## 4. Ajouter des attributs au calque
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("measurement", AttributeDataType.Double));
layer.Attributes.Add(new FeatureAttribute("id", AttributeDataType.Integer));
```
Définissez les attributs des entités à ajouter à la couche.
## 5. Ajouter des fonctionnalités à la couche
```csharp
var feature0 = layer.ConstructFeature();
feature0.SetValue("name", "name_0");
feature0.SetValue("measurement", 1.03);
feature0.SetValue("id", 0);
feature0.Geometry = new Point(1.3, 2.3);
layer.Add(feature0);
var feature1 = layer.ConstructFeature();
feature1.SetValue("name", "name_1");
feature1.SetValue("measurement", 10.03);
feature1.SetValue("id", 1);
feature1.Geometry = new Point(241.32, 23.2);
layer.Add(feature1);
```
Construisez des entités avec des attributs et des géométries spécifiés et ajoutez-les à la couche.
## Conclusion
Toutes nos félicitations! Vous avez réussi à écrire des fonctionnalités sur TopoJSON à l'aide d'Aspose.GIS pour .NET. Ce didacticiel fournit une compréhension fondamentale du processus, vous permettant d'intégrer cette fonctionnalité dans vos applications SIG de manière transparente.
## Questions fréquemment posées
### Q : Puis-je utiliser Aspose.GIS pour .NET avec d’autres bibliothèques SIG ?
R : Aspose.GIS pour .NET est conçu pour fonctionner de manière indépendante, mais l'intégration avec d'autres bibliothèques est possible pour des fonctionnalités améliorées.
### Q : Existe-t-il des options de licence pour Aspose.GIS ?
 R : Oui, vous pouvez explorer les options de licence et effectuer des achats.[ici](https://purchase.aspose.com/buy).
### Q : Existe-t-il un essai gratuit disponible pour Aspose.GIS pour .NET ?
 R : Absolument ! Vous pouvez accéder à l'essai gratuit[ici](https://releases.aspose.com/).
### Q : Où puis-je demander de l'aide ou me connecter à la communauté Aspose.GIS ?
 R : Dirigez-vous vers le[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le soutien et les discussions de la communauté.
### Q : Comment puis-je obtenir une licence temporaire pour Aspose.GIS ?
 R : Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).