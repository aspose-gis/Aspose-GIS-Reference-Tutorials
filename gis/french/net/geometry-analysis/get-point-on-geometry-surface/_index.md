---
date: 2025-12-09
description: Apprenez comment vérifier si un point se trouve à l'intérieur d'un polygone
  avec Aspose.GIS pour .NET. Guide étape par étape pour obtenir un point sur la surface,
  créer un polygone en C# et récupérer le point sur le polygone.
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

# Vérifier si un point est à l'intérieur d'un polygone et obtenir un point sur la surface

## Introduction
Dans ce tutoriel, vous apprendrez **comment vérifier si un point est à l'intérieur d'un polygone** avec Aspose.GIS for .NET et vous verrez également comment **obtenir un point sur la surface** d’une géométrie. Nous parcourrons la création d’un polygone en C#, la récupération d’un point qui se trouve sur la surface du polygone, et la vérification que le point réside réellement à l’intérieur du polygone. À la fin, vous disposerez d’un extrait prêt à l’emploi que vous pourrez intégrer dans n’importe quelle application géospatiale .NET.

## Quick Answers
- **Que signifie « check point inside polygon » ?** Cela vérifie si une coordonnée donnée se trouve à l’intérieur des limites d’une géométrie polygone.  
- **Quelle méthode renvoie un point à l’intérieur d’un polygone ?** `GetPointOnSurface()` renvoie un point garanti d’être à l’intérieur du polygone.  
- **Ai‑je besoin d’une licence pour exécuter l’exemple ?** Un essai gratuit suffit pour l’évaluation ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework, .NET Core et .NET Standard sont tous compatibles.  
- **Combien de temps prend l’implémentation ?** Environ 5‑10 minutes pour copier, compiler et exécuter.

## Prerequisites
Avant de commencer, assurez‑vous de disposer de ce qui suit :

### Environment Setup
1. Installez Aspose.GIS for .NET : téléchargez et installez la bibliothèque Aspose.GIS for .NET depuis [here](https://releases.aspose.com/gis/net/).  
2. Configurez votre environnement de développement : assurez‑vous d’avoir un environnement de développement fonctionnel pour la programmation .NET. Si ce n’est pas le cas, vous pouvez installer Visual Studio ou tout autre environnement .NET de votre choix.  
3. Connaissances de base en C# : familiarisez‑vous avec les bases du langage C# si vous ne les maîtrisez pas déjà.  
4. Accès à la documentation : gardez la [documentation](https://reference.aspose.com/gis/net/) à portée de main pour vous y référer tout au long du tutoriel.

## Import Namespaces
Avant de plonger dans l’implémentation, commençons par importer les espaces de noms nécessaires :

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Maintenant que nous avons configuré notre environnement et importé les espaces de noms requis, décomposons l’exemple en plusieurs étapes pour mieux le comprendre.

## How to Create Polygon C#  
Tout d’abord, nous devons **créer un polygone**. Nous définissons la boucle extérieure du polygone en spécifiant ses sommets.

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

## How to Get Point on Surface  
Ensuite, nous récupérons un point sur la surface du polygone à l’aide de la méthode `GetPointOnSurface()`. Il s’agit de l’étape **get point on surface**.

```csharp
IPoint pointOnSurface = polygon.GetPointOnSurface();
```

## How to Check Point Inside Polygon  
Nous pouvons vérifier si le point récupéré se trouve à l’intérieur du polygone en utilisant la méthode `SpatiallyContains()`. Cela montre **retrieving point on polygon** puis la vérification.

```csharp
Console.WriteLine(polygon.SpatiallyContains(pointOnSurface)); // True
```

## Common Issues and Solutions
- **Polygone vide** – Assurez‑vous que la boucle extérieure possède au moins trois sommets distincts ; sinon `GetPointOnSurface()` peut renvoyer un point indéfini.  
- **Horaire vs. anti‑horaire** – L’orientation de la boucle n’affecte pas la vérification d’appartenance, mais garder un ordre de rotation cohérent facilite d’autres opérations spatiales.  
- **Système de coordonnées** – L’exemple utilise un plan cartésien simple ; lorsque vous travaillez avec des coordonnées du monde réel, veillez à ce que le CRS (système de référence de coordonnées) soit correctement défini.

## Conclusion
Dans ce tutoriel, nous avons appris comment **check point inside polygon** avec Aspose.GIS for .NET, obtenir un **point on surface**, et vérifier son appartenance. Avec Aspose.GIS, la gestion des données géospatiales devient efficace et simple, permettant aux développeurs de créer des applications géospatiales robustes.

## FAQ's
### Aspose.GIS est‑il compatible avec d’autres frameworks .NET ?
Oui, Aspose.GIS prend en charge divers frameworks .NET, notamment .NET Framework, .NET Core et .NET Standard.

### Puis‑je essayer Aspose.GIS avant d’acheter ?
Oui, vous pouvez télécharger une version d’essai gratuite d’Aspose.GIS depuis [here](https://releases.aspose.com/).

### Comment obtenir du support pour Aspose.GIS ?
Vous pouvez visiter le forum Aspose.GIS [here](https://forum.aspose.com/c/gis/33) pour demander de l’aide et interagir avec d’autres utilisateurs et développeurs.

### Aspose.GIS propose‑t‑il des licences temporaires ?
Oui, vous pouvez obtenir des licences temporaires pour Aspose.GIS depuis [here](https://purchase.aspose.com/temporary-license/).

### Où puis‑je acheter Aspose.GIS ?
Vous pouvez acheter Aspose.GIS sur la page d’achat [here](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** Quelle est la meilleure façon de gérer de grands ensembles de données de polygones ?  
**A:** Chargez les géométries de façon paresseuse et réutilisez une seule instance de `GeometryFactory` pour réduire la consommation de mémoire.

**Q:** Puis‑je récupérer plusieurs points sur la surface ?  
**A:** `GetPointOnSurface()` renvoie un seul point intérieur. Pour générer plusieurs points intérieurs, vous pouvez utiliser un générateur de points aléatoires à l’intérieur de la boîte englobante du polygone et tester chacun avec `SpatiallyContains()`.

**Q:** Est‑il possible d’exporter le polygone vers un shapefile après sa création ?  
**A:** Oui, Aspose.GIS fournit les classes `FeatureSet` et `ShapefileWriter` pour écrire des géométries au format Shapefile.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose