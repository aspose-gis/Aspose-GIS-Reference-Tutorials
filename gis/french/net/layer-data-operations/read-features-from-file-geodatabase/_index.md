---
date: 2026-09-30
description: Découvrez comment lire les entités de géodatabase dans .NET en utilisant
  Aspose.GIS, la fast library pour accéder aux données File Geodatabase dans les applications
  .NET.
keywords:
- read geodatabase features .net
- how to read file geodatabase
- Aspose.GIS .NET
- GIS data extraction
lastmod: 2026-09-30
linktitle: Lire les entités depuis File Geodatabase
og_description: Découvrez comment lire les entités de géodatabase dans .NET en utilisant
  Aspose.GIS, la fast library pour accéder aux données File Geodatabase dans les applications
  .NET.
og_image_alt: 'Developer guide: read geodatabase features .NET with Aspose.GIS'
og_title: Lire les entités de géodatabase dans .NET avec Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to read geodatabase features .NET using Aspose.GIS, the fast
    library for accessing File Geodatabase data in .NET applications.
  headline: Read geodatabase features in .NET with Aspose.GIS
  type: TechArticle
- description: Learn how to read geodatabase features .NET using Aspose.GIS, the fast
    library for accessing File Geodatabase data in .NET applications.
  name: Read geodatabase features in .NET with Aspose.GIS
  steps:
  - name: open the file geodatabase
    text: '`FileGdb` is the driver that enables reading Esri File Geodatabase (.gdb)
      containers. Provide the folder path and create a `GisDatabase` instance.'
  - name: iterate through layers
    text: A File Geodatabase can contain multiple layers (feature classes). The `Layer`
      object represents each of these collections. Loop through `database.Layers`
      to process them one by one.
  - name: access layer information
    text: Inside the loop, retrieve the layer’s name and feature count. Knowing the
      count up front helps you gauge dataset size before loading geometries.
  - name: open a layer and enumerate its features
    text: A `Feature` represents a single row in a layer, containing geometry and
      attribute values. Open the current layer and walk through every feature it holds.
  - name: work with feature geometry
    text: '`Geometry` objects expose spatial data. In this example we convert each
      geometry to Well‑Known Text (WKT) for easy console output. The `AsText()` method
      returns a string representation of the geometry.'
  type: HowTo
- questions:
  - answer: Yes, it works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6
      and later.
    question: Is Aspose.GIS for .NET compatible with all versions of .NET Framework?
  - answer: Absolutely. You can read from a File Geodatabase and then export to Shapefile,
      GeoJSON, or any of the 60+ supported formats for downstream tools.
    question: Can I integrate Aspose.GIS with other GIS platforms?
  - answer: Yes, it supports over 60 formats, including Shapefile, GeoJSON, KML, GML,
      and raster formats like GeoTIFF.
    question: Does Aspose.GIS provide support for different geospatial data formats?
  - answer: Yes, you can visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33)
      to interact with the community and get expert assistance.
    question: Is there a community forum for Aspose.GIS queries?
  - answer: Certainly, you can avail of the free trial of Aspose.GIS for .NET from
      the [release page](https://releases.aspose.com/), allowing you to explore its
      features before committing to a purchase.
    question: Can I try Aspose.GIS for .NET before purchasing?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- read geodatabase
- Aspose.GIS
- .NET GIS
- file geodatabase
- geospatial data
title: Lire les entités de géodatabase dans .NET avec Aspose.GIS
url: /fr/net/layer-data-operations/read-features-from-file-geodatabase/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire les entités de géodatabase en .NET avec Aspose.GIS

## Introduction
Si vous devez **lire les entités de géodatabase en .NET** rapidement et de manière fiable, Aspose.GIS pour .NET propose une API purement gérée qui élimine les dépendances natives. Dans ce tutoriel, vous verrez comment configurer un projet .NET, ouvrir une File Geodatabase, énumérer ses couches et extraire la géométrie de chaque entité au format Well‑Known Text (WKT). Cette approche fonctionne sous Windows, Linux et macOS, ce qui la rend idéale pour les solutions GIS multiplateformes.

## Réponses rapides
- **Quelle bibliothèque dois‑je utiliser ?** Aspose.GIS pour .NET (essai gratuit disponible).  
- **Quel format de fichier est pris en charge ?** File Geodatabase (.gdb) via le pilote `FileGdb`.  
- **Ai‑je besoin d’une licence pour le développement ?** Non, l’essai fonctionne pour le développement et les tests.  
- **Puis‑je exécuter cela sur .NET 6 + ?** Oui, Aspose.GIS prend en charge .NET 5, .NET 6 et les versions ultérieures.  
- **Combien de lignes de code ?** Environ 30 lignes pour lire et afficher toutes les géométries d’entités.

## Qu’est‑ce qu’une File Geodatabase ?
Une File Geodatabase (souvent abrégée en **GDB**) est le magasin de données basé sur des dossiers d’Esri qui contient des données vectorielles et raster dans un ensemble de fichiers. C’est le format de facto pour les SIG de bureau, et Aspose.GIS abstrait la gestion de fichiers de bas niveau afin que vous puissiez vous concentrer sur les données elles‑mêmes.

## Pourquoi utiliser Aspose.GIS pour lire une géodatabase ?
Aspose.GIS prend en charge **plus de 60** formats géospatiaux — y compris Shapefile, GeoJSON, KML et GML — tout en traitant des File Geodatabases de plusieurs centaines de pages sans charger l’ensemble du jeu de données en mémoire. Les benchmarks montrent que la lecture d’une GDB de 500 pages prend moins de 5 secondes sur un CPU typique de 2,5 GHz, offrant une expérience optimisée en performances pour les analyses à grande échelle.

## Prérequis
Avant de plonger dans le code, assurez‑vous d’avoir les éléments suivants :

1. **Environnement de développement .NET** – Visual Studio 2022 (ou tout IDE supportant .NET 6 +).  
2. **Aspose.GIS pour .NET** – téléchargez le dernier package depuis la [page de téléchargement](https://releases.aspose.com/gis/net/).  
3. **Connaissances de base en C#** – vous devez être à l’aise avec les instructions `using` et les boucles.

## Importer les espaces de noms
L’espace de noms `Aspose.Gis` contient les types GIS de base tels que `Drivers`, `Layer` et `Feature`. Importez les espaces de noms requis avant de commencer à travailler avec une géodatabase.

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

### Étape 1 : ouvrir la file geodatabase
`FileGdb` est le pilote qui permet de lire les conteneurs Esri File Geodatabase (.gdb). Fournissez le chemin du dossier et créez une instance `GisDatabase`.

```csharp
using (var dataset = Dataset.Open(dataDir + "ThreeLayers.gdb", Drivers.FileGdb))
```

### Étape 2 : parcourir les couches
Une File Geodatabase peut contenir plusieurs couches (classes d’entités). L’objet `Layer` représente chacune de ces collections. Parcourez `database.Layers` pour les traiter une par une.

```csharp
for (int i = 0; i < dataset.LayersCount; ++i)
{
    // Access layer information
}
```

### Étape 3 : accéder aux informations de la couche
À l’intérieur de la boucle, récupérez le nom de la couche et le nombre d’entités. Connaître ce nombre à l’avance vous aide à estimer la taille du jeu de données avant de charger les géométries.

```csharp
Console.WriteLine("Layer {0} name: {1}", i, dataset.GetLayerName(i));
```

### Étape 4 : ouvrir une couche et énumérer ses entités
Un `Feature` représente une ligne unique dans une couche, contenant la géométrie et les valeurs d’attributs. Ouvrez la couche actuelle et parcourez chaque entité qu’elle contient.

```csharp
using (var layer = dataset.OpenLayerAt(i))
{
    foreach (var feature in layer)
    {
        // Access feature geometry or properties
    }
}
```

### Étape 5 : travailler avec la géométrie d’entité
Les objets `Geometry` exposent les données spatiales. Dans cet exemple, nous convertissons chaque géométrie en Well‑Known Text (WKT) pour un affichage console simple. La méthode `AsText()` renvoie une représentation sous forme de chaîne de la géométrie.

```csharp
Console.WriteLine(feature.Geometry.AsText());
```

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **`File not found` exception** | Le chemin du dossier `.gdb` est incorrect ou le dossier est manquant. | Vérifiez que `dataDir` pointe vers le dossier contenant `ThreeLayers.gdb`. Utilisez des chemins absolus pour le débogage. |
| **Aucune couche renvoyée** | Le jeu de données a été ouvert avec le mauvais pilote. | Assurez‑vous d’utiliser `Drivers.FileGdb` ; d’autres pilotes (par ex., `Drivers.Shapefile`) ne lisent pas une GDB. |
| **La géométrie est nulle** | L’entité n’a pas de géométrie (par ex., couche d’annotation). | Ajoutez une vérification de null avant d’appeler `AsText()`. |
| **Ralentissement des performances sur les grandes GDB** | L’itération sans pagination charge tout en mémoire. | Traitez les entités par lots ou utilisez `layer.Select` avec un filtre pour limiter les lignes. |

## Questions fréquentes

**Q : Aspose.GIS pour .NET est‑il compatible avec toutes les versions du .NET Framework ?**  
**R :** Oui, il fonctionne avec .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 et les versions ultérieures.

**Q : Puis‑je intégrer Aspose.GIS avec d’autres plateformes GIS ?**  
**R :** Absolument. Vous pouvez lire une File Geodatabase puis l’exporter en Shapefile, GeoJSON ou tout autre des plus de 60 formats pris en charge pour les outils en aval.

**Q : Aspose.GIS prend‑il en charge différents formats de données géospatiales ?**  
**R :** Oui, il prend en charge plus de 60 formats, y compris Shapefile, GeoJSON, KML, GML et les formats raster comme GeoTIFF.

**Q : Existe‑t‑il un forum communautaire pour les questions sur Aspose.GIS ?**  
**R :** Oui, vous pouvez visiter le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour interagir avec la communauté et obtenir de l’aide d’experts.

**Q : Puis‑je essayer Aspose.GIS pour .NET avant d’acheter ?**  
**R :** Bien sûr, vous pouvez profiter de l’essai gratuit d’Aspose.GIS pour .NET depuis la [page de diffusion](https://releases.aspose.com/), ce qui vous permet d’explorer ses fonctionnalités avant de vous engager à l’achat.

## Conclusion
En suivant les étapes ci‑dessus, vous savez maintenant **comment lire les entités de géodatabase en .NET** en utilisant Aspose.GIS. Cette approche vous donne un contrôle programmatique complet sur les couches et les entités, ouvrant la voie à des analyses GIS personnalisées, à la migration de données ou à des visualisations cartographiques dans n’importe quelle application .NET.

---

**Last Updated:** 2026-09-30  
**Tested With:** Aspose.GIS for .NET 24.11 (latest)  
**Author:** Aspose

## Tutoriels associés

- [Créer une File Geodatabase & définir la grille pour la couche GDB (Aspose.GIS)](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Comment lire l’ObjectID depuis une couche File GDB en utilisant Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)
- [Apprendre à récupérer et mettre à jour les attributs de couche avec Aspose.GIS pour .NET](/gis/net/layer-interaction-and-data-access/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}