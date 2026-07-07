---
date: 2026-06-15
description: Apprenez à créer une couche vectorielle et à définir le système de référence
  spatiale de la couche avec Aspose.GIS for .NET. Maîtrisez la définition de la référence
  spatiale, l'ajout d'une entité ponctuelle et la récupération du code EPSG.
keywords:
- create vector layer
- add point feature
- set layer coordinate system
- define epsg code
- how to set crs
linktitle: Définir le système de référence spatiale de la couche
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  headline: Create Vector Layer and Set Layer Spatial Reference System
  type: TechArticle
- description: Learn how to create vector layer and set layer spatial reference system
    with Aspose.GIS for .NET. Master defining spatial reference, adding point feature,
    and retrieving EPSG code.
  name: Create Vector Layer and Set Layer Spatial Reference System
  steps:
  - name: Specify the Document Directory
    text: Begin by specifying the path to your document directory. This will be the
      location where your spatial data files are stored.
  - name: Define Spatial Reference and Set Shapefile Coordinate System
    text: SpatialReferenceSystem represents the CRS of a layer, identified by an EPSG
      code. Define the path for the Shapefile, and **define spatial reference** using
      the EPSG code (26918 in this example). This step **sets the shapefile coordinate
      system** for the layer.
  - name: Create Vector Layer
    text: '`ConstructFeature` creates a new feature object that can hold geometry
      and attribute data. Now **create vector layer** with the specified Shapefile
      path, driver type (Shapefile), and the spatial reference system you just defined.'
  - name: Add Point Feature to the Layer
    text: Construct a new feature and **add point feature** by setting its geometry
      (a `Point` with coordinates 60, 24). Then add the feature to the vector layer.
  - name: Retrieve Spatial Reference System Information (Retrieve EPSG Code)
    text: Open the Vector Layer and retrieve information about the spatial reference
      system, such as the EPSG code and the human‑readable name. This demonstrates
      how to **retrieve EPSG code** and **set layer CRS**.
  type: HowTo
- questions:
  - answer: Open the layer, create a new `SpatialReferenceSystem` with the desired
      EPSG code, assign it to `layer.SpatialReferenceSystem`, then save the layer.
    question: How do I change the CRS of an existing Shapefile?
  - answer: Yes—replace `new Point(x, y)` with `new Polygon(...)` or `new LineString(...)`
      as needed.
    question: Can I add other geometry types (e.g., polygons) using the same approach?
  - answer: Use streaming APIs (`VectorLayer.Create` with `FeatureCollection`) and
      dispose layers promptly to free resources.
    question: Is it possible to work with large datasets efficiently?
  - answer: Yes—use `Geometry.Transform(targetSrs)` to reproject geometries between
      different spatial references.
    question: Does Aspose.GIS support coordinate transformation?
  - answer: Aspose.GIS works with .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Créer une couche vectorielle et définir le système de référence spatiale de
  la couche
url: /fr/net/layer-data-operations/set-layer-spatial-reference-system/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une couche vectorielle et définir le système de référence spatiale de la couche

## Introduction
Dans le vaste paysage des systèmes d’information géographique (SIG), **Aspose.GIS for .NET** se distingue comme une bibliothèque robuste et haute performance qui prend en charge **plus de 70** formats vectoriels et raster et peut traiter des fichiers de plus de **10 GB** sans charger l’ensemble du jeu de données en mémoire. Dans ce tutoriel, vous allez **créer une couche vectorielle**, définir sa référence spatiale, **ajouter une entité point**, et récupérer le code EPSG — le tout avec des instructions claires, étape par étape. Que vous construisiez un service de cartographie, un pipeline de conversion de données ou un moteur d’analyse spatiale, maîtriser ces fondamentaux garantira la précision du système de coordonnées de votre shapefile et la fiabilité de votre flux de travail SIG.

## Réponses rapides
- **Que signifie « create vector layer » ?** Cela crée une nouvelle couche GIS (par ex., un Shapefile) qui peut stocker des géométries telles que des points, des lignes ou des polygones.  
- **Quel code EPSG est utilisé dans l'exemple ?** EPSG 26918 (NAD83 / UTM zone 18N).  
- **Puis‑je ajouter une entité point après avoir créé la couche ?** Oui—utilisez `ConstructFeature()` et attribuez une géométrie `Point`.  
- **Comment récupérer le CRS de la couche ?** Lisez `layer.SpatialReferenceSystem.EpsgCode` ou `.Name`.  
- **Ai‑je besoin d’une licence pour Aspose.GIS ?** Un essai gratuit est disponible ; une licence est requise pour une utilisation en production.

## Qu’est‑ce que créer une couche vectorielle ?
L’opération **create vector layer** crée un nouveau jeu de données vectorielles (tel qu’un Shapefile) pouvant contenir des entités géométriques et des données attributaires. Dans Aspose.GIS, cela se fait en instanciant un objet `VectorLayer` avec un driver et un système de référence spatiale.

## Pourquoi définir correctement le système de coordonnées (CRS) de la couche ?
Définir le système de référence de coordonnées (CRS) correct garantit que chaque géométrie que vous stockez s’aligne avec d’autres jeux de données spatiales. Avec Aspose.GIS, vous pouvez définir le CRS à l’aide d’un code EPSG standard, ce qui assure l’interopérabilité avec les logiciels SIG du monde entier. Par exemple, EPSG 26918 définit NAD83 / UTM zone 18N, une projection courante pour les données de l’est des États‑Unis.

## Prérequis
- Expérience en développement .NET (C# ou VB.NET).  
- Visual Studio 2022 ou version ultérieure.  
- Bibliothèque Aspose.GIS pour .NET – téléchargez‑la **[ici](https://releases.aspose.com/gis/net/)**.  
- Familiarité de base avec les systèmes de référence spatiale (CRS/EPSG).

## Importer les espaces de noms
L’espace de noms `Aspose.Gis` fournit les classes SIG de base, tandis que `Aspose.Gis.Geometries` vous donne les types de géométrie tels que `Point`.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
```

## Comment créer une couche vectorielle dans Aspose.GIS pour .NET ?
`VectorLayer` représente un jeu de données vectorielles tel qu’un Shapefile et fournit des méthodes pour créer, lire et modifier des entités.  
`SpatialReferenceSystem` définit le système de référence de coordonnées à l’aide d’un code EPSG.  

Chargez le dossier cible, définissez un `SpatialReferenceSystem` codé EPSG, puis appelez `VectorLayer.Create` avec le driver Shapefile. Cette unique appel alloue un nouveau fichier `.shp`, écrit les fichiers associés `.shx` et `.dbf`, et intègre les métadonnées CRS, prêtes pour l’insertion d’entités de manière efficace.

### Étape 1 : Spécifier le répertoire du document
Commencez par spécifier le chemin vers votre répertoire de documents. Ce sera l’emplacement où vos fichiers de données spatiales seront stockés.

```csharp
string dataDir = "Your Document Directory";
```

### Étape 2 : Définir la référence spatiale et définir le système de coordonnées du Shapefile
`SpatialReferenceSystem` représente le CRS d’une couche, identifié par un code EPSG.  

Définissez le chemin du Shapefile, et **définissez la référence spatiale** en utilisant le code EPSG (26918 dans cet exemple). Cette étape **définit le système de coordonnées du Shapefile** pour la couche.

```csharp
string path = dataDir + "SpecifyLayerSpatialReference_out.shp";
var srs = SpatialReferenceSystem.CreateFromEpsg(26918);
```

## Comment ajouter une entité point à une couche vectorielle ?
`Point` est un type de géométrie représentant une paire de coordonnées X/Y unique.  

Construisez une nouvelle entité, attribuez‑lui une géométrie `Point` avec les coordonnées X/Y souhaitées, puis ajoutez l’entité à la `VectorLayer` ouverte. L’opération écrit la géométrie dans le fichier `.shp` et l’enregistrement attributaire dans le fichier `.dbf` en une seule transaction.

### Étape 3 : Créer la couche vectorielle
`ConstructFeature` crée un nouvel objet entité pouvant contenir géométrie et données attributaires.  

Maintenant, **créez la couche vectorielle** avec le chemin Shapefile spécifié, le type de driver (Shapefile) et le système de référence spatiale que vous venez de définir.

```csharp
using (VectorLayer layer = VectorLayer.Create(path, Drivers.Shapefile, srs))
{
    // Your code for further operations on the layer goes here
}
```

### Étape 4 : Ajouter une entité point à la couche
Construisez une nouvelle entité et **ajoutez l’entité point** en définissant sa géométrie (un `Point` avec les coordonnées 60, 24). Puis ajoutez l’entité à la couche vectorielle.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(60, 24);
layer.Add(feature);
```

### Étape 5 : Récupérer les informations du système de référence spatiale (récupérer le code EPSG)
Ouvrez la couche vectorielle et récupérez les informations sur le système de référence spatiale, telles que le code EPSG et le nom lisible par l’homme. Cela montre comment **récupérer le code EPSG** et **définir le CRS de la couche**.

```csharp
using (VectorLayer layer = VectorLayer.Open(path, Drivers.Shapefile))
{
    Console.WriteLine(layer.SpatialReferenceSystem.EpsgCode); // 26918
    Console.WriteLine(layer.SpatialReferenceSystem.Name);     // NAD83_UTM_zone_18N
}
```

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Échec de l'ouverture de la couche** | Pilote incorrect ou chemin de fichier corrompu | Vérifiez `Drivers.Shapefile` et assurez‑vous que `path` pointe vers un fichier `.shp` existant. |
| **CRS affiché incorrectement** | Utilisation d'un mauvais code EPSG | Revérifiez le code EPSG avec une source autoritaire (p. ex., EPSG.io). |
| **Entité non enregistrée** | Absence d’appel à `layer.Add(feature)` dans le bloc `using` | Assurez‑vous que la méthode `Add` est exécutée avant la libération de la couche. |

## Questions fréquemment posées
**Q : Comment changer le CRS d’un Shapefile existant ?**  
R : Ouvrez la couche, créez un nouveau `SpatialReferenceSystem` avec le code EPSG souhaité, assignez‑le à `layer.SpatialReferenceSystem`, puis enregistrez la couche.

**Q : Puis‑je ajouter d’autres types de géométrie (par ex., des polygones) avec la même approche ?**  
R : Oui—remplacez `new Point(x, y)` par `new Polygon(...)` ou `new LineString(...)` selon le besoin.

**Q : Est‑il possible de travailler avec de grands ensembles de données de façon efficace ?**  
R : Utilisez les API de streaming (`VectorLayer.Create` avec `FeatureCollection`) et libérez rapidement les couches pour libérer les ressources.

**Q : Aspose.GIS prend‑il en charge la transformation de coordonnées ?**  
R : Oui—utilisez `Geometry.Transform(targetSrs)` pour reprojeter les géométries entre différentes références spatiales.

**Q : Quelles versions de .NET sont prises en charge ?**  
R : Aspose.GIS fonctionne avec .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

---

**Dernière mise à jour :** 2026-06-15  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Créer une couche vectorielle et définir la tolérance de linéarisation avec Aspose.GIS pour .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Créer une couche vectorielle dans File GDB – Tutoriel Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [référence spatiale wgs84 – Ajouter une couche à GDB avec Aspose.GIS](/gis/net/layer-management/add-layer-to-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}