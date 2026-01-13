---
date: 2026-01-13
description: Apprenez comment ajouter une couche à un jeu de données File GDB en utilisant
  Aspose.GIS, avec prise en charge du système de référence spatiale WGS84. Suivez
  ce guide étape par étape pour ajouter une couche à un GDB en .NET.
linktitle: Add Layer to File GDB Dataset
second_title: Aspose.GIS .NET API
title: référence spatiale wgs84 – Ajouter une couche à GDB avec Aspose.GIS
url: /fr/net/layer-management/add-layer-to-file-gdb-dataset/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# spatial reference wgs84 – Ajouter une couche à GDB avec Aspose.GIS

## Introduction
Prêt à améliorer votre flux de travail GIS avec Aspose.GIS pour .NET ? Dans ce tutoriel, vous apprendrez **comment ajouter une couche à un jeu de données File GDB** tout en travaillant avec le système de coordonnées **spatial reference wgs84**. Nous parcourrons chaque étape, de la préparation de votre dossier de données à la validation de la couche nouvellement créée, afin que vous puissiez commencer à manipuler les données géographiques en toute confiance.

## Quick Answers
- **Quel est le système de coordonnées principal utilisé ?** spatial reference wgs84 (WGS 84)  
- **Quelle bibliothèque fournit l'API ?** Aspose.GIS for .NET  
- **Ai-je besoin d'une licence pour les tests ?** Oui – une licence temporaire Aspose est disponible.  
- **Puis-je ajouter des attributs à la nouvelle couche ?** Absolument, vous pouvez définir n'importe quel nombre d'attributs de caractéristiques.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6.

## What is spatial reference wgs84?
La référence spatiale wgs84 (World Geodetic System 1984) est le système de coordonnées géographiques le plus largement utilisé. Elle définit la latitude et la longitude en degrés et sert de CRS par défaut pour de nombreux jeux de données GIS, y compris celui que nous créerons dans ce guide.

## Why use Aspose.GIS to add a layer?
- **Aucune dépendance externe :** Fonctionne immédiatement avec du code .NET pur.  
- **Contrôle total du schéma :** Vous pouvez définir des attributs personnalisés et des types de géométrie.  
- **Multi‑plateforme :** Compatible avec les environnements d'exécution Windows, Linux et macOS.  
- **Licence robuste :** Les licences temporaires vous permettent d'évaluer rapidement avant de vous engager.

## Prerequisites
Avant de commencer, assurez‑vous d'avoir :

- Bibliothèque Aspose.GIS pour .NET : Téléchargez et installez la bibliothèque depuis la [Documentation Aspose.GIS pour .NET](https://reference.aspose.com/gis/net/).  
- Répertoire de documents : Créez un dossier dédié sur votre machine pour stocker les fichiers GIS.

## Import Namespaces
Ajoutez les instructions `using` requises à votre projet C# afin de pouvoir accéder aux classes Aspose.GIS :

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

## Step 1: Copy Directory
Tout d'abord, dupliquez le dossier contenant le jeu de données GDB original. Conserver une copie protège les données sources pendant que vous expérimentez.

```csharp
string dataDir = "Your Document Directory";
var path = dataDir + "ThreeLayers.gdb";
var datasetPath = "Your Document Directory" + "AddLayerToFileGdbDataset_out.gdb";
RunExamples.CopyDirectory(path, datasetPath);
```

## Step 2: Open Dataset and Verify Creation Capability
Ouvrez le jeu de données fraîchement copié et confirmez qu'il peut créer de nouvelles couches. La propriété `CanCreateLayers` doit renvoyer **True**.

```csharp
using (var dataset = Dataset.Open(datasetPath, Drivers.FileGdb))
{
    Console.WriteLine(dataset.CanCreateLayers); // True
```

## Step 3: Create and Populate a New Layer with spatial reference wgs84
Nous créons maintenant une couche nommée **data** et définissons explicitement sa référence spatiale sur **Wgs84**. Nous ajoutons également un attribut simple appelé **Name** et insérons une entité ponctuelle.

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

## Step 4: Open and Validate the Added Layer
Enfin, ouvrez la couche que vous venez de créer et vérifiez son contenu. La console affichera que la couche contient une entité et que l'attribut **Name** correspond à ce que nous avons défini.

```csharp
using (var layer = dataset.OpenLayer("data"))
{
    Console.WriteLine(layer.Count); // 1
    Console.WriteLine(layer[0].GetValue<string>("Name")); // "Name_1"
}
```

## Common Issues & Tips
- **Chemin incorrect :** Assurez‑vous que `dataDir` se termine par un séparateur de chemin (`/` ou `\`) afin que les chaînes concaténées forment des chemins de fichiers valides.  
- **Erreurs de licence :** Si vous voyez des avertissements de licence, appliquez une licence temporaire depuis le portail Aspose avant d'exécuter le code.  
- **Incohérence de CRS :** Lors de l'ouverture de la couche plus tard dans un autre outil GIS, vérifiez que l'outil reconnaît WGS 84 (EPSG:4326) comme système de coordonnées.

## Frequently Asked Questions
### Q: Can I use Aspose.GIS for .NET with other GIS libraries?
Aspose.GIS pour .NET est conçu pour fonctionner de manière autonome, mais il peut être intégré à d'autres bibliothèques pour des fonctionnalités supplémentaires.

### Q: Is a temporary license available for testing purposes?
Oui, vous pouvez obtenir une licence temporaire depuis [ici](https://purchase.aspose.com/temporary-license/) pour les tests et l'évaluation.

### Q: What spatial reference systems does Aspose.GIS for .NET support?
Aspose.GIS pour .NET prend en charge un large éventail de systèmes de référence spatiale, offrant une flexibilité dans la gestion des données géographiques.

### Q: Can I contribute to the Aspose.GIS community?
Absolument ! Rejoignez les discussions et partagez vos expériences sur le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### Q: Where can I find detailed documentation for Aspose.GIS for .NET?
Explorez la documentation complète [ici](https://reference.aspose.com/gis/net/) pour des informations détaillées sur Aspose.GIS pour .NET.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-01-13  
**Testé avec :** Aspose.GIS for .NET (latest stable version)  
**Auteur :** Aspose