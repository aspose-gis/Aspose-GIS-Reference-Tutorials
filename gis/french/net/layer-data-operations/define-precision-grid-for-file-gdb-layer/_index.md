---
date: 2026-09-30
description: Apprenez à créer une geodatabase et à définir une grille de précision
  pour une couche File GDB en utilisant Aspose.GIS for .NET, y compris l'ajout de
  features à une couche et la validation de coordinate range.
keywords:
- how to create geodatabase
- how to validate coordinates
- handle out of range
- configure coordinate grid
- validate coordinate range
lastmod: 2026-09-30
linktitle: Définir la grille de précision pour une couche File GDB
og_description: Apprenez à créer une geodatabase et à définir une grille de précision
  pour une couche File GDB en utilisant Aspose.GIS for .NET, en garantissant des coordonnées
  précises et la gestion des out‑of‑range.
og_image_alt: Developer guide showing how to create a geodatabase and configure a
  precision grid with Aspose.GIS
og_title: Comment créer une geodatabase et définir une grille de précision pour une
  couche File GDB
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create geodatabase and set a precision grid for a File
    GDB layer using Aspose.GIS for .NET, including adding features to a layer and
    validating coordinate range.
  headline: How to create geodatabase and set grid for File GDB layer
  type: TechArticle
- description: Learn how to create geodatabase and set a precision grid for a File
    GDB layer using Aspose.GIS for .NET, including adding features to a layer and
    validating coordinate range.
  name: How to create geodatabase and set grid for File GDB layer
  steps:
  - name: create a dataset
    text: '`Dataset` represents a file‑geodatabase container that holds one or more
      spatial layers.'
  - name: define precision grid options
    text: '`PrecisionGridOptions` specifies the origin, scale, and validation behavior
      for coordinates. *The `EnsureValidCoordinatesRange = true` flag tells Aspose.GIS
      to **validate coordinate range** for every feature you add.*'
  - name: create a layer with the grid
    text: '`FeatureLayer` is the object that stores vector features inside a dataset.'
  - name: add features to the layer
    text: '`Feature` represents a single geometric object (point, line, polygon) together
      with its attribute values.'
  - name: handle exceptions when adding out‑of‑range features
    text: '`FeatureException` is thrown when a geometry violates the defined grid
      limits.'
  - name: clean up
    text: The `using` statements automatically close and dispose of the dataset and
      layer, ensuring all resources are released.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports Shapefile, GeoJSON, KML, and many more formats—over
      30 in total.
    question: Can I use Aspose.GIS for .NET with other GIS file formats?
  - answer: Absolutely. The library works with .NET Framework, .NET Core, and .NET
      5/6+.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, the API includes methods for buffering, intersecting, and calculating
      distances.
    question: Can I perform spatial operations such as buffering or intersection?
  - answer: Yes, you can transform geometries between different spatial reference
      systems using the built‑in reprojection tools.
    question: Does Aspose.GIS provide coordinate transformation capabilities?
  - answer: Yes, you can download a free trial from the [website](https://releases.aspose.com/gis/net/).
    question: Is there a trial version available?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create geodatabase
- Aspose.GIS
- .NET GIS programming
- precision grid
title: Comment créer une geodatabase et définir une grille de précision pour une couche
  File GDB
url: /fr/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir la grille pour une couche File GDB dans Aspose.GIS

## Introduction
Dans ce tutoriel, vous allez **créer une géodatabase**, ajouter une couche et apprendre comment **définir une grille de précision** pour cette couche File Geodatabase (GDB) en utilisant Aspose.GIS pour .NET. Définir une grille de précision vous permet de **valider la plage de coordonnées**, empêche les erreurs hors plage et garantit que toute opération **ajout de fonctionnalités à la couche** stocke les données avec précision. Vous verrez pourquoi cela est important, comment **configurer la grille de coordonnées**, et comment **gérer les scénarios hors plage** de manière fluide.

## Réponses rapides
- **Que signifie « set grid » ?** Elle définit la précision des coordonnées et la plage valide pour une couche GIS.  
- **Pourquoi utiliser une grille de précision ?** Elle protège vos données des coordonnées invalides et améliore l’efficacité du stockage.  
- **Quelle bibliothèque fournit cette fonctionnalité ?** Aspose.GIS for .NET.  
- **Ai-je besoin d’une licence ?** Une version d’essai est disponible ; une licence commerciale est requise pour la production.  
- **Puis-je l’utiliser avec .NET Core ?** Oui, Aspose.GIS prend en charge .NET Framework et .NET Core.

## Qu’est‑ce qu’une grille de précision et pourquoi la définir ?
Une grille de précision est un ensemble de paramètres (origine, échelle, etc.) qui indique au moteur GIS comment arrondir et stocker les valeurs de coordonnées. En configurant une grille, vous **validez automatiquement la plage de coordonnées**, et toute tentative d’insérer un point en dehors de la grille déclenchera une exception—vous aidant à **gérer les scénarios hors plage** dès le début du développement.

## Pourquoi créer une géodatabase avec une grille de précision ?
Créer une géodatabase de fichiers vous fournit un conteneur portable et haute performance pour les données vectorielles. Ajouter une grille de précision lors de la création garantit que chaque entité stockée respecte les mêmes limites numériques, améliore la vitesse d’indexation et détecte les coordonnées invalides avant qu’elles ne corrompent le jeu de données. Cette validation précoce réduit les efforts de nettoyage en aval et garantit une qualité de données cohérente tout au long du projet.

- **Qualité de données cohérente** – chaque entité respecte la même précision numérique.  
- **Indexation plus rapide** – le moteur peut stocker les coordonnées plus efficacement.  
- **Détection précoce des erreurs** – les coordonnées hors plage sont détectées avant de corrompre le jeu de données.

## Prérequis
Avant de commencer, assurez‑vous d’avoir les éléments suivants installés :

1. **Visual Studio** – toute version récente (Community, Professional ou Enterprise).  
2. **Aspose.GIS for .NET** – téléchargez‑le depuis le [site web](https://releases.aspose.com/gis/net/).  
3. **Connaissances de base en C#** – vous devez être à l’aise avec la création de projets console .NET.

## Cas d’utilisation courants
- **Collecte de données sur le terrain** où les appareils GPS peuvent produire des coordonnées légèrement en dehors de l’étendue prévue.  
- **Migration de données** depuis des systèmes hérités qui utilisaient des précisions de coordonnées différentes.  
- **Pipelines ETL automatisés** qui doivent garantir l’intégrité spatiale avant de charger les données dans une base de données GIS.

## Importer les espaces de noms
Les espaces de noms Aspose.GIS requis fournissent les classes pour travailler avec les jeux de données, les couches et les géométries.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Comment configurer la grille de coordonnées dans une couche File GDB
Dans cette section, nous parcourons le processus complet de création d’un jeu de données, de définition d’une grille de précision, d’ajout d’une couche, d’insertion d’entités et de gestion des éventuelles erreurs. Les étapes sont illustrées par des extraits de code concis, et chaque étape comprend une brève explication de la raison pour laquelle l’opération est nécessaire au maintien de l’intégrité spatiale.

### Étape 1 : créer un jeu de données
`Dataset` représente un conteneur de géodatabase de fichiers qui contient une ou plusieurs couches spatiales.  

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Étape 2 : définir les options de grille de précision
`PrecisionGridOptions` spécifie l’origine, l’échelle et le comportement de validation des coordonnées.  

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*Le drapeau `EnsureValidCoordinatesRange = true` indique à Aspose.GIS de **valider la plage de coordonnées** pour chaque entité que vous ajoutez.*

### Étape 3 : créer une couche avec la grille
`FeatureLayer` est l’objet qui stocke les entités vectorielles à l’intérieur d’un jeu de données.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Étape 4 : ajouter des entités à la couche
`Feature` représente un objet géométrique unique (point, ligne, polygone) ainsi que ses valeurs d’attributs.  

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Étape 5 : gérer les exceptions lors de l’ajout d’entités hors plage
`FeatureException` est levée lorsqu’une géométrie viole les limites de la grille définie.  

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### Étape 6 : nettoyage
Les instructions `using` ferment et libèrent automatiquement le jeu de données et la couche, garantissant que toutes les ressources sont libérées.

## Pourquoi configurer une grille de précision ?
Aspose.GIS prend en charge **plus de 30 formats de fichiers GIS** et peut traiter des **jeux de données de plusieurs centaines de pages** sans charger le fichier complet en mémoire. L’utilisation d’une grille de précision réduit la taille de stockage jusqu’à **15 %** et diminue le temps d’indexation d’environ **20 %** car les coordonnées sont stockées sous une forme normalisée et arrondie.

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Exception : « X value … is out of valid range. »** | Les coordonnées sont en dehors de la grille de précision. | Ajustez `XOrigin`, `YOrigin` ou `XYScale` pour couvrir vos données, ou assurez‑vous que les données d’entrée sont dans la plage définie. |
| **Les entités n’apparaissent pas dans le visualiseur GIS** | Couche non enregistrée ou référence spatiale incorrecte. | Vérifiez que `SpatialReferenceSystem.Wgs84` correspond au CRS du visualiseur, et que `Dataset.Create` a réussi. |
| **Valeurs M ignorées** | `MScale` réglé à 0 ou trop bas. | Définissez un `MScale` raisonnable (par ex., `1e4`) pour stocker les valeurs de mesure. |

## Conseils de dépannage
- **Vérifiez à nouveau les étendues de la grille** avant de charger de gros lots de données ; une petite faute de frappe dans `XOrigin` peut entraîner le rejet de nombreuses lignes.  
- **Enregistrez le message d’exception** (comme montré dans le bloc try‑catch) dans un fichier lors du traitement d’importations automatisées ; cela facilite la détection de motifs dans les données hors plage.  
- **Utilisez `EnsureValidCoordinatesRange = false` uniquement pour des sources de données fiables** – le désactiver supprime la validation et peut entraîner des géométries corrompues.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.GIS pour .NET avec d’autres formats de fichiers GIS ?**  
R : Oui, Aspose.GIS prend en charge Shapefile, GeoJSON, KML et de nombreux autres formats—plus de 30 au total.

**Q : Aspose.GIS pour .NET est‑il compatible avec .NET Core ?**  
R : Absolument. La bibliothèque fonctionne avec .NET Framework, .NET Core et .NET 5/6+.

**Q : Puis‑je effectuer des opérations spatiales telles que le buffering ou l’intersection ?**  
R : Oui, l’API inclut des méthodes de buffering, d’intersection et de calcul des distances.

**Q : Aspose.GIS offre‑t‑il des capacités de transformation de coordonnées ?**  
R : Oui, vous pouvez transformer des géométries entre différents systèmes de référence spatiale à l’aide des outils de reprojection intégrés.

**Q : Une version d’essai est‑elle disponible ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite depuis le [site web](https://releases.aspose.com/gis/net/).

---

**Dernière mise à jour :** 2026-09-30  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Comment créer un jeu de données GDB avec Aspose.GIS pour .NET](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Comment ajouter une couche à un jeu de données File GDB avec la référence spatiale WGS84 en utilisant Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)
- [Comment créer un jeu de données GDB et définir les tolérances pour une couche](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}