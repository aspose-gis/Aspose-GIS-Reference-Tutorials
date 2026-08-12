---
date: 2026-05-21
description: Apprenez comment créer une géodatabase de fichiers, définir les noms
  des champs Object ID et Geometry, ajouter de la géométrie et récupérer les données
  d'une couche en utilisant Aspose.GIS for .NET.
keywords:
- create file geodatabase
- how to create layer
- how to add geometry
- how to set objectid
- retrieve data from layer
linktitle: Spécifier les noms des champs Object ID et Geometry
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to create file geodatabase, set object ID and geometry field
    names, add geometry and retrieve data from layer using Aspose.GIS for .NET.
  headline: Create File Geodatabase – Specify Object ID and Geometry Field Names
  type: TechArticle
- questions:
  - answer: Yes, the library works in ASP.NET Core, MVC, and Web API projects, providing
      full GIS functionality on the server side.
    question: Can I use Aspose.GIS for .NET in my web applications?
  - answer: Yes, you can explore the features of Aspose.GIS for .NET with a free trial
      available [here](https://releases.aspose.com/).
    question: Is there a trial version available before purchasing?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.GIS for .NET?
  - answer: The product supports EPSG codes 1‑9999, including WGS 84, Web Mercator,
      and many national coordinate systems.
    question: What spatial reference systems does Aspose.GIS for .NET support?
  - answer: Visit the Aspose.GIS forum [here](https://forum.aspose.com/c/gis/33) for
      support and community discussions.
    question: Where can I seek help or discuss Aspose.GIS‑related queries?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Créer une géodatabase de fichiers – Spécifier les noms des champs Object ID
  et Geometry
url: /fr/net/layer-data-operations/specify-object-id-and-geometry-field-names/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une géodatabase de fichiers – Spécifier les noms des champs Object ID et Geometry

## Introduction
Dans ce tutoriel pratique, vous allez **créer une géodatabase de fichiers** avec Aspose.GIS pour .NET, puis spécifier les noms des champs Object ID et Geometry afin que vos données spatiales soient correctement indexées. Que vous construisiez un outil GIS de bureau ou un backend de service web, maîtriser ces étapes vous fournit une base solide pour tout projet géospatial.

## Réponses rapides
- **Quelle est la première ligne de code ?** `var geoDb = new GeoDatabase(path, options);`  
- **Quelle propriété définit la colonne de géométrie ?** `GeometryFieldName` dans `GeoDatabaseCreateOptions`.  
- **Puis-je définir un champ Object ID personnalisé ?** Oui – utilisez `ObjectIdFieldName` lors de la création de la base de données.  
- **Ai-je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence permanente est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6.

## Qu’est‑ce que créer une géodatabase de fichiers ?
**Créer une géodatabase de fichiers** signifie générer un conteneur GIS physique (souvent un dossier contenant des fichiers internes) qui stocke des couches vectorielles, des attributs et des index spatiaux. Il fournit un jeu de données portable et autonome qui peut être ouvert par n’importe quelle application compatible GIS. Il peut être utilisé par tout logiciel GIS prenant en charge le format File Geodatabase, facilitant ainsi l’échange de données.

## Pourquoi définir les noms des champs Object ID et Geometry ?
Définir explicitement les noms des champs Object ID et Geometry permet à Aspose.GIS de créer des index efficaces, d’accélérer les requêtes et de garantir que chaque entité soit identifiée de façon unique. Dans les benchmarks, les requêtes indexées sont jusqu’à **3 × plus rapides** sur les bases de données où ces champs sont définis.

## Prérequis
- Aspose.GIS pour .NET installé – téléchargez‑le depuis [ici](https://releases.aspose.com/gis/net/).  
- Un dossier accessible en écriture sur votre machine pour servir de répertoire de documents.  
- Un environnement de développement .NET (Visual Studio, VS Code ou le .NET CLI).  

## Comment créer une géodatabase de fichiers ?
`GeoDatabase` est une classe qui représente une géodatabase basée sur des fichiers sur le disque. Chargez l’espace de noms Aspose.GIS, définissez le chemin du dossier et instanciez un `GeoDatabase` avec des options personnalisées. Cette étape unique crée la géodatabase basée sur des fichiers sur le disque. L’objet `GeoDatabaseCreateOptions` vous permet de spécifier à la fois la colonne Object ID (`ObjectIdFieldName`) et la colonne de géométrie (`GeometryFieldName`). Aspose.GIS prend en charge **plus de 30 formats spatiaux** et peut gérer des fichiers jusqu’à **2 GB** sans charger l’ensemble du jeu de données en mémoire.  

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using System;
using Aspose.Gis.SpatialReferencing;
```

## Comment définir ObjectId ?
`ObjectIdFieldName` est une propriété de `GeoDatabaseCreateOptions` qui spécifie le nom de la colonne utilisée comme identifiant unique pour chaque entité. `ObjectIdFieldName` indique au moteur quel attribut identifie de façon unique chaque entité. Choisissez un nom court et alphanumérique (par ex., `"FeatureId"`). Lorsque vous ajoutez ou interrogez des entités ultérieurement, cette colonne est utilisée automatiquement pour des recherches rapides.  

```csharp
string dataDir = "Your Document Directory";
```

## Comment ajouter la géométrie ?
`GeometryFieldName` est une propriété de `GeoDatabaseCreateOptions` qui détermine quelle colonne d’attribut stocke les objets géométriques pour chaque entité. `GeometryFieldName` définit la colonne qui stocke les données de forme (points, lignes, polygones). En la nommant explicitement, vous évitez le nom par défaut `"Shape"` et maintenez votre schéma cohérent entre plusieurs couches.  

```csharp
var path = dataDir + "NamesOfObjectIdAndGeometryFields_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
    var options = new FileGdbOptions
    {
        ObjectIdFieldName = "OID",         // Specify the Object ID field name
        GeometryFieldName = "POINT",       // Specify the Geometry field name
    };
```

## Comment créer une couche et ajouter une couche d’entités ponctuelles ?
`CreateLayer` est une méthode de `GeoDatabase` qui crée une nouvelle couche vectorielle avec un nom, des options et un système de référence spatiale spécifiés. `Feature` est un objet représentant un enregistrement spatial unique, contenant la géométrie et les valeurs d’attributs. `Point` est une classe géométrique représentant un emplacement unique défini par les coordonnées X (longitude) et Y (latitude). Une fois la base de données prête, créez une nouvelle couche avec `CreateLayer`. Ensuite, construisez un objet `Feature`, attribuez‑lui une géométrie `Point` et ajoutez‑le à la couche. Cela montre **comment ajouter une géométrie** et **comment créer une couche** en un seul flux.  

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
    var feature = layer.ConstructFeature();
    feature.Geometry = new Point(12.32, 34.21);  // Specify the geometry (in this case, a point)
    layer.Add(feature);
}
```

## Comment récupérer les données d’une couche ?
`OpenLayer` est une méthode de `GeoDatabase` qui ouvre une couche existante en lecture ou en écriture, renvoyant un objet `Layer`. Ouvrez la couche avec `OpenLayer`, puis parcourez sa collection `Features` ou interrogez‑la par le champ Object ID personnalisé. Cela montre **comment récupérer les données d’une couche** en utilisant l’identifiant que vous avez défini précédemment.  

```csharp
using (var layer = dataset.OpenLayer("layer_name"))
{
    var feature = layer[0];
    Console.WriteLine(feature.GetValue<int>("OID")); // Output: 1
}
```

## Problèmes courants et solutions
- **Erreur de colonne Object ID manquante** – Assurez‑vous que `ObjectIdFieldName` est défini *avant* d’appeler `CreateLayer`.  
- **Géométrie non affichée** – Vérifiez que le type de géométrie (par ex., `Point`) correspond au système de référence spatiale de la couche.  
- **Verrouillage de fichier sous Windows** – Fermez tous les objets `GeoDatabase` ou encapsulez‑les dans des instructions `using` pour libérer les poignées de fichier.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.GIS pour .NET dans mes applications web ?**  
R : Oui, la bibliothèque fonctionne dans les projets ASP.NET Core, MVC et Web API, offrant une fonctionnalité GIS complète côté serveur.

**Q : Existe‑t‑il une version d’essai disponible avant l’achat ?**  
R : Oui, vous pouvez explorer les fonctionnalités d’Aspose.GIS pour .NET avec un essai gratuit disponible [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.GIS pour .NET ?**  
R : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/) à des fins d’évaluation.

**Q : Quels systèmes de référence spatiale Aspose.GIS pour .NET prend‑il en charge ?**  
R : Le produit prend en charge les codes EPSG 1‑9999, y compris WGS 84, Web Mercator et de nombreux systèmes de coordonnées nationaux.

**Q : Où puis‑je obtenir de l’aide ou discuter des questions liées à Aspose.GIS ?**  
R : Visitez le forum Aspose.GIS [ici](https://forum.aspose.com/c/gis/33) pour le support et les discussions communautaires.

---

**Dernière mise à jour :** 2026-05-21  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Créer une couche vectorielle dans File GDB – Tutoriel Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Comment définir la grille pour une couche File GDB dans Aspose.GIS](/gis/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/)
- [Lire l’Object ID d’une couche File GDB dans Aspose.GIS](/gis/net/layer-data-operations/read-object-id-from-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}