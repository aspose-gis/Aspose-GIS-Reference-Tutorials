---
date: 2026-01-13
description: Apprenez à convertir un shapefile en GeoJSON à l'aide d'Aspose.GIS pour
  .NET. Le guide couvre également la copie des attributs entre les couches et la génération
  d'un fichier GeoJSON en C#.
linktitle: Extract Features to GeoJSON
second_title: Aspose.GIS .NET API
title: Comment convertir un Shapefile en GeoJSON avec Aspose.GIS pour .NET
url: /fr/net/layer-management/extract-features-to-geojson/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir un Shapefile en GeoJSON avec Aspose.GIS pour .NET

## Introduction
Dans ce tutoriel complet, étape par étape, vous apprendrez **comment convertir un shapefile en geojson** en utilisant la puissante bibliothèque Aspose.GIS pour .NET. Que vous construisiez un service web de cartographie, prépariez des données pour une application GIS mobile, ou ayez simplement besoin d’échanger des données entre formats, ce guide vous montre exactement quoi faire, pourquoi chaque étape est importante et comment éviter les pièges courants.

## Réponses rapides
- **Quel est le sujet de ce tutoriel ?** Conversion d’un Shapefile en fichier GeoJSON, copie des attributs entre les couches, et génération du résultat avec C#.
- **Quelle bibliothèque est requise ?** Aspose.GIS pour .NET.
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou complète est requise pour la production ; un essai gratuit suffit pour l’évaluation.
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour une conversion de base.
- **Puis‑je l’exécuter sur .NET Core/.NET 6 ?** Oui – le code fonctionne sur toutes les versions .NET prises en charge.

## Prérequis
Avant de commencer, assurez‑vous d’avoir les éléments suivants :

- Aspose.GIS pour .NET : assurez‑vous que la bibliothèque est installée. Sinon, vous pouvez la télécharger depuis la [page Aspose.GIS pour .NET](https://releases.aspose.com/gis/net/).
- Données Shapefile : disposez d’un Shapefile prêt à être utilisé. Si vous avez besoin d’exemples de données, vous les trouverez dans la [documentation Aspose.GIS](https://reference.aspose.com/gis/net/).
- Environnement .NET : configurez un environnement .NET pour exécuter le code fourni.
- Répertoire de documents : définissez le chemin vers votre répertoire de documents dans l’extrait de code.

Maintenant que tout est en place, commençons à convertir le shapefile en geojson !

## Qu’est‑ce que « convertir shapefile en geojson » ?
Convertir un Shapefile en GeoJSON signifie lire les entités vectorielles du format classique ESRI Shapefile et les écrire sous forme d’un document GeoJSON moderne et adapté au web. Le GeoJSON est largement utilisé dans les bibliothèques de cartographie JavaScript (Leaflet, Mapbox GL) et les API, ce qui fait de cette conversion une tâche fréquente en développement GIS.

## Pourquoi utiliser Aspose.GIS pour cette conversion ?
Aspose.GIS masque les détails de bas niveau des formats de fichiers, vous permet de copier les tables d’attributs sans effort, et fournit une API propre orientée objet qui fonctionne sur .NET Framework, .NET Core et .NET 5/6. Cela vous permet de vous concentrer sur la logique métier plutôt que sur l’analyse de fichiers binaires.

## Importer les espaces de noms
Tout d’abord, incluez les espaces de noms nécessaires dans votre code :

```csharp
using Aspose.Gis;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Ces espaces de noms sont essentiels pour travailler avec les fonctionnalités d’Aspose.GIS.

## Comment convertir un Shapefile en GeoJSON
Voici le flux complet découpé en étapes claires. Chaque étape comprend une courte explication suivie du bloc de code exact à copier dans votre projet.

### Étape 1 : Ouvrir le Shapefile d’entrée
```csharp
using (VectorLayer inputLayer = VectorLayer.Open(dataDir + "InputShapeFile.shp", Drivers.Shapefile))
{
    // Your code for processing the input shapefile goes here
}
```
Ouvrez le Shapefile d’entrée à l’aide de la méthode `VectorLayer.Open`. Cela vous fournit une collection énumérable d’objets `Feature`.

### Étape 2 : Créer le GeoJSON de sortie
```csharp
using (VectorLayer outputLayer = VectorLayer.Create(dataDir + "ExtractFeaturesFromShapeFileToGeoJSON_out.json", Drivers.GeoJson))
{
    // Your code for creating the output GeoJSON goes here
}
```
Créez le fichier de sortie avec la méthode `VectorLayer.Create`, en spécifiant le pilote `Drivers.GeoJson`.

### Étape 3 : Copier les attributs entre les couches
```csharp
outputLayer.CopyAttributes(inputLayer);
```
Cette ligne unique copie le schéma d’attributs (noms de champs, types) du Shapefile source vers la nouvelle couche GeoJSON — exactement ce que décrit le mot‑clé secondaire *copy attributes between layers*.

### Étape 4 : Traiter les entités
```csharp
foreach (Feature inputFeature in inputLayer)
{
    // Your code for processing each input feature goes here
}
```
Itérez sur chaque entité du Shapefile afin de pouvoir appliquer une logique personnalisée avant de l’écrire.

### Étape 5 : Filtrer les entités par date
```csharp
DateTime? date = inputFeature.GetValue<DateTime?>("dob");
if (date == null || date < new DateTime(1982, 1, 1))
{
    continue;
}
```
Dans cet exemple, nous ignorons les enregistrements dont le champ `dob` (date de naissance) est manquant ou antérieur au 1 janv. 1982. N’hésitez pas à ajuster le filtre selon vos propres exigences de données.

### Étape 6 : Construire une nouvelle entité (C# Générer un fichier GeoJSON)
```csharp
Feature outputFeature = outputLayer.ConstructFeature();
outputFeature.Geometry = inputFeature.Geometry;
outputFeature.CopyValues(inputFeature);
outputLayer.Add(outputFeature);
```
Ici nous créons une nouvelle `Feature` pour la couche GeoJSON, copions la géométrie et les valeurs d’attributs, puis l’ajoutons à la sortie. C’est le cœur de *c# generate geojson file*.

Félicitations ! Vous avez réussi à **convertir un shapefile en geojson** et avez appris comment copier les attributs entre les couches en cours de route.

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| Le fichier de sortie est vide | `CopyAttributes` appelé après la fermeture de la couche de sortie | Assurez‑vous que le bloc `using` pour `outputLayer` reste ouvert jusqu’après l’ajout de toutes les entités. |
| Le filtre de date supprime tous les enregistrements | Nom de champ incorrect ou format de date inattendu | Vérifiez le nom de l’attribut (`dob`) et utilisez `GetValue<string>` si les dates sont stockées sous forme de chaînes. |
| Exception de licence | Exécution sans licence Aspose.GIS valide en production | Appliquez une licence temporaire ou complète comme décrit dans la documentation Aspose. |

## Questions fréquemment posées
**Q : Où puis‑je trouver plus de documentation ?**  
R : Consultez la [documentation Aspose.GIS](https://reference.aspose.com/gis/net/) pour des informations détaillées.

**Q : Comment obtenir une licence temporaire ?**  
R : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je obtenir du support ?**  
R : Rejoignez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le support communautaire et les discussions.

**Q : Une version d’essai gratuite est‑elle disponible ?**  
R : Oui, vous pouvez trouver l’essai gratuit [ici](https://releases.aspose.com/).

**Q : Où puis‑je acheter Aspose.GIS pour .NET ?**  
R : Vous pouvez acheter le produit [ici](https://purchase.aspose.com/buy).

## Conclusion
Dans ce tutoriel, nous avons exploré le processus complet de **conversion d’un shapefile en geojson** avec Aspose.GIS pour .NET, démontré comment copier les attributs entre les couches, et présenté une méthode propre pour *c# generate geojson file*. Expérimentez avec différents filtres, des ensembles de données plus volumineux ou des transformations géométriques supplémentaires afin de tirer pleinement parti des capacités de la bibliothèque.

---  
**Dernière mise à jour :** 2026-01-13  
**Testé avec :** Aspose.GIS for .NET (latest stable release)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}