---
date: 2025-12-03
description: Apprenez à comparer des géométries avec Aspose.GIS pour .NET et à vérifier
  l’égalité des géométries dans vos applications .NET.
language: fr
linktitle: How to Compare Geometries for Equality
second_title: Aspose.GIS .NET API
title: Comment comparer des géométries pour l’égalité en utilisant Aspose.GIS pour
  .NET
url: /net/geometry-analysis/check-geometries-for-equality/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment comparer des géométries pour l'égalité avec Aspose.GIS pour .NET

## Introduction
Dans ce tutoriel, vous découvrirez **comment comparer des géométries** avec Aspose.GIS pour .NET. Que vous construisiez un service de cartographie, effectuiez une analyse spatiale, ou ayez simplement besoin de vérifier que deux formes représentent le même emplacement, savoir comment comparer des géométries est essentiel. Nous parcourrons un exemple complet, de bout en bout, qui vous montre comment créer, modifier et tester l'égalité des géométries en quelques lignes de code C#.

## Quick Answers
- **Que signifie « comparer des géométries » ?** Cela vérifie si deux objets géométriques occupent le même espace, quel que soit leur mode de construction.  
- **Quelle méthode est utilisée ?** `SpatiallyEquals` de l'API Aspose.GIS.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Versions .NET prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Temps d'implémentation typique ?** Environ 5‑10 minutes pour une vérification d'égalité basique.

## What is Geometry Equality?
L'égalité de géométrie (souvent appelée égalité spatiale) signifie que deux géométries représentent exactement le même ensemble de points à la surface de la Terre. Deux formes peuvent être construites différemment — un MultiLineString versus un seul LineString — mais être néanmoins spatialement égales.

## Why Use Aspose.GIS to Compare Geometries?
Aspose.GIS fournit un moteur de géométrie robuste et haute performance qui :
- Gère une large gamme de formats vectoriels (WKT, GeoJSON, Shapefile, etc.).
- Propose des méthodes de comparaison sensibles à la précision comme `SpatiallyEquals`.
- Fonctionne hors ligne, sans services externes, ce qui le rend idéal pour des environnements sécurisés ou isolés.

## Prerequisites
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- **.NET Framework ou .NET Core installé** – toute version prise en charge par Aspose.GIS.
- **Bibliothèque Aspose.GIS pour .NET** – téléchargez depuis la [page de téléchargement Aspose.GIS](https://releases.aspose.com/gis/net/).
- **Un IDE de développement** – Visual Studio, Rider ou VS Code avec extensions C#.

## Import Namespaces
Dans votre projet .NET, ajoutez les instructions `using` requises afin que le compilateur sache où trouver les classes GIS :

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Step 1: Define the Geometries
### Étape 1 : définir les géométries
Tout d'abord, nous créons deux géométries que nous allons comparer. Dans cet exemple, `geometry1` est un `MultiLineString` composé de deux segments de ligne, tandis que `geometry2` est un seul `LineString` qui couvre les mêmes points de départ et d'arrivée.

```csharp
var geometry1 = new MultiLineString
{
    new LineString(new [] { new Point(0, 0), new Point(1, 1) }),
    new LineString(new [] { new Point(1, 1), new Point(2, 2) }),
};
var geometry2 = new LineString(new[]
{
    new Point(0, 0), new Point(2, 2),
});
```

## Step 2: Check Geometries for Equality
### Étape 2 : vérifier l'égalité des géométries
Nous utilisons maintenant la méthode `SpatiallyEquals` pour voir si les deux formes sont considérées comme égales par le moteur GIS.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // True
```

La console affiche `True` parce que, malgré la construction différente, les deux géométries couvrent la même ligne de (0,0) à (2,2).

## Step 3: Modify One Geometry
### Étape 3 : modifier une géométrie
Pour illustrer comment une modification affecte l'égalité, nous ajoutons un point supplémentaire à `geometry2`.

```csharp
geometry2.AddPoint(3, 3);
```

## Step 4: Re‑check Equality After Modification
### Étape 4 : revérifier l'égalité après modification
Après la modification, les géométries ne sont plus identiques, donc `SpatiallyEquals` renvoie `False`.

```csharp
Console.WriteLine(geometry1.SpatiallyEquals(geometry2)); // False
```

Le résultat `False` confirme que le point supplémentaire a rompu l'égalité spatiale.

## Common Issues & Tips
### Problèmes courants et astuces
- **Problèmes de précision** – Si vous travaillez avec des coordonnées très précises, envisagez d'arrondir ou d'utiliser une surcharge avec tolérance de `SpatiallyEquals`.  
- **SRID différents** – Assurez-vous que les deux géométries partagent le même Spatial Reference System Identifier (SRID) avant la comparaison.  
- **Performance** – Pour de grandes collections, les comparaisons par lots avec LINQ peuvent réduire la surcharge.

## Frequently Asked Questions
### Questions fréquentes
**Q : Puis‑je utiliser Aspose.GIS pour .NET avec d’autres frameworks .NET ?**  
R : Oui, Aspose.GIS fonctionne avec les projets .NET Framework, .NET Core et .NET Standard.

**Q : Une version d’essai gratuite est‑elle disponible ?**  
R : Absolument. Téléchargez une version d’essai depuis la [page des versions Aspose.GIS](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation complète de l’API ?**  
R : La documentation détaillée se trouve sur la [page de documentation Aspose.GIS](https://reference.aspose.com/gis/net/).

**Q : Comment obtenir de l’aide en cas de problème ?**  
R : Publiez votre question sur le forum communautaire Aspose.GIS [ici](https://forum.aspose.com/c/gis/33).

**Q : Puis‑je acheter une licence temporaire pour l’évaluation ?**  
R : Oui, des licences temporaires sont disponibles sur la [page d’achat](https://purchase.aspose.com/temporary-license/).

## Conclusion
Vous savez maintenant **comment comparer des géométries** avec Aspose.GIS pour .NET, de la création des objets à la vérification de l'égalité spatiale et la gestion des modifications. Cette capacité constitue une base pour des analyses spatiales plus avancées telles que la validation de topologie, la détection de doublons et le filtrage basé sur la géométrie.

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.GIS for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}