---
date: 2026-06-30
description: Apprenez comment ajouter une couche à un jeu de données File GDB en utilisant
  Aspose.GIS avec la référence spatiale WGS84. Suivez ce guide étape par étape pour
  ajouter une couche en .NET.
keywords:
- how to add layer
- spatial reference wgs84
- Aspose.GIS .NET
- File GDB dataset
linktitle: Ajouter une couche à un jeu de données File GDB
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to add layer to a File GDB dataset using Aspose.GIS with
    spatial reference WGS84. Follow this step‑by‑step guide to add a layer in .NET.
  headline: How to Add Layer to File GDB Dataset with spatial reference WGS84 using
    Aspose.GIS
  type: TechArticle
- questions:
  - answer: spatial reference wgs84 (WGS 84)
    question: What is the primary coordinate system used?
  - answer: Aspose.GIS for .NET
    question: Which library provides the API?
  - answer: Yes – a temporary Aspose license is available.
    question: Do I need a license for testing?
  - answer: Absolutely, you can define any number of feature attributes.
    question: Can I add attributes to the new layer?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Comment ajouter une couche à un jeu de données File GDB avec la référence spatiale
  WGS84 en utilisant Aspose.GIS
url: /fr/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# comment ajouter une couche – référence spatiale wgs84 avec Aspose.GIS

## Introduction
Prêt à améliorer votre flux de travail GIS avec Aspose.GIS pour .NET ? Dans ce tutoriel, vous apprendrez **comment ajouter une couche** à un jeu de données File GDB tout en travaillant avec le système de coordonnées **référence spatiale WGS84**. Nous parcourrons chaque étape, de la préparation de votre dossier de données à la validation de la couche nouvellement créée, afin que vous puissiez commencer à manipuler les données géographiques en toute confiance et efficacité.

## Réponses rapides
- **Quel est le système de coordonnées principal utilisé ?** spatial reference wgs84 (WGS 84)  
- **Quelle bibliothèque fournit l’API ?** Aspose.GIS for .NET  
- **Ai-je besoin d’une licence pour les tests ?** Yes – a temporary Aspose license is available.  
- **Puis-je ajouter des attributs à la nouvelle couche ?** Absolutely, you can define any number of feature attributes.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## Qu’est‑ce que la référence spatiale wgs84 ?
La référence spatiale wgs84 (World Geodetic System 1984) est le système de coordonnées géographiques le plus largement utilisé. Elle définit la latitude et la longitude en degrés et sert de CRS par défaut pour de nombreux jeux de données GIS, y compris celui que nous créerons dans ce guide.

## Pourquoi utiliser Aspose.GIS pour ajouter une couche ?
Chargez vos données GIS sans binaires tiers et conservez un contrôle total sur la définition du schéma. Aspose.GIS prend en charge **plus de 40 systèmes de référence spatiale**, peut traiter des fichiers de plus de **2 Go** sans charger l’ensemble du jeu de données en mémoire, et fonctionne sous Windows, Linux et macOS. Cela en fait une solution fiable, multiplateforme, pour l’automatisation GIS de niveau entreprise.

## Pré‑requis
- Bibliothèque Aspose.GIS pour .NET : téléchargez et installez la bibliothèque depuis la [Aspose.GIS for .NET Documentation](https://reference.aspose.com/gis/net/).  
- Répertoire de documents : créez un dossier dédié sur votre machine pour stocker les fichiers GIS.  
- Une licence temporaire Aspose (optionnelle pour l’évaluation) – voir la FAQ ci‑dessous pour le lien de téléchargement.

## Importer les espaces de noms
Ajoutez les instructions `using` requises à votre projet C# afin de pouvoir accéder aux classes Aspose.GIS :

*Aucun bloc de code n’est requis ici ; ajoutez simplement les lignes suivantes en haut de votre fichier :*

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.Geometries.Collections;
using Aspose.Gis.SpatialReference;
```

## Étape 1 : Copier le répertoire
**Definition anchor:** Un jeu de données File GDB est une géodatabase ESRI basée sur un dossier qui stocke les données spatiales dans un ensemble de fichiers.  
Tout d'abord, dupliquez le dossier contenant le jeu de données GDB original. Conserver une copie protège les données sources pendant que vous expérimentez.

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

## Étape 2 : Ouvrir le jeu de données et vérifier la capacité de création
`Dataset` représente une collection de couches GIS stockées dans un File GDB. Ouvrez le jeu de données nouvellement copié et confirmez qu’il peut créer de nouvelles couches. La propriété `CanCreateLayers` doit renvoyer **True**. **`CanCreateLayers` est une propriété booléenne indiquant si le jeu de données prend en charge la création de nouvelles couches.**

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Étape 3 : Créer et remplir une nouvelle couche avec la référence spatiale wgs84
Nous créons maintenant une couche nommée **data** et définissons explicitement sa référence spatiale sur **Wgs84**. Nous ajoutons également un attribut simple appelé **Name** et insérons une entité ponctuelle. **`CreateLayer` crée une nouvelle couche dans le jeu de données avec le nom et la référence spatiale spécifiés.** **`SpatialReference` représente le système de coordonnées utilisé par une couche.** **`Feature` est un objet géographique individuel (point, ligne ou polygone) stocké dans une couche.**

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Étape 4 : Ouvrir et valider la couche ajoutée
Enfin, ouvrez la couche que vous venez de créer et vérifiez son contenu. La console affichera que la couche contient une entité et que l’attribut **Name** correspond à ce que nous avons défini. **`Layer.Open` ouvre une couche existante pour la lecture ou la modification.** Cela confirme que la couche a été ajoutée correctement et que la référence spatiale est WGS84.

```csharp
using (var layer = dataset.CreateLayer("data", SpatialReferenceSystem.Wgs84))
{
    layer.Attributes.Add(new FeatureAttribute("Name", AttributeDataType.String));
    var feature = layer.ConstructFeature();
    feature.SetValue("Name", "Name_1");
    feature.Geometry = new Point(12.21, 23.123, 20, -200);
    layer.Add(feature);
}
```

## Comment ajouter une couche à un jeu de données File GDB ?
Chargez le jeu de données, appelez `CreateLayer` avec le nom et la référence spatiale souhaités, définissez le schéma des attributs, puis insérez les entités. Tout cela peut être réalisé avec quelques appels de méthodes Aspose.GIS, et l’API gère automatiquement le verrouillage des fichiers et la validation du schéma. Le processus garantit que la nouvelle couche respecte la référence spatiale du jeu de données, que les définitions d’attributs sont stockées dans le schéma de la couche, et que les données peuvent être accessibles par tout logiciel GIS prenant en charge le File GDB.

## Problèmes courants et astuces
- **Chemin incorrect :** Assurez‑vous que `dataDir` se termine par un séparateur de chemin (`/` ou `\`) afin que les chaînes concaténées forment des chemins de fichier valides.  
- **Erreurs de licence :** Si vous voyez des avertissements de licence, appliquez une licence temporaire depuis le portail Aspose avant d’exécuter le code.  
- **Incohérence de CRS :** Lors de l’ouverture de la couche plus tard dans un autre outil GIS, confirmez que l’outil reconnaît WGS 84 (EPSG:4326) comme système de coordonnées.  
- **Jeux de données volumineux :** Pour les jeux de données dépassant 1 Go, envisagez d’utiliser `Dataset.OpenReadOnly` afin de réduire la consommation de mémoire.

## Questions fréquentes
### Q : Puis‑je utiliser Aspose.GIS pour .NET avec d’autres bibliothèques GIS ?
R : Oui, Aspose.GIS fonctionne de manière indépendante mais peut être combiné avec des bibliothèques telles que GDAL ou NetTopologySuite pour un traitement avancé.

### Q : Une licence temporaire est‑elle disponible à des fins de test ?
R : Oui, vous pouvez obtenir une licence temporaire depuis [ici](https://purchase.aspose.com/temporary-license/) pour les tests et l’évaluation.

### Q : Quels systèmes de référence spatiale Aspose.GIS pour .NET prend‑il en charge ?
R : Aspose.GIS prend en charge plus de **40 codes EPSG**, y compris des systèmes populaires comme WGS84 (EPSG:4326), Web Mercator (EPSG:3857) et NAD83 (EPSG:4269). Explorez la documentation complète [ici](https://reference.aspose.com/gis/net/).

### Q : Puis‑je contribuer à la communauté Aspose.GIS ?
R : Absolument ! Rejoignez les discussions et partagez vos expériences sur le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### Q : Où puis‑je trouver la documentation détaillée d’Aspose.GIS pour .NET ?
R : Explorez la documentation complète [ici](https://reference.aspose.com/gis/net/) pour des informations détaillées sur toutes les classes, méthodes et bonnes pratiques.

---

**Dernière mise à jour :** 2026-06-30  
**Testé avec :** Aspose.GIS for .NET (latest stable version)  
**Auteur :** Aspose

{{< blocks/products/products-backtop-button >}}

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Tutoriels associés

- [Créer un jeu de données File Geodatabase .NET avec Aspose.GIS](/gis/net/layer-management/create-new-file-gdb-dataset/)
- [Créer une couche vectorielle dans File GDB – Tutoriel Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)
- [Créer un jeu de données File GDB et définir les tolérances pour une couche](/gis/net/layer-data-operations/set-tolerances-for-file-gdb-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}