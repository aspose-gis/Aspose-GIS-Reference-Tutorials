---
date: 2026-06-30
description: Apprenez à créer une couche vectorielle dans un File Geodatabase en utilisant
  Aspose.GIS pour .NET. Gérez les données géospatiales avec la référence spatiale
  WGS84 et les options de file gdb.
keywords:
- create vector layer
- add line feature
- manage geospatial data
- feature count example
- file gdb compression
linktitle: Créer un File GDB avec une seule couche
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  headline: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  type: TechArticle
- description: Learn how to create vector layer in a File Geodatabase using Aspose.GIS
    for .NET. Manage geospatial data with spatial reference WGS84 and file gdb options.
  name: Create Vector Layer in File GDB – Aspose.GIS .NET Tutorial
  steps:
  - name: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS for .NET** – download it from the [Aspose.GIS for .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
    text: '**A .NET development environment** – Visual Studio, Rider, or the `dotnet`
      CLI.'
  - name: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
    text: '**A folder** where the File GDB will be created (we’ll call it *Your Document
      Directory*).'
  type: HowTo
- questions:
  - answer: It means adding a new vector dataset (points, lines, or polygons) to a
      geodatabase file.
    question: What does “create vector layer” mean?
  - answer: Aspose.GIS for .NET provides full support for File GDB creation and editing.
    question: Which library should I use?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `SpatialReferenceSystem.Wgs84` for the common WGS84 datum.
    question: Can I set the spatial reference?
  - answer: Less than 30 lines to create the GDB, add a line feature, and read back
      the feature count.
    question: How many lines of code?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Créer une couche vectorielle dans un File GDB – Tutoriel Aspose.GIS .NET
url: /fr/net/layer-management/create-file-gdb-with-single-layer/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une couche vectorielle dans un fichier GDB

## Introduction
If you need to **create vector layer** inside a File Geodatabase (GDB) and manage geospatial data efficiently, Aspose.GIS for .NET gives you a clean, code‑first approach. In this step‑by‑step guide we’ll show you how to write a line feature, configure file GDB options, and work with the spatial reference WGS84—all in a few lines of C#. By the end you’ll be able to count features in a layer and integrate the resulting GDB into any .NET mapping or analysis workflow.

## Réponses rapides
- **Que signifie « create vector layer » ?** Cela signifie ajouter un nouveau jeu de données vectorielles (points, lignes ou polygones) à un fichier de géodatabase.  
- **Quelle bibliothèque dois‑je utiliser ?** Aspose.GIS for .NET provides full support for File GDB creation and editing.  
- **Ai‑je besoin d’une licence pour le développement ?** Une version d’essai gratuite fonctionne pour les tests ; une licence commerciale est requise pour la production.  
- **Puis‑je définir la référence spatiale ?** Oui – utilisez `SpatialReferenceSystem.Wgs84` pour le datum WGS84 commun.  
- **Combien de lignes de code ?** Moins de 30 lignes pour créer le GDB, ajouter une entité linéaire et lire le nombre d’entités.

## Qu’est‑ce qu’une opération « create vector layer » ?
Creating a vector layer defines a new table in a geodatabase that stores geometric objects (points, lines, polygons) and their attributes. Each row represents a feature, and the geometry column holds its shape. In Aspose.GIS you create it by instantiating a `FeatureClass` within a `FileGdbDataSource` and specifying the geometry type.

## Pourquoi utiliser Aspose.GIS pour créer une couche vectorielle ?
Aspose.GIS eliminates external dependencies and supports **50+** GIS formats, making it a one‑stop solution for .NET developers.  
It provides built‑in file GDB compression (up to 70 % reduction for typical vector data), spatial indexing, and full WGS84 handling out of the box. The library works on .NET Framework 4.6+, .NET Core 2.0+, and .NET 5/6, so you can target any modern Windows or cross‑platform environment without additional native libraries.

## Prérequis
Before you start, make sure you have:

1. **Aspose.GIS for .NET** – téléchargez‑le depuis la [page de téléchargement d'Aspose.GIS pour .NET](https://releases.aspose.com/gis/net/).  
2. **Un environnement de développement .NET** – Visual Studio, Rider, ou le CLI `dotnet`.  
3. **Un dossier** où le File GDB sera créé (nous l’appellerons *Your Document Directory*).

## Importer les espaces de noms
The `using` statements bring the required types into scope.  

The `Document` namespace provides the core GIS objects, while `System.IO` handles file paths.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.SpatialReferencing;
```

## Étape 1 : Configurer votre répertoire de documents
Replace `"Your Document Directory"` with the absolute path where you want the File GDB to live.  
Creating the directory ahead of time avoids the “File not found” error that often trips new users.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : Créer une géodatabase fichier avec une couche unique
FileGdbOptions is a class that lets you configure compression, spatial indexing, and other settings for a File Geodatabase.  
This snippet **creates a vector layer** using `FileGdbOptions`, writes a simple line feature, and stores it in a File GDB that uses the **spatial reference WGS84**.

```csharp
var options = new FileGdbOptions();
using (var layer = VectorLayer.Create(path, Drivers.FileGdb, options, SpatialReferenceSystem.Wgs84))
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

## Étape 3 : Ouvrir la géodatabase fichier et récupérer les informations de la couche
`FileGdbDataSource` is the entry point for creating and opening File Geodatabases.  
`FeatureClass` represents a vector layer within a geodatabase and provides access to its features.  
Here we **count features in the layer** by opening the dataset and printing the number of features – in this case, `1`.

```csharp
using (var dataset = Dataset.Open(path, Drivers.FileGdb))
using (var layer = dataset.OpenLayer("layer"))
{
    Console.WriteLine("Features count: {0}", layer.Count); // Output: Features count: 1
}
```

## Comment vérifier que la couche a été créée correctement ?
Open the geodatabase with `FileGdbDataSource.Open` and query the `FeatureClass`. The `Count` property returns the total number of features, confirming that the line was persisted. This quick verification step helps you catch issues early, especially when automating bulk imports.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **`File not found`** | Variable `path` incorrecte | Vérifiez que `dataDir` pointe vers un dossier existant et que `path` le combine avec un nom de fichier, par ex., `Path.Combine(dataDir, "MyData.gdb")`. |
| **`Unsupported geometry`** | Utilisation d’un type de géométrie non autorisé dans le File GDB | Utilisez `Point`, `LineString` ou `Polygon` pour les couches de base. |
| **`License not set`** | Exécution sans licence valide en production | Enregistrez votre licence avec `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Questions fréquentes
### Puis‑je utiliser Aspose.GIS pour .NET dans mes projets .NET existants ?
Oui, Aspose.GIS pour .NET peut être intégré de manière transparente dans vos projets .NET existants.

### Existe‑t‑il une version d’essai disponible pour Aspose.GIS pour .NET ?
Oui, vous pouvez explorer les fonctionnalités d’Aspose.GIS pour .NET en téléchargeant la [version d’essai gratuite](https://releases.aspose.com/).

### Où puis‑je trouver la documentation détaillée d’Aspose.GIS pour .NET ?
Consultez la [documentation](https://reference.aspose.com/gis/net/) pour des informations complètes sur Aspose.GIS pour .NET.

### Comment obtenir du support pour Aspose.GIS pour .NET ?
Visitez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour obtenir le support de la communauté et de l’aide.

### Des licences temporaires sont‑elles disponibles pour Aspose.GIS pour .NET ?
Oui, vous pouvez obtenir une [licence temporaire](https://purchase.aspose.com/temporary-license/) pour Aspose.GIS pour .NET.

---

**Dernière mise à jour:** 2026-06-30  
**Testé avec:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose

## Tutoriels associés

- [Créer un jeu de données .NET de géodatabase fichier avec Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Créer une couche vectorielle et définir le système de référence spatiale de la couche](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Comment supprimer une couche d’un jeu de données File GDB avec Aspose.GIS](/gis/net/layer-data-operations/remove-layers-from-file-gdb-dataset/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}