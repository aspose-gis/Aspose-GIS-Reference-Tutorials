---
date: 2026-06-10
description: Apprenez comment ajouter des points et ajouter des coordonnées à une
  forme tout en parcourant la géométrie à l'aide d'Aspose.GIS for .NET, la puissante
  boîte à outils GIS pour les développeurs .NET.
keywords:
- how to add points
- add coordinates to shape
- Aspose.GIS geometry
linktitle: Comment ajouter des points et itérer sur la géométrie en .NET
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  headline: How to Add Points and Iterate Over Geometry in .NET
  type: TechArticle
- description: Learn how to add points and add coordinates to shape while iterating
    over geometry using Aspose.GIS for .NET, the powerful GIS toolkit for .NET developers.
  name: How to Add Points and Iterate Over Geometry in .NET
  steps:
  - name: Create a `LineString` object
    text: '`LineString` is Aspose.GIS''s geometry type that represents an ordered
      collection of points forming a polyline.'
  - name: Add points to the `LineString`
    text: The `AddPoint` method inserts a new vertex (longitude, latitude) at the
      end of the line. Call it repeatedly to **add coordinates to shape** objects.
  - name: Iterate over the points
    text: '`LineString` implements `IEnumerable<IPoint>`, allowing you to loop through
      each point with a `foreach` statement. This makes extracting X (longitude) and
      Y (latitude) values trivial. The loop prints each point’s X (longitude) and
      Y (latitude) values to the console, allowing you to verify that the p'
  type: HowTo
- questions:
  - answer: '`LineString`'
    question: What is the primary class for point collections?
  - answer: Use `AddPoint(longitude, latitude)`
    question: How do you add a point?
  - answer: Yes, `LineString` implements `IEnumerable<IPoint>`
    question: Can you iterate with a foreach loop?
  - answer: .NET 6+ (or .NET Core 3.1/Framework 4.6+) and Aspose.GIS for .NET library
    question: Prerequisites?
  - answer: Building routes, visualizing tracks, or preprocessing data for spatial
      analysis
    question: Typical use case?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Comment ajouter des points et itérer sur la géométrie en .NET
url: /fr/net/geometry-processing/iterate-over-points-in-geometry/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter des points et parcourir la géométrie en .NET

## Introduction

Si vous travaillez avec des données SIG dans un environnement .NET, l’une des premières choses à connaître est **comment ajouter des points** à une géométrie puis travailler avec ces points. Aspose.GIS for .NET fournit une API propre, orientée objet, qui rend ce processus simple. Dans ce tutoriel, nous allons créer un `LineString`, y ajouter des points et parcourir ces points afin d’extraire les coordonnées ou d’effectuer d’autres analyses. Vous verrez également comment **ajouter des coordonnées aux objets shape** de manière efficace.

## Réponses rapides
- **Quelle est la classe principale pour les collections de points ?** `LineString`
- **Comment ajouter un point ?** Utilisez `AddPoint(longitude, latitude)`
- **Peut‑on parcourir avec une boucle foreach ?** Oui, `LineString` implémente `IEnumerable<IPoint>`
- **Prérequis ?** .NET 6+ (ou .NET Core 3.1/Framework 4.6+) et la bibliothèque Aspose.GIS for .NET
- **Cas d’utilisation typique ?** Construction d’itinéraires, visualisation de traces, ou prétraitement de données pour l’analyse spatiale  
- **IPoint** représente une géométrie point unique avec des coordonnées X (longitude) et Y (latitude).

## Qu’est‑ce que « ajouter des points » en SIG ?

Ajouter des points signifie insérer des paires de coordonnées individuelles (longitude, latitude) dans un conteneur géométrique tel qu’un `LineString`, `Polygon` ou `MultiPoint`. Chaque point devient un sommet qui définit la forme ou le chemin que vous modélisez, permettant des opérations spatiales et des visualisations. Ces sommets peuvent ensuite être accédés pour des analyses, exportés vers divers formats SIG, ou utilisés dans des calculs spatiaux tels que la mesure de distance ou les tests d’intersection.

## Pourquoi ajouter des points avec Aspose.GIS ?

Vous ajoutez des points avec Aspose.GIS parce que la bibliothèque garantit **une gestion de la géométrie sûre au niveau du typage**, prend en charge **plus de 30 formats vectoriels et raster**, et peut traiter **des jeux de données de plusieurs centaines de pages** sans charger le fichier complet en mémoire. L’API offre également une itération intégrée, des opérations spatiales et la conversion de formats (Shapefile, GeoJSON, KML, etc.) sur chaque plateforme prise en charge.

## Prérequis

- Visual Studio 2022 (ou tout IDE C#)  
- Package NuGet Aspose.GIS for .NET installé  
- Connaissances de base de la syntaxe C#  

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

Vous ajoutez des points en créant une instance de `LineString`, en appelant sa méthode `AddPoint` pour chaque paire de coordonnées, puis en parcourant la collection lorsque nécessaire. Ce schéma en trois étapes couvre la création, le peuplement et le parcours de manière concise et lisible. **LineString est un type de géométrie représentant une collection ordonnée de points formant une polyligne.** Cette approche garantit que la géométrie reste valide et prête pour d’autres opérations spatiales telles que le calcul de longueur ou l’exportation.

### Étape 1 : Créer un objet `LineString`  

`LineString` est le type de géométrie d’Aspose.GIS qui représente une collection ordonnée de points formant une polyligne.

```csharp
LineString line = new LineString();
```

### Étape 2 : Ajouter des points au `LineString`  

La méthode `AddPoint` insère un nouveau sommet (longitude, latitude) à la fin de la ligne. Appelez‑la de façon répétée pour **ajouter des coordonnées aux objets shape**.

```csharp
line.AddPoint(78.65, -32.65);
line.AddPoint(-98.65, 12.65);
```

### Étape 3 : Parcourir les points  

`LineString` implémente `IEnumerable<IPoint>`, ce qui vous permet de boucler sur chaque point avec une instruction `foreach`. Cela rend l’extraction des valeurs X (longitude) et Y (latitude) triviale.

```csharp
foreach (IPoint point in line)
{
    Console.WriteLine(point.X + "," + point.Y);
}
```

La boucle affiche les valeurs X (longitude) et Y (latitude) de chaque point dans la console, vous permettant de vérifier que les points ont été ajoutés correctement.

## Cas d’utilisation courants

- **Planification d’itinéraires** – Construisez un chemin à partir de journaux GPS puis analysez les distances entre les points de passage.  
- **Validation de données** – Parcourez les points pour vous assurer qu’ils se situent dans les limites attendues (par ex., à l’intérieur des frontières d’un pays).  
- **Visualisation** – Exportez le `LineString` vers GeoJSON ou Shapefile pour l’utiliser dans des outils de cartographie.

## Foire aux questions

**Q1 : Aspose.GIS for .NET peut‑il gérer d’autres formes géométriques que `LineString` ?**  
R : Oui, Aspose.GIS prend en charge `Point`, `Polygon`, `MultiLineString`, `MultiPolygon` et de nombreux autres types de géométrie.

**Q2 : Aspose.GIS convient‑il aux projets commerciaux et personnels ?**  
R : Absolument. Les options de licence couvrent les usages commerciaux, personnels et éducatifs.

**Q3 : Aspose.GIS for .NET propose‑t‑il une documentation complète pour les débutants ?**  
R : Oui, le produit comprend une documentation exhaustive, des références API et des dizaines d’exemples de code pour vous aider à démarrer rapidement.

**Q4 : Puis‑je étendre les fonctionnalités d’Aspose.GIS for .NET par du développement personnalisé ?**  
R : Vous pouvez créer des méthodes d’extension ou encapsuler les classes Aspose.GIS pour les adapter à des flux de travail spécifiques, vous offrant un contrôle total sur des solutions géospatiales personnalisées.

**Q5 : Un support technique est‑il disponible pour les utilisateurs d’Aspose.GIS ?**  
R : Un support technique dédié est fourni via les forums Aspose et le système de tickets, garantissant une assistance rapide.

---

**Dernière mise à jour :** 2026-06-10  
**Testé avec :** Aspose.GIS for .NET 24.5 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [How to Count Points in Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/count-points-in-geometry/)
- [How to Add Point to LineString and Convert Geometry to Editable Format with Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [Create MultiPoint Geometry with Aspose.GIS for .NET](/gis/net/geometry-creation/create-multipoint-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}