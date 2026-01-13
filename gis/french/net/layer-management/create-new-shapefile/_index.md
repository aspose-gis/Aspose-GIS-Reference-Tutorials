---
date: 2026-01-13
description: Apprenez à créer un nouveau shapefile avec Aspose.GIS pour .NET. Ce guide
  étape par étape vous montre comment définir une couche vectorielle, ajouter un attribut
  de date et gérer les données spatiales.
linktitle: Create New Shapefile
second_title: Aspose.GIS .NET API
title: Créer un nouveau shapefile
url: /fr/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un nouveau Shapefile

## Introduction
Si vous vous plongez dans le développement de systèmes d'information géographique (SIG) avec .NET, Aspose.GIS est votre solution de référence. Cette bibliothèque puissante permet aux développeurs de travailler de manière fluide avec des données spatiales, et dans ce tutoriel, nous vous guiderons pour **créer un nouveau shapefile** à l'aide d'Aspose.GIS pour .NET. Vous verrez pourquoi la définition d'une couche vectorielle et l'ajout d'un attribut date sont des étapes essentielles pour des projets SIG robustes.

## Quick Answers
- **Qu'enseigne ce tutoriel ?** Comment créer un nouveau shapefile, définir une couche vectorielle et ajouter des attributs (y compris un champ date).  
- **Quelle bibliothèque est requise ?** Aspose.GIS pour .NET.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour l’apprentissage ; une licence commerciale est requise pour la production.  
- **Quel IDE dois‑je utiliser ?** Visual Studio (toute version récente).  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour l’exemple de base.

## Prerequisites
Avant de commencer le tutoriel, assurez‑vous d’avoir les prérequis suivants :
- Une compréhension de base du langage de programmation C#.
- Visual Studio installé sur votre machine.
- La bibliothèque Aspose.GIS pour .NET. Vous pouvez la télécharger [ici](https://releases.aspose.com/gis/net/).

## Import Namespaces
Commencez par importer les espaces de noms nécessaires pour exploiter les fonctionnalités d’Aspose.GIS :

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Set Up Your Project
Commencez par créer un nouveau projet C# dans Visual Studio et incluez la bibliothèque Aspose.GIS.

## Step 2: Define the Document Directory
```csharp
string dataDir = "Your Document Directory";
```
Remplacez *Your Document Directory* par le chemin réel où vous souhaitez enregistrer votre nouveau shapefile.

## Step 3: Create a VectorLayer
```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```
Ce segment de code **définit une couche vectorielle** et déclare trois attributs : un champ texte (`name`), un champ entier (`age`) et un champ date‑heure (`dob`). L’ajout de l’attribut date est crucial pour les analyses SIG temporelles.

## Step 4: Add Features
### Case 1: Sets Values Individually
```csharp
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
firstFeature.SetValue("dob", new DateTime(1982, 2, 5, 16, 30, 0));
layer.Add(firstFeature);
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
secondFeature.SetValue("dob", new DateTime(1984, 12, 15, 15, 30, 0));
layer.Add(secondFeature);
```
Ici nous créons deux points, définissons chaque attribut séparément et ajoutons les entités à la couche.

### Case 2: Sets New Values for All Attributes
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Dans cette approche, nous remplissons toutes les valeurs d’attributs en un seul appel à l’aide d’un tableau d’objets — pratique lorsqu’il y a de nombreux attributs.

## Why This Matters
Créer un shapefile de façon programmatique vous permet d’automatiser les pipelines de données, de générer des jeux de données de test ou d’intégrer directement la sortie SIG dans des services web. En maîtrisant **comment créer un shapefile** avec Aspose.GIS, vous obtenez un contrôle complet sur la géométrie des entités, le schéma des attributs et la conformité du format de fichier.

## Common Pitfalls & Tips
- **Séparateurs de chemin :** Utilisez `Path.Combine` pour garantir la compatibilité multiplateforme au lieu de concaténer des chaînes.  
- **Ordre des attributs :** L’ordre des valeurs dans `SetValues` doit correspondre à l’ordre dans lequel vous avez ajouté les attributs.  
- **Gestion des dates :** Utilisez toujours `DateTimeKind.Utc` si vos données SIG seront partagées entre différents fuseaux horaires.

## Conclusion
Félicitations ! Vous avez créé avec succès un nouveau shapefile à l’aide d’Aspose.GIS pour .NET. Ce tutoriel a couvert les bases de la configuration de votre projet, de la définition d’une couche vectorielle et de l’ajout d’entités — y compris un attribut date. Au fur et à mesure de votre exploration, consultez la [documentation](https://reference.aspose.com/gis/net/) pour découvrir les fonctionnalités avancées et les possibilités supplémentaires.

## Frequently Asked Questions
### Q: Puis‑je utiliser Aspose.GIS avec d’autres langages de programmation ?
Aspose.GIS prend principalement en charge .NET, mais des versions sont également disponibles pour Java.

### Q: Un essai gratuit est‑il disponible ?
Oui, vous pouvez accéder à l’essai gratuit [ici](https://releases.aspose.com/).

### Q: Où puis‑je trouver du support pour Aspose.GIS ?
Visitez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le support communautaire et les discussions.

### Q: Comment obtenir une licence temporaire ?
Obtenez votre licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Q: Où puis‑je acheter Aspose.GIS pour .NET ?
Vous pouvez acheter la bibliothèque [ici](https://purchase.aspose.com/buy).

---

**Dernière mise à jour :** 2026-01-13  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}