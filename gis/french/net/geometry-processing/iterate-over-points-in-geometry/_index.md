---
date: 2025-12-20
description: Apprenez à ajouter des points et à parcourir la géométrie en utilisant
  Aspose.GIS pour .NET, la puissante boîte à outils GIS pour les développeurs .NET.
linktitle: How to Add Points and Iterate Over Geometry in .NET
second_title: Aspose.GIS .NET API
title: Comment ajouter des points et parcourir la géométrie en .NET
url: /fr/net/geometry-processing/iterate-over-points-in-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter des points et itérer sur une géométrie

## Introduction

Si vous travaillez avec des données SIG dans un environnement .NET, l’une des premières choses à connaître est **comment ajouter des points** à une géométrie puis travailler avec ces points. Aspose.GIS for .NET propose une API orientée objet claire qui rend ce processus simple. Dans ce tutoriel, nous allons créer un `LineString`, y ajouter des points et itérer sur ces points afin d’extraire les coordonnées ou d’effectuer d’autres analyses.

## Réponses rapides
- **Quelle est la classe principale pour les collections de points ?** `LineString`
- **Comment ajouter un point ?** Utilisez `AddPoint(longitude, latitude)`
- **Peut‑on itérer avec une boucle foreach ?** Oui, `LineString` implémente `IEnumerable<IPoint>`
- **Prérequis ?** .NET 6+ (ou .NET Core 3.1/Framework 4.6+) et la bibliothèque Aspose.GIS for .NET
- **Cas d’utilisation typique ?** Construction d’itinéraires, visualisation de traces, ou prétraitement de données pour l’analyse spatiale

## Qu’est‑ce que « l’ajout de points » en SIG ?

Ajouter des points signifie insérer des paires de coordonnées individuelles (longitude, latitude) dans un conteneur géométrique tel qu’un `LineString`, `Polygon` ou `MultiPoint`. Chaque point devient un sommet qui définit la forme ou le tracé que vous modélisez.

## Pourquoi ajouter des points avec Aspose.GIS ?

- **Sécurité de type forte** – les objets géométriques sont fortement typés, ce qui réduit les erreurs d’exécution.  
- **Multiplateforme** – fonctionne sur .NET Framework, .NET Core et .NET 5/6+.  
- **API riche** – itération intégrée, opérations spatiales et prise en charge de formats (Shapefile, GeoJSON, etc.).

## Prérequis

- Visual Studio 2022 (ou tout IDE C#)  
- Package NuGet Aspose.GIS for .NET installé  
- Connaissances de base en syntaxe C#  

## Importer les espaces de noms

Commencez par importer les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.GIS dans votre application .NET :

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Comment ajouter des points à une géométrie ?

### Étape 1 : Créer un objet `LineString`  

Un `LineString` représente une séquence de points connectés (une polyligne). Tout d’abord, instanciez l’objet :

```csharp
LineString line = new LineString();
```

### Étape 2 : Ajouter des points au `LineString`  

Utilisez la méthode `AddPoint` pour insérer chaque paire de coordonnées. C’est le cœur de **comment ajouter des points** à votre géométrie :

```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

Vous pouvez appeler `AddPoint` autant de fois que nécessaire ; chaque appel ajoute un nouveau sommet à la ligne.

### Étape 3 : Itérer sur les points  

Une fois les points ajoutés, vous pouvez les parcourir avec une instruction `foreach`. Le `LineString` implémente `IEnumerable<IPoint>`, rendant l’itération simple et intuitive :

```csharp
foreach (IPoint point in line)
{
    Console.WriteLine(point.X + "," + point.Y);
}
```

La boucle affiche les valeurs X (longitude) et Y (latitude) de chaque point dans la console, vous permettant de vérifier que les points ont bien été ajoutés.

## Cas d’utilisation courants

- **Planification d’itinéraires** – Construisez un tracé à partir de journaux GPS puis analysez les distances entre les points de passage.  
- **Validation de données** – Parcourez les points pour vous assurer qu’ils se situent dans les limites attendues (par ex., à l’intérieur des frontières d’un pays).  
- **Visualisation** – Exportez le `LineString` en GeoJSON ou Shapefile pour l’utiliser dans des outils de cartographie.

## Foire aux questions

### Q1 : Aspose.GIS for .NET peut‑il gérer d’autres formes géométriques que le `LineString` ?

**R :** Oui, Aspose.GIS prend en charge `Point`, `Polygon`, `MultiLineString`, `MultiPolygon` et de nombreux autres types géométriques.

### Q2 : Aspose.GIS convient‑il aux projets commerciaux et personnels ?

**R :** Absolument. Les options de licence couvrent les usages commerciaux, personnels et éducatifs.

### Q3 : Aspose.GIS for .NET propose‑t‑il une documentation complète pour les débutants ?

**R :** Oui, le produit comprend une documentation exhaustive, des références API et des dizaines’exemples de code pour vous aider à démarrer rapidement.

### Q4 : Puis‑je étendre les fonctionnalités d’Aspose.GIS for .NET par du développement personnalisé ?

**R :** Vous pouvez créer des méthodes d’extension encapsuler les classes Aspose.GIS pour les adapter à des flux de travail spécifiques, vous offrant ainsi un contrôle total sur vos solutions géospatiales personnalisées.

### Q5 : Un support technique est‑il disponible pour les utilisateurs d’Aspose.GIS ?

**R :** Un support technique dédié est fourni via les forums Aspose et le système de tickets, garantissant une assistance rapide.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2025-12-20  
**Testé avec :** Aspose.GIS for .NET 24.5 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

---