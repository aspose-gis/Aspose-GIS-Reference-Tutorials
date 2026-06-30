---
date: 2026-06-30
description: Apprenez comment créer un shapefile avec Aspose.GIS for .NET. Ce guide
  étape par étape vous montre comment définir une couche vectorielle, ajouter un attribut
  de date et gérer les données spatiales efficacement.
keywords:
- how to create shapefile
- temporal gis shapefile
- Aspose.GIS vector layer
- GIS data automation
linktitle: Créer un nouveau shapefile
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create shapefile using Aspose.GIS for .NET. This step‑by‑step
    guide shows you how to define a vector layer, add a date attribute, and manage
    spatial data efficiently.
  headline: How to Create Shapefile with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Aspose.GIS primarily supports .NET, but there are versions available for
      Java as well.
    question: Can I use Aspose.GIS with other programming languages?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      support and discussions.
    question: Where can I find support for Aspose.GIS?
  - answer: Get your temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license?
  - answer: You can buy the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Comment créer un shapefile avec Aspose.GIS for .NET
url: /fr/net/layer-management/create-new-shapefile/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un nouveau Shapefile

## Introduction
Si vous vous plongez dans le développement de systèmes d'information géographique (SIG) avec .NET, Aspose.GIS est votre solution de référence pour **comment créer un shapefile** de manière programmatique. Cette bibliothèque vous offre un contrôle complet sur les couches vectorielles, les schémas d'attributs et la conformité aux formats de fichiers, vous permettant d'automatiser les pipelines de données ou de générer des jeux de données de test en quelques minutes.

## Réponses rapides
- **Quel est l'objectif de ce tutoriel ?** Comment créer un nouveau shapefile, définir une couche vectorielle et ajouter des attributs (y compris un champ de date).  
- **Quelle bibliothèque est requise ?** Aspose.GIS pour .NET.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour l’apprentissage ; une licence commerciale est requise pour la production.  
- **Quel IDE dois‑je utiliser ?** Visual Studio (toute version récente).  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour l’exemple de base.

## Comment créer un shapefile avec Aspose.GIS pour .NET ?
Chargez la bibliothèque Aspose.GIS, définissez le dossier de sortie, créez un `VectorLayer`, définissez les attributs et ajoutez des entités — tout ce flux de travail peut être écrit en moins de 30 lignes de C#. La bibliothèque gère automatiquement la création de géométrie, le typage des attributs et l’écriture du fichier, vous n’avez donc pas à gérer les spécifications bas‑niveau du Shapefile vous‑même.

## Prérequis
Avant de commencer le tutoriel, assurez‑vous d’avoir les prérequis suivants :
- Bonne compréhension du langage de programmation C#.  
- Visual Studio installé sur votre machine.  
- Bibliothèque Aspose.GIS pour .NET. Vous pouvez la télécharger [here](https://releases.aspose.com/gis/net/).

## Importer les espaces de noms
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

## Étape 1 : Configurer votre projet
Commencez par créer un nouveau projet C# dans Visual Studio et incluez la bibliothèque Aspose.GIS.

## Étape 2 : Définir le répertoire du document
```csharp
string dataDir = "Your Document Directory";
```
Remplacez *Your Document Directory* par le chemin réel où vous souhaitez enregistrer votre nouveau shapefile.

## Étape 3 : Créer un VectorLayer
La classe `VectorLayer` représente une couche shapefile unique qui stocke la géométrie et les données d’attributs.  
Dans cette étape, nous définissons une couche vectorielle et déclarons trois attributs : un champ texte (`name`), un champ entier (`age`) et un champ date‑heure (`dob`). L’ajout de l’attribut date est crucial pour les analyses de **temporal GIS shapefile**.

```csharp
using (VectorLayer layer = VectorLayer.Create(dataDir + "NewShapeFile_out.shp", Drivers.Shapefile))
{
    // add attributes before adding features
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    layer.Attributes.Add(new FeatureAttribute("dob", AttributeDataType.DateTime));
```

## Étape 4 : Ajouter des entités
### Cas 1 : Définit les valeurs individuellement
La méthode `SetValues` assigne les valeurs d’attribut à une entité dans l’ordre où elles ont été définies.  
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
Ici, nous créons deux points, définissons chaque attribut séparément et ajoutons les entités à la couche.

### Cas 2 : Définit de nouvelles valeurs pour tous les attributs
Alternativement, vous pouvez fournir toutes les valeurs d’attribut en une seule fois en utilisant `SetValues` avec un tableau d’objets.  
```csharp
Feature thirdFeature = layer.ConstructFeature();
thirdFeature.Geometry = new Point(34.81, -92.28);
object[] data = new object[3] { "Alex", 25, new DateTime(1989, 4, 15, 15, 30, 0) };
thirdFeature.SetValues(data);
layer.Add(thirdFeature);
}
```
Dans cette approche, nous remplissons toutes les valeurs d’attribut en un appel unique à l’aide d’un tableau d’objets — pratique lorsque vous avez de nombreux attributs.

## Pourquoi est‑ce important ?
Créer un shapefile de façon programmatique vous permet d’automatiser les pipelines de données, de générer des jeux de données de test ou d’intégrer directement les sorties SIG dans des services web. Aspose.GIS prend en charge **plus de 30 formats vectoriels et raster** et peut écrire des shapefiles de plusieurs centaines de pages sans charger le fichier complet en mémoire, offrant à la fois rapidité et évolutivité.

## Pièges courants et astuces
- **Séparateurs de chemin :** Utilisez `Path.Combine` pour la compatibilité multiplateforme au lieu de la concaténation de chaînes.  
- **Ordre des attributs :** L’ordre des valeurs dans `SetValues` doit correspondre à l’ordre dans lequel vous avez ajouté les attributs.  
- **Gestion des dates :** Utilisez toujours `DateTimeKind.Utc` si vos données SIG seront partagées entre différents fuseaux horaires.

## Conclusion
Félicitations ! Vous avez créé avec succès un nouveau shapefile en utilisant Aspose.GIS pour .NET. Ce tutoriel a couvert les bases de la configuration de votre projet, de la définition d’une couche vectorielle et de l’ajout d’entités—including un attribut date. Au fur et à mesure que vous explorez davantage, consultez la [documentation](https://reference.aspose.com/gis/net/) pour les fonctionnalités avancées et les possibilités supplémentaires.

## Questions fréquemment posées
**Q : Puis‑je utiliser Aspose.GIS avec d’autres langages de programmation ?**  
R : Aspose.GIS prend principalement en charge .NET, mais des versions sont également disponibles pour Java.

**Q : Une version d’essai gratuite est‑elle disponible ?**  
R : Oui, vous pouvez accéder à l’essai gratuit [here](https://releases.aspose.com/).

**Q : Où puis‑je trouver du support pour Aspose.GIS ?**  
R : Visitez le [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) pour le support communautaire et les discussions.

**Q : Comment obtenir une licence temporaire ?**  
R : Obtenez votre licence temporaire [here](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je acheter Aspose.GIS pour .NET ?**  
R : Vous pouvez acheter la bibliothèque [here](https://purchase.aspose.com/buy).

**Dernière mise à jour :** 2026-06-30  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Obtenir les attributs de couche – Récupérer les informations d'attribut de couche avec Aspose.GIS pour .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Créer une couche vectorielle et définir le système de référence spatiale de la couche](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Créer une couche vectorielle dans un fichier GDB – Tutoriel Aspose.GIS .NET](/gis/net/layer-management/create-file-gdb-with-single-layer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}