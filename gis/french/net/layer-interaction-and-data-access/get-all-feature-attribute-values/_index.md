---
date: 2026-01-05
description: Apprenez à lire un shapefile en C# avec Aspose.GIS pour .NET, à récupérer
  toutes les valeurs d’attributs des entités et à exporter les attributs efficacement.
linktitle: Get All Feature Attribute Values
second_title: Aspose.GIS .NET API
title: Lire un Shapefile C# – Obtenir toutes les valeurs d’attributs des entités
url: /fr/net/layer-interaction-and-data-access/get-all-feature-attribute-values/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Récupérer toutes les valeurs d’attributs des entités

## Introduction
Bienvenue dans le monde du développement géospatial avec Aspose.GIS pour .NET ! Dans ce tutoriel, vous apprendrez **comment lire un shapefile en C#** et récupérer chaque valeur d’attribut de ses entités. Que vous construisiez une application cartographique ou que vous traitiez des données spatiales en lot, maîtriser l’extraction d’attributs est essentiel. Plongeons‑y et voyons le code en action.

## Réponses rapides
- **Que fait ce code ?** Il ouvre un Shapefile et lit toutes, plusieurs ou les valeurs d’attributs « dumpées » de chaque entité.  
- **Quelle bibliothèque est requise ?** Aspose.GIS pour .NET (compatible avec .NET Framework et .NET Core).  
- **Ai‑je besoin d’une licence ?** Une licence temporaire suffit pour les tests ; une licence complète est requise en production.  
- **Puis‑je lire d’autres formats ?** Oui – la même API prend en charge GeoJSON, KML et bien d’autres.  
- **Comment dumper les attributs ?** Utilisez `feature.GetValuesDump()` pour obtenir un tableau d’objets flexible.

## Qu’est‑ce que « read shapefile C# » ?
Lire un Shapefile en C# signifie ouvrir le fichier *.shp* avec une bibliothèque GIS, parcourir ses entités vectorielles et accéder aux données d’attribut stockées dans le fichier *.dbf* associé. Aspose.GIS abstrait la gestion bas‑niveau des fichiers, vous permettant de vous concentrer sur les valeurs d’attribut dont vous avez besoin.

## Pourquoi utiliser Aspose.GIS pour lire les attributs ?
- **API simple** – méthodes intuitives comme `GetValues` et `GetValuesDump`.  
- **Multiplateforme** – fonctionne sous Windows, Linux et macOS avec .NET Core.  
- **Large prise en charge des formats** – gérez Shapefile, GeoJSON, GML, et plus sans plugins supplémentaires.  
- **Performance optimisée** – itération rapide sur de grands ensembles de données.

## Prérequis
Avant de commencer ce passionnant parcours, assurez‑vous d’avoir les prérequis suivants :
- Aspose.GIS pour .NET : téléchargez et installez la bibliothèque depuis la [page de téléchargement d’Aspose.GIS pour .NET](https://releases.aspose.com/gis/net/).
- Environnement de développement : configurez un environnement .NET, par exemple Visual Studio.
- Shapefile : disposez d’un Shapefile d’exemple (par ex. « InputShapeFile.shp ») dans votre répertoire de documents.

## Importer les espaces de noms
Dans votre code C#, commencez par importer les espaces de noms nécessaires pour exploiter les fonctionnalités d’Aspose.GIS :
```csharp
using System;
using Aspose.Gis;
```

## Étape 1 : définir le répertoire du document
```csharp
string dataDir = "Your Document Directory";
```
Remplacez « Your Document Directory » par le chemin réel où se trouve votre Shapefile.

## Étape 2 : ouvrir le VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for further steps goes here
}
```
Cette étape consiste à ouvrir le Shapefile avec Aspose.GIS, en spécifiant le chemin du fichier et le format (dans ce cas, Shapefile).

## Étape 3 : récupérer toutes les valeurs d’attributs des entités
```csharp
foreach (var feature in layer)
{
    // reads all the attributes into an array.
    object[] all = new object[3];
    feature.GetValues(all);
    Console.WriteLine("all    : {0}, {1}, {2}", all);
    // Your code for handling all attribute values goes here
    Console.WriteLine();
}
```
L’extrait montre **comment lire les attributs** de chaque entité en les chargeant dans un tableau à taille fixe.

## Étape 4 : récupérer plusieurs valeurs d’attributs d’une entité
```csharp
foreach (var feature in layer)
{
    // reads several attributes into an array.
    object[] several = new object[2];
    feature.GetValues(several);
    Console.WriteLine("several: {0}, {1}", several);
    // Your code for handling several attribute values goes here
    Console.WriteLine();
}
```
Ici nous démontrons **comment lire des valeurs d’attributs spécifiques** lorsque vous ne avez besoin que d’un sous‑ensemble de champs.

## Étape 5 : récupérer les valeurs d’attributs sous forme de dump d’objets
```csharp
foreach (var feature in layer)
{
    // reads attributes as a dump of objects.
    var dump = feature.GetValuesDump();
    Console.WriteLine("dump   : {0}, {1}, {2}", dump);
    // Your code for handling dumped attribute values goes here
    Console.WriteLine();
}
```
Cette dernière étape illustre **comment dumper les attributs** à l’aide de `GetValuesDump()`, qui renvoie une collection flexible que vous pouvez inspecter ou sérialiser.

## Problèmes courants et solutions
- **Mauvaise taille du tableau** – Assurez‑vous que le tableau passé à `GetValues` correspond au nombre d’attributs attendus ; sinon vous obtiendrez des entrées `null`.  
- **Fichier introuvable** – Vérifiez que `dataDir` pointe vers le bon dossier et que le nom du Shapefile est exactement correct.  
- **Exception de licence** – Si vous voyez une erreur de licence, appliquez une licence temporaire ou complète avant d’appeler toute méthode de l’API.

## Questions fréquentes
### Aspose.GIS est‑il compatible avec .NET Core ?
Oui, Aspose.GIS est entièrement compatible avec .NET Core, ce qui vous permet de créer des applications multiplateformes.

### Puis‑je travailler avec différents formats de fichiers GIS grâce à Aspose.GIS ?
Absolument ! Aspose.GIS prend en charge divers formats, dont Shapefile, GeoJSON et bien d’autres.

### Existe‑t‑il un forum communautaire pour le support d’Aspose.GIS ?
Oui, vous pouvez obtenir de l’aide et échanger avec la communauté Aspose.GIS sur le [forum de support](https://forum.aspose.com/c/gis/33).

### Comment obtenir une licence temporaire pour Aspose.GIS ?
Vous pouvez acquérir une licence temporaire à des fins de test [ici](https://purchase.aspose.com/temporary-license/).

### Où trouver la documentation détaillée d’Aspose.GIS ?
La documentation complète est disponible [ici](https://reference.aspose.com/gis/net/).

### Comment récupérer uniquement l’attribut « Name » de chaque entité ?
Utilisez `GetValues` avec un tableau de taille un et passez l’indice du champ « Name », ou appelez directement `feature["Name"]`.

### Quelle est la différence entre `GetValues` et `GetValuesDump` ?
`GetValues` remplit un tableau pré‑alloué avec les valeurs brutes, tandis que `GetValuesDump` renvoie un tableau d’objets qui peut être énuméré sans connaître le schéma au préalable.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-01-05  
**Testé avec :** Aspose.GIS pour .NET (dernière version)  
**Auteur :** Aspose  

---