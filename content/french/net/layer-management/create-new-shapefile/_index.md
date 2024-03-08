---
title: Créer un nouveau fichier de formes
linktitle: Créer un nouveau fichier de formes
second_title: API Aspose.GIS .NET
description: Découvrez comment créer un nouveau fichier de formes à l'aide d'Aspose.GIS pour .NET. Suivez notre guide étape par étape et débloquez la puissance de la manipulation des données spatiales.
type: docs
weight: 12
url: /fr/net/layer-management/create-new-shapefile/
---
## Introduction
Si vous vous lancez dans le développement de systèmes d'information géographique (SIG) avec .NET, Aspose.GIS est votre solution incontournable. Cette puissante bibliothèque permet aux développeurs de travailler de manière transparente avec des données spatiales. Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'un nouveau fichier de formes à l'aide d'Aspose.GIS pour .NET.
## Conditions préalables
Avant de passer au didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Compréhension de base du langage de programmation C#.
- Visual Studio installé sur votre ordinateur.
-  Aspose.GIS pour la bibliothèque .NET. Vous pouvez le télécharger[ici](https://releases.aspose.com/gis/net/).
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires pour exploiter les fonctionnalités d'Aspose.GIS :
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Étape 1 : Configurez votre projet
Commencez par créer un nouveau projet C# dans Visual Studio et incluez la bibliothèque Aspose.GIS.
## Étape 2 : définir le répertoire des documents
```csharp
string dataDir = "Your Document Directory";
```
Remplacez « Votre répertoire de documents » par le chemin réel où vous souhaitez enregistrer votre nouveau fichier de formes.
## Étape 3 : Créer un VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    //ajouter des attributs avant d'ajouter des fonctionnalités
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Ce segment de code configure la couche vectorielle et définit les attributs de vos entités.
## Étape 4 : Ajouter des fonctionnalités
### Cas 1 : définit les valeurs individuellement
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
### Cas 2 : définit de nouvelles valeurs pour tous les attributs
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
## Conclusion
 Toutes nos félicitations! Vous avez créé avec succès un nouveau fichier de formes à l'aide d'Aspose.GIS pour .NET. Ce didacticiel a couvert les bases de la configuration de votre projet, de la définition des attributs et de l'ajout de fonctionnalités. Au fur et à mesure de votre exploration, reportez-vous au[Documentation](https://reference.aspose.com/gis/net/) pour des fonctionnalités et fonctionnalités avancées.
## Questions fréquemment posées
### Q : Puis-je utiliser Aspose.GIS avec d’autres langages de programmation ?
Aspose.GIS prend principalement en charge .NET, mais des versions sont également disponibles pour Java.
### Q : Existe-t-il un essai gratuit ?
 Oui, vous pouvez accéder à l'essai gratuit[ici](https://releases.aspose.com/).
### Q : Où puis-je trouver de l'assistance pour Aspose.GIS ?
 Visiter le[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le soutien et les discussions de la communauté.
### Q : Comment puis-je obtenir une licence temporaire ?
 Obtenez votre permis temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Q : Où puis-je acheter Aspose.GIS pour .NET ?
 Vous pouvez acheter la bibliothèque[ici](https://purchase.aspose.com/buy).