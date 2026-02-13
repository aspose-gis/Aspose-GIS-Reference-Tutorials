---
date: 2026-02-13
description: Apprenez à vérifier si un point se trouve à l'intérieur d'un polygone
  avec Aspose.GIS pour .NET, à créer une géométrie de polygone et à obtenir un point
  sur la surface en C#. Guide étape par étape avec un exemple de code complet.
linktitle: Check Point Inside Polygon and Get Point on Surface
second_title: Aspose.GIS .NET API
title: Vérifier si un point est à l'intérieur d'un polygone et obtenir le point sur
  la surface
url: /fr/net/geometry-analysis/get-point-on-geometry-surface/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vérifier si un point se trouve à l'intérieur d'un polygone et obtenir un point sur la surface

## Introduction
Dans ce tutoriel, vous apprendrez **comment vérifier si un point se trouve à l'intérieur d'un polygone** avec Aspose.GIS pour .NET et vous verrez également comment **obtenir un point sur la surface** d'une géométrie. Nous parcourrons la création d'une géométrie de polygone en C#, la récupération d'un point qui se trouve sur la surface du polygone, et la vérification que le point réside réellement à l'intérieur du polygone. À la fin, vous disposerez d'un extrait prêt à l'emploi que vous pourrez intégrer dans n'importe quelle application géospatiale .NET.

## Quick Answers
- **Que signifie « vérifier si un point se trouve à l'intérieur d'un polygone » ?** Cela vérifie si une coordonnée donnée se situe à l'intérieur des limites d'une géométrie de polygone.  
- **Quelle méthode renvoie un point à l'intérieur d'un polygone ?** `GetPointOnSurface()` renvoie un point garanti d'être à l'intérieur du polygone.  
- **Ai‑je besoin d'une licence pour exécuter l'exemple ?** Un essai gratuit suffit pour l'évaluation ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework, .NET Core et .NET Standard sont tous compatibles.  
- **Combien de temps prend l'implémentation ?** Environ 5‑10 minutes pour copier, compiler et exécuter.

## What is “check point inside polygon”?
Vérifier un point à l'intérieur d'un polygone est une opération spatiale fondamentale. Elle répond à la question « Cette coordonnée se situe-t-elle dans la zone définie par le polygone ? ». Ceci est essentiel pour des tâches telles que le géorepérage, l'analyse cartographique et la validation spatiale.

## Why use Aspose.GIS for this task?
Aspose.GIS fournit une API entièrement gérée, haute performance, qui gère les opérations géométriques complexes sans dépendances externes. Elle prend en charge un large éventail de systèmes de référence de coordonnées, fonctionne sur tous les principaux environnements d'exécution .NET, et offre des méthodes claires et chaînables comme `SpatiallyContains()` et `GetPointOnSurface()`.

## Prerequisites
Avant de commencer, assurez‑vous de disposer de ce qui suit :

### Environment Setup
1. Installez Aspose.GIS pour .NET : téléchargez et installez la bibliothèque Aspose.GIS pour .NET depuis [here](https://releases.aspose.com/gis/net/).  
2. Configurez votre environnement de développement : assurez‑vous de disposer d'un environnement de développement fonctionnel pour la programmation .NET. Sinon, vous pouvez installer Visual Studio ou tout autre environnement de développement .NET de votre choix.  
3. Connaissances de base en C# : familiarisez‑vous avec les bases du langage de programmation C# si ce n'est pas déjà le cas.  
4. Accès à la documentation : gardez la [documentation](https://reference.aspose.com/gis/net/) à portée de main pour vous y référer tout au long du tutoriel.

## Import Namespaces
Avant de plonger dans l'implémentation, commençons par importer les espaces de noms nécessaires :

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step‑by‑Step Guide

### Step 1: Create Polygon Geometry in C#
#### Étape 1 : Créer une géométrie de polygone en C#
Tout d'abord, nous devons **créer une géométrie de polygone**. Nous définissons la boucle extérieure du polygone en spécifiant ses sommets.

```csharp
var polygon = new Polygon();
polygon.ExteriorRing = new LinearRing(new[]
{
    new Point(0, 0),
    new Point(0, 1),
    new Point(1, 1),
    new Point(0, 0),
});
```

### Step 2: Get Point on Surface
#### Étape 2 : Obtenir un point sur la surface
Ensuite, nous récupérons un point sur la surface du polygone à l'aide de la méthode `GetPointOnSurface()`. Il s'agit de l'étape **obtenir un point sur la surface**.

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

### Step 3: Check Point Inside Polygon
#### Étape 3 : Vérifier si le point se trouve à l'intérieur du polygone
Nous pouvons vérifier si le point récupéré se situe à l'intérieur du polygone en utilisant la méthode `SpatiallyContains()`. Cela montre **la récupération du point sur le polygone** puis sa vérification.

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## Common Issues and Solutions
- **Polygone vide** – Assurez‑vous que la boucle extérieure possède au moins trois sommets distincts ; sinon `GetPointOnSurface()` peut renvoyer un point indéfini.  
- **Sens horaire vs. anti‑horaire** – L'orientation de la boucle n'affecte pas la vérification de contenance, mais garder un ordre de rotation cohérent facilite d'autres opérations spatiales.  
- **Système de coordonnées** – L'exemple utilise un simple plan cartésien ; lors de l'utilisation de coordonnées réelles, assurez‑vous que le CRS (système de référence de coordonnées) est correctement défini.

## Frequently Asked Questions

### FAQ's
#### Aspose.GIS est‑il compatible avec d'autres frameworks .NET ?
Oui, Aspose.GIS prend en charge divers frameworks .NET, y compris .NET Framework, .NET Core et .NET Standard.

#### Puis‑je essayer Aspose.GIS avant d'acheter ?
Oui, vous pouvez télécharger un essai gratuit d'Aspose.GIS depuis [here](https://releases.aspose.com/).

#### Comment obtenir du support pour Aspose.GIS ?
Vous pouvez visiter le forum Aspose.GIS [here](https://forum.aspose.com/c/gis/33) pour demander de l'aide et interagir avec d'autres utilisateurs et développeurs.

#### Aspose.GIS propose‑t‑il des licences temporaires ?
Oui, vous pouvez obtenir des licences temporaires pour Aspose.GIS depuis [here](https://purchase.aspose.com/temporary-license/).

#### Où puis‑je acheter Aspose.GIS ?
Vous pouvez acheter Aspose.GIS sur la page d'achat [here](https://purchase.aspose.com/buy).

### Additional Q&A

**Q:** Quelle est la meilleure façon de gérer de grands ensembles de données de polygones ?  
**R:** Chargez les géométries de façon paresseuse et réutilisez une seule instance de `GeometryFactory` pour réduire la consommation de mémoire.

**Q:** Puis‑je récupérer plusieurs points sur la surface ?  
**R:** `GetPointOnSurface()` renvoie un seul point intérieur. Pour générer plusieurs points intérieurs, vous pouvez utiliser un générateur de points aléatoires à l'intérieur de la boîte englobante du polygone et tester chacun avec `SpatiallyContains()`.

**Q:** Est‑il possible d'exporter le polygone vers un shapefile après sa création ?  
**R:** Oui, Aspose.GIS fournit les classes `FeatureSet` et `ShapefileWriter` pour écrire des géométries au format Shapefile.

## Conclusion
Dans ce tutoriel, nous avons appris comment **vérifier si un point se trouve à l'intérieur d'un polygone** avec Aspose.GIS pour .NET, obtenir un **point sur la surface**, et vérifier sa contenance. Avec Aspose.GIS, la gestion des données géospatiales devient efficace et simple, permettant aux développeurs de créer des applications géospatiales robustes.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}