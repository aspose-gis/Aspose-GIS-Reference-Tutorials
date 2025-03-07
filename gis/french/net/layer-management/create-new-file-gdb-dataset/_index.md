---
title: Créer un nouveau jeu de données GDB
linktitle: Créer un nouveau jeu de données GDB
second_title: API Aspose.GIS .NET
description: Explorez Aspose.GIS pour .NET pour créer et gérer sans effort des ensembles de données SIG. Téléchargez-le dès maintenant pour un développement géospatial fluide. #Aspose #SIG
weight: 10
url: /fr/net/layer-management/create-new-file-gdb-dataset/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un nouveau jeu de données GDB

## Introduction
Dans le domaine du développement géospatial, Aspose.GIS pour .NET se distingue comme une puissante boîte à outils pour gérer et manipuler les données du système d'information géographique (SIG). Que vous soyez un développeur chevronné ou que vous commenciez tout juste votre parcours dans le SIG, ce didacticiel vous guidera tout au long du processus de création d'un nouvel ensemble de données de géodatabase fichier (GDB) à l'aide d'Aspose.GIS pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
-  Aspose.GIS pour .NET : assurez-vous que la bibliothèque Aspose.GIS pour .NET est installée. Vous pouvez le télécharger depuis le[Page de téléchargement d'Aspose.GIS pour .NET](https://releases.aspose.com/gis/net/).
- Environnement de développement : configurez votre environnement de développement avec un IDE compatible, tel que Visual Studio, et possédez une compréhension de base de la programmation .NET.
- Répertoire de documents : remplacez « Votre répertoire de documents » dans l'extrait de code par le chemin approprié où vous souhaitez stocker votre ensemble de données GDB.
- Familiarité avec C# : ce didacticiel suppose que vous êtes familier avec le langage de programmation C#.
## Importer des espaces de noms
Dans les étapes initiales, importez les espaces de noms nécessaires pour exploiter la fonctionnalité Aspose.GIS dans votre application .NET :
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```
## Étape 1 : Créer un nouvel ensemble de données fichier GDB
```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Sortie : 0
    // Continuez avec les étapes suivantes...
}
```
 Explication : Dans cette étape, nous créons un nouvel ensemble de données GDB à l'aide du`Dataset.Create` méthode. Nous spécifions le chemin et le pilote (FileGdb) pour créer une géodatabase fichier. La sortie de la console affiche le nombre de couches initial, qui est nul à ce stade.
## Étape 2 : créer et remplir le calque_1
```csharp
using (var layer = dataset.CreateLayer("layer_1"))
{
    layer.Attributes.Add(new FeatureAttribute("value", AttributeDataType.Integer));
    for (int i = 0; i < 10; ++i)
    {
        var feature = layer.ConstructFeature();
        feature.SetValue("value", i);
        feature.Geometry = new Point(i, i);
        layer.Add(feature);
    }
}
```
Explication : Cette étape implique la création d'une couche nommée "layer_1" dans l'ensemble de données. Il définit un attribut nommé « valeur » de type entier et remplit la couche avec dix entités, chacune ayant une géométrie ponctuelle.
## Étape 3 : créer et remplir le calque_2
```csharp
using (var layer = dataset.CreateLayer("layer_2"))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new LineString(new[]
    {
        new Point(1, 2),
        new Point(3, 4),
    });
    layer.Add(feature);
}
```
Explication : Ici, nous créons une deuxième couche nommée "layer_2" et ajoutons une seule entité avec une géométrie de chaîne de lignes.
## Étape 4 : Vérifiez le nombre de couches mis à jour
```csharp
Console.WriteLine(dataset.LayersCount); // Sortie : 2
```
Explication : Enfin, nous vérifions le nombre de couches mises à jour après avoir ajouté les deux couches. Dans ce cas, la sortie devrait être 2.
## Conclusion
Toutes nos félicitations! Vous avez créé avec succès un nouveau jeu de données File GDB et l'avez rempli avec des couches à l'aide d'Aspose.GIS pour .NET. Ce didacticiel fournit une compréhension fondamentale de l'utilisation de données géospatiales dans un environnement .NET.
## Questions fréquemment posées
### Q : Puis-je utiliser Aspose.GIS pour .NET avec d’autres bibliothèques SIG ?
Aspose.GIS pour .NET est une boîte à outils autonome ; cependant, vous pouvez l'intégrer à d'autres bibliothèques .NET pour améliorer les fonctionnalités.
### Q : Existe-t-il un forum communautaire pour le support d'Aspose.GIS ?
 Oui, vous pouvez trouver du soutien et des discussions sur le[Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).
### Q : Comment puis-je obtenir une licence temporaire pour Aspose.GIS ?
 Visiter le[Permis temporaire](https://purchase.aspose.com/temporary-license/) page pour obtenir des informations sur l'obtention d'un permis temporaire.
### Q : Existe-t-il des exemples et de la documentation supplémentaires disponibles ?
 Explore le[Documentation Aspose.GIS](https://reference.aspose.com/gis/net/) pour plus d’exemples et d’informations détaillées.
### Q : Où puis-je acheter Aspose.GIS pour .NET ?
 Vous pouvez acheter Aspose.GIS pour .NET sur le[page d'achat](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
