---
date: 2026-01-10
description: Apprenez à créer des ensembles de données .NET de géodatabase fichier
  avec Aspose.GIS pour .NET. Guide étape par étape pour une gestion sans effort des
  données SIG.
linktitle: Create New File GDB Dataset
second_title: Aspose.GIS .NET API
title: Créer un jeu de données .NET de géodatabase de fichiers avec Aspose.GIS
url: /fr/net/layer-management/create-new-file-gdb-dataset/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un jeu de données File Geodatabase .NET avec Aspose.GIS

## Introduction
Dans ce tutoriel, vous allez **créer des jeux de données File Geodatabase .NET** à partir de zéro en utilisant Aspose.GIS pour .NET. Que vous construisiez un outil GIS de bureau, un service web qui stocke des données spatiales, ou que vous ayez simplement besoin d’une méthode fiable pour générer des File Geodatabases de façon programmatique, ce guide vous accompagne à chaque étape avec des explications claires et un contexte réel.

## Réponses rapides
- **Que couvre ce tutoriel ?** Création d’une nouvelle File Geodatabase, ajout de deux couches, et vérification du jeu de données avec Aspose.GIS pour .NET.  
- **Combien de temps cela prend‑il ?** Environ 10‑15 minutes pour un développeur familier avec C#.  
- **Prérequis ?** Environnement de développement .NET, bibliothèque Aspose.GIS pour .NET, et un chemin de dossier accessible en écriture.  
- **Puis‑je l’utiliser avec .NET Core / .NET 6+ ?** Oui – l’API est entièrement compatible avec les runtimes .NET modernes.  
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou permanente Aspose.GIS est requise pour une utilisation en production.

## Qu’est‑ce qu’une File Geodatabase ?
Une File Geodatabase (File GDB) est un magasin de données basé sur un dossier qui contient des classes d’entités GIS, des jeux de données raster et les métadonnées associées. Elle offre des performances de lecture/écriture rapides, prend en charge de grands jeux de données et est largement utilisée dans l’écosystème ArcGIS d’Esri. Avec Aspose.GIS, vous pouvez créer et manipuler ces bases directement depuis du code .NET sans aucun logiciel GIS externe.

## Pourquoi créer une File Geodatabase .NET avec Aspose.GIS ?
- **Aucune dépendance externe** – la bibliothèque gère tous les détails du format de fichier.  
- **Multiplateforme** – fonctionne sur les runtimes .NET Windows, Linux et macOS.  
- **Support riche de la géométrie** – points, lignes, polygones, etc.  
- **Contrôle total** – vous décidez du schéma, des attributs et du système de référence spatiale.

## Prérequis
Avant de commencer, assurez‑vous de disposer de :

- Aspose.GIS pour .NET installé. Vous pouvez le télécharger depuis la [page de téléchargement Aspose.GIS pour .NET](https://releases.aspose.com/gis/net/).  
- Un environnement de développement tel que Visual Studio 2022 (ou tout IDE supportant .NET).  
- Un dossier accessible en écriture sur votre machine où la nouvelle GDB sera créée – remplacez `"Your Document Directory"` dans le code par ce chemin.  
- Une connaissance de base du C# et de la structure d’un projet .NET.

## Importer les espaces de noms
Tout d’abord, importez les espaces de noms qui vous donnent accès aux classes Aspose.GIS :

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

## Guide étape par étape

### Étape 1 : Créer un nouveau jeu de données File GDB
Le fragment suivant crée une File Geodatabase vide. C’est le cœur du **create file geodatabase .net**.

```csharp
string dataDir = "Your Document Directory";
using (var dataset = Dataset.Create(dataDir, Drivers.FileGdb))
{
    Console.WriteLine(dataset.LayersCount); // Output: 0
    // Continue with subsequent steps...
}
```

**Explication :** `Dataset.Create` initialise la GDB au chemin spécifié en utilisant le pilote `FileGdb`. À ce stade, le jeu de données ne contient aucune couche, donc le nombre de couches est zéro.

### Étape 2 : Créer et remplir `layer_1`
Nous ajoutons maintenant une première couche qui stocke des attributs entiers et des géométries de points.

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

**Explication :**  
- `CreateLayer` crée une nouvelle classe d’entités nommée **layer_1**.  
- Un attribut entier appelé **value** est défini.  
- La boucle ajoute dix entités, chacune avec un entier unique et un point aux coordonnées *(i, i)*.

### Étape 3 : Créer et remplir `layer_2`
Ensuite, nous ajoutons une seconde couche qui montre la gestion des géométries de ligne.

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

**Explication :** Ceci crée **layer_2** et insère une unique entité dont la géométrie est un `LineString` reliant deux points.

### Étape 4 : Vérifier le nombre de couches mis à jour
Enfin, confirmez que les deux couches ont bien été ajoutées.

```csharp
Console.WriteLine(dataset.LayersCount); // Output: 2
```

**Explication :** Le jeu de données indique maintenant deux couches, confirmant que le processus **create file geodatabase .net** s’est déroulé comme prévu.

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **`UnauthorizedAccessException`** lors de la création du jeu de données | Le chemin du dossier est en lecture‑seule ou vous n’avez pas les permissions nécessaires. | Choisissez un répertoire accessible en écriture ou exécutez Visual Studio en tant qu’administrateur. |
| **`ArgumentException` pour le pilote** | Le nom du pilote est mal orthographié ou la version de la bibliothèque ne le supporte pas. | Utilisez exactement `Drivers.FileGdb` comme indiqué ; assurez‑vous d’avoir la dernière version du package Aspose.GIS. |
| **Les entités n’apparaissent pas dans ArcGIS** | Référence spatiale manquante ou géométrie incompatible. | Définissez une référence spatiale sur la couche si nécessaire, et assurez‑vous que les géométries sont valides. |

## Questions fréquentes
### Q : Puis‑je utiliser Aspose.GIS pour .NET avec d’autres bibliothèques GIS ?
Aspose.GIS pour .NET est une boîte à outils autonome ; toutefois, vous pouvez l’intégrer à d’autres bibliothèques .NET pour enrichir les fonctionnalités.

### Q : Existe‑t‑il un forum communautaire pour le support d’Aspose.GIS ?
Oui, vous pouvez trouver de l’aide et des discussions sur le [Forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### Q : Comment obtenir une licence temporaire pour Aspose.GIS ?
Visitez la page [Licence temporaire](https://purchase.aspose.com/temporary-license/) pour obtenir des informations sur l’obtention d’une licence temporaire.

### Q : Y a‑t‑il des exemples supplémentaires et de la documentation disponible ?
Explorez la [documentation Aspose.GIS](https://reference.aspose.com/gis/net/) pour plus d’exemples et d’informations détaillées.

### Q : Où puis‑je acheter Aspose.GIS pour .NET ?
Vous pouvez acheter Aspose.GIS pour .NET sur la [page d’achat](https://purchase.aspose.com/buy).

## Conclusion
Vous avez maintenant créé avec succès des **jeux de données file geodatabase .NET**, ajouté deux couches distinctes et vérifié le résultat à l’aide d’Aspose.GIS. Cette base vous permet de développer des applications GIS plus riches — ajoutez d’autres couches, définissez des schémas complexes, ou intégrez‑les à des services web. Explorez davantage l’API Aspose.GIS pour travailler avec des données raster, des requêtes spatiales et des opérations géométriques avancées.

---

**Dernière mise à jour :** 2026-01-10  
**Testé avec :** Aspose.GIS pour .NET 24.11 (ou version la plus récente)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}