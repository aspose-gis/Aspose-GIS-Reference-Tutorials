---
date: 2026-04-24
description: Apprenez à lire les données de géodatabase en utilisant Aspose.GIS pour
  .NET, une bibliothèque complète pour les données géospatiales dans les applications
  .NET.
keywords:
- how to read geodatabase
- Aspose.GIS .NET
- read File Geodatabase
- GIS data extraction
linktitle: Lire les entités depuis une géodatabase de fichiers
second_title: Aspose.GIS .NET API
title: Comment lire les entités d’une géodatabase à partir d’une géodatabase de fichiers
  dans Aspose.GIS
url: /fr/net/layer-data-operations/read-features-from-file-geodatabase/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire les entités d’une géodatabase de fichiers dans Aspose.GIS

## Introduction
Si vous cherchez un moyen fiable **de lire les données d’une géodatabase** dans un environnement .NET, Aspose.GIS pour .NET offre une API propre et haute performance qui vous permet d’extraire les informations d’entités d’une File Geodatabase en quelques lignes de code C#. Dans ce tutoriel, nous parcourrons l’ensemble du processus — de la configuration du projet à l’itération sur les couches et l’extraction de la géométrie — pour que vous puissiez commencer à créer des applications GIS dès maintenant.

## Réponses rapides
- **Quelle bibliothèque faut‑il ?** Aspose.GIS pour .NET (essai gratuit disponible).  
- **Quel format de fichier est pris en charge ?** File Geodatabase (.gdb) via le driver `FileGdb`.  
- **Ai‑je besoin d’une licence pour le développement ?** Non, l’essai fonctionne pour le développement et les tests.  
- **Puis‑je exécuter cela sur .NET 6+ ?** Oui, Aspose.GIS prend en charge .NET 5, .NET 6 et les versions ultérieures.  
- **Combien de lignes de code ?** Environ 30 lignes pour lire et afficher toutes les géométries d’entités.

## Qu’est‑ce qu’une géodatabase de fichiers ?
Une File Geodatabase (souvent abrégée **GDB**) est le magasin de données basé sur des dossiers d’Esri qui contient des données vectorielles et raster sous forme d’un ensemble de fichiers. Elle est largement utilisée dans les SIG de bureau, et Aspose.GIS abstrait la gestion bas‑niveau des fichiers afin que vous puissiez vous concentrer sur les données elles‑mêmes.

## Pourquoi utiliser Aspose.GIS pour lire une géodatabase ?
- **Aucune dépendance externe** – pur .NET, aucune DLL native.  
- **Multiplateforme** – fonctionne sous Windows, Linux et macOS.  
- **Ensemble complet de fonctionnalités** – lire, écrire, modifier et analyser les données sans outils supplémentaires.  
- **Optimisé pour les performances** – itération rapide sur de grands ensembles de données.

## Prérequis
Avant de plonger dans le code, assurez‑vous de disposer de :

1. **Environnement de développement .NET** – Visual Studio 2022 (ou tout IDE supportant .NET 6+).  
2. **Aspose.GIS pour .NET** – téléchargez le dernier package depuis la [page de téléchargement](https://releases.aspose.com/gis/net/).  
3. **Connaissances de base en C#** – vous devez être à l’aise avec les instructions `using` et les boucles.

## Importer les espaces de noms
Tout d’abord, importez les espaces de noms qui exposent les classes GIS dont nous aurons besoin.

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
```

## Guide étape par étape

### Étape 1 : Ouvrir la géodatabase de fichiers
Spécifiez le chemin vers votre dossier `.gdb` et ouvrez‑le avec le driver `FileGdb`.

```csharp
using (var dataset = Dataset.Open(dataDir + "ThreeLayers.gdb", Drivers.FileGdb))
```

### Étape 2 : Parcourir les couches
Une File Geodatabase peut contenir plusieurs couches (classes d’entités). Parcourez‑les pour traiter chacune.

```csharp
for (int i = 0; i < dataset.LayersCount; ++i)
{
    // Access layer information
}
```

### Étape 3 : Accéder aux informations de la couche
À l’intérieur de la boucle, récupérez le nom de la couche et le nombre d’entités. Cela vous aide à comprendre la structure du jeu de données avant d’aller plus loin.

```csharp
Console.WriteLine("Layer {0} name: {1}", i, dataset.GetLayerName(i));
```

### Étape 4 : Ouvrir une couche et énumérer ses entités
Ouvrez la couche courante et parcourez chaque entité qu’elle contient.

```csharp
using (var layer = dataset.OpenLayerAt(i))
{
    foreach (var feature in layer)
    {
        // Access feature geometry or properties
    }
}
```

### Étape 5 : Travailler avec la géométrie des entités
Pour chaque entité, vous pouvez lire sa géométrie, ses attributs, voire les modifier. Ici nous affichons simplement la géométrie au format WKT (Well‑Known Text).

```csharp
Console.WriteLine(feature.Geometry.AsText());
```

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Exception `File not found`** | Le chemin vers le dossier `.gdb` est incorrect ou le dossier est absent. | Vérifiez que `dataDir` pointe vers le dossier contenant `ThreeLayers.gdb`. Utilisez des chemins absolus pour le débogage. |
| **Aucune couche retournée** | Le jeu de données a été ouvert avec le mauvais driver. | Assurez‑vous d’utiliser `Drivers.FileGdb` ; d’autres drivers (ex. `Drivers.Shapefile`) ne lisent pas une GDB. |
| **Géométrie nulle** | L’entité n’a pas de géométrie (ex. couche d’annotation). | Ajoutez une vérification de null avant d’appeler `AsText()`. |
| **Ralentissement des performances sur de grandes GDB** | L’itération sans pagination charge tout en mémoire. | Traitez les entités par lots ou utilisez `layer.Select` avec un filtre pour limiter les lignes. |

## Questions fréquentes

**Q : Aspose.GIS pour .NET est‑il compatible avec toutes les versions du .NET Framework ?**  
R : Oui, il fonctionne avec .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 et les versions ultérieures.

**Q : Puis‑je intégrer Aspose.GIS avec d’autres plateformes SIG ?**  
R : Absolument. Vous pouvez lire une File Geodatabase puis l’exporter vers Shapefile, GeoJSON ou tout autre format supporté pour les outils en aval.

**Q : Aspose.GIS prend‑il en charge différents formats de données géospatiales ?**  
R : Oui, il supporte plus de 60 formats, dont Shapefile, GeoJSON, KML, GML et des formats raster comme GeoTIFF.

**Q : Existe‑t‑il un forum communautaire où je peux poser des questions sur Aspose.GIS ?**  
R : Oui, vous pouvez visiter le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour interagir avec la communauté et obtenir de l’aide d’experts.

**Q : Puis‑je essayer Aspose.GIS pour .NET avant d’acheter ?**  
R : Bien sûr, vous pouvez profiter de l’essai gratuit d’Aspose.GIS pour .NET depuis la [page de diffusion](https://releases.aspose.com/), ce qui vous permet d’explorer ses fonctionnalités avant de vous engager.

## Conclusion
En suivant les étapes ci‑dessus, vous savez maintenant **comment lire les données d’une géodatabase** à l’aide d’Aspose.GIS pour .NET. Cette approche vous donne un contrôle programmatique complet sur les couches et les entités, ouvrant la voie à des analyses GIS personnalisées, à la migration de données ou à des visualisations cartographiques dans n’importe quelle application .NET.

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.GIS for .NET 24.11 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}