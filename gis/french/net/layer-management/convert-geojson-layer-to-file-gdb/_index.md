---
date: 2026-06-20
description: Apprenez comment convertir geojson en gdb avec Aspose.GIS pour .NET.
  Ce guide pas à pas couvre la lecture de GeoJSON en C#, la création d'une File Geodatabase
  et la gestion des problèmes courants.
keywords:
- convert geojson to gdb
- how to convert geojson
- read geojson c#
- asp.net geojson conversion
linktitle: Convertir la couche GeoJSON en GDB
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to convert geojson to gdb with Aspose.GIS for .NET. This
    step‑by‑step guide covers reading GeoJSON in C#, creating a File Geodatabase,
    and handling common issues.
  headline: How to Convert GeoJSON to GDB Using Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Converting a GeoJSON layer to a GDB with Aspose.GIS for .NET.
    question: What does this guide teach?
  - answer: '*convert geojson to gdb*.'
    question: Which primary keyword is targeted?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Supported .NET versions?
  - answer: Roughly 10‑15 minutes for a basic conversion.
    question: Implementation time?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Comment convertir GeoJSON en GDB avec Aspose.GIS pour .NET
url: /fr/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment convertir GeoJSON en GDB à l'aide d'Aspose.GIS pour .NET

## Introduction
Si vous cherchez à **convert geojson to gdb** rapidement et de manière fiable, vous êtes au bon endroit. Ce tutoriel vous guide à travers chaque étape — depuis la lecture d'un fichier GeoJSON en C# jusqu'à la création d'une File Geodatabase (GDB) avec Aspose.GIS. Vous découvrirez pourquoi Aspose.GIS est une bibliothèque privilégiée pour la conversion de données géospatiales, comment configurer l'environnement, et comment exécuter la conversion en quelques minutes seulement.

## Réponses rapides
- **Que couvre ce guide ?** Conversion d'une couche GeoJSON en GDB avec Aspose.GIS pour .NET.  
- **Quel mot‑clé principal est ciblé ?** *convert geojson to gdb*.  
- **Ai‑je besoin d'une licence ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Versions .NET prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Temps d'implémentation ?** Environ 10‑15 minutes pour une conversion de base.

## Qu'est‑ce que GeoJSON et File GDB ?
GeoJSON est un format léger, basé sur du texte, pour les entités géographiques, tandis que File GDB est une géodatabase ESRI haute performance basée sur des dossiers.  
GeoJSON stocke les points, lignes et polygones sous forme de texte brut, ce qui facilite le partage et la modification, alors que File GDB conserve les données dans des fichiers binaires offrant des requêtes spatiales rapides et une gestion robuste des attributs. Ensemble, ils couvrent à la fois les échanges adaptés au web et le traitement GIS de bureau à haute vitesse.

## Pourquoi utiliser Aspose.GIS pour la conversion de données géospatiales ?
Aspose.GIS fournit une API unique et cohérente qui masque les particularités propres à chaque format. Elle prend en charge **plus de 30 formats géospatiaux**, peut traiter des fichiers jusqu'à **2 GB** sans charger l'intégralité du jeu de données en mémoire, et préserve automatiquement les systèmes de référence de coordonnées. Cela signifie que vous passez moins de temps à écrire des analyseurs et plus de temps à développer la logique de votre application.

## Prérequis
- Familiarité avec C# et la structure d'un projet .NET.  
- Aspose.GIS pour .NET installé. Si vous ne l'avez pas encore installé, téléchargez-le depuis [here](https://releases.aspose.com/gis/net/) et suivez le guide d'installation. Vous pouvez également explorer d'autres produits Aspose à [here](https://releases.aspose.com/).

## Importer les espaces de noms
La première étape consiste à importer les espaces de noms requis dans la portée.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Comment lire un GeoJSON en C# ?
Chargez le fichier GeoJSON avec la classe `GeoJsonReader`, qui analyse le JSON et crée une `FeatureCollection` en mémoire. Le lecteur détecte automatiquement le système de référence de coordonnées, vous n'avez donc pas besoin de gérer manuellement l'analyse du CRS. Il prend également en charge le streaming de gros fichiers, la préservation des types d'attributs, et peut être combiné avec des transformations géométriques personnalisées si nécessaire.

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```

## Étape 1 : Configurer la couche GeoJSON
Créez un fichier GeoJSON temporaire contenant les attributs et les entités que vous souhaitez convertir. Cet exemple ajoute deux entités ponctuelles simples.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Étape 2 : Copier le jeu de données de test
Pour ne pas altérer les données de test originales, dupliquez le jeu de données File GDB existant. Cela garantit un environnement propre pour la conversion.

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## Étape 3 : Convertir GeoJSON en GDB
`FileGdb` représente un conteneur de File Geodatabase et fournit des méthodes pour gérer les couches. Ouvrez la couche GeoJSON, créez une nouvelle couche dans le File GDB copié, copiez les attributs et transférez chaque entité. C'est le cœur du processus de **conversion Aspose.GIS**.

CODE_BLOCK_PLACEHOLDER_4_END

## Comment convertir GeoJSON en GDB ?
Chargez le GeoJSON avec `GeoJsonReader`, créez une instance d'objet `FileGdb` pointant vers votre dossier de destination, créez une nouvelle couche d'entités, puis parcourez chaque entité pour l'insérer. En pratique, il s'agit d'un flux en trois étapes — lire, créer, copier — qui se termine en moins d'une minute pour des jeux de données typiques.

## Problèmes courants et solutions
- **Référence spatiale manquante :** Assurez‑vous que le GeoJSON source inclut une définition CRS ou définissez explicitement `SpatialReferenceSystem.Wgs84` lors de la création de la couche GDB.  
- **Incohérence de type d'attribut :** Les types de données des attributs dans le GeoJSON doivent correspondre au schéma cible ; sinon, Aspose.GIS lèvera une exception.  
- **Erreurs d'accès aux fichiers :** Vérifiez que le dossier de destination possède les permissions d'écriture et qu'aucun autre processus ne verrouille les fichiers GDB.

## Questions fréquemment posées
### Aspose.GIS est‑il compatible avec le dernier framework .NET ?
Oui, Aspose.GIS fonctionne avec .NET Framework 4.5+, .NET Core 3.1+, .NET 5 et .NET 6+.

### Puis‑je convertir d'autres formats géospatiaux avec Aspose.GIS ?
Absolument ! Aspose.GIS prend en charge plus de 30 formats d'entrée et de sortie, y compris Shapefile, KML, GML et SQLite.

### Existe‑t‑il une version d'essai disponible pour Aspose.GIS ?
Oui, vous pouvez explorer les fonctionnalités d'Aspose.GIS en téléchargeant la version d'essai [here](https://releases.aspose.com/).

### Comment obtenir du support pour les questions liées à Aspose.GIS ?
Rendez‑vous sur le [forum](https://forum.aspose.com/c/gis/33) Aspose.GIS pour obtenir une assistance dédiée de la communauté et de l'équipe produit.

### Puis‑je obtenir une licence temporaire pour Aspose.GIS ?
Oui, vous pouvez obtenir une licence temporaire [here](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2026-06-20  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un jeu de données File Geodatabase .NET avec Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Lire les entités d'une File Geodatabase dans Aspose.GIS](/gis/net/layer-data-operations/read-features-from-file-geodatabase/)
- [Créer une couche vecteur dans File GDB – Tutoriel Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}