---
date: 2026-08-03
description: Apprenez à créer une linestring c# avec Aspose.GIS pour .NET, à ajouter
  des points à une linestring et à effectuer une vérification point sur ligne à l’aide
  de la méthode covers.
keywords:
- create linestring c#
- point on line check
- add points to linestring
- use covers method
lastmod: 2026-08-03
linktitle: Créer une linestring c# – Vérifier qu’une géométrie couvre une autre
og_description: Créer une linestring c# et vérifier le point sur ligne à l’aide de
  la méthode covers d’Aspose.GIS. Apprenez les vérifications géométriques précises
  pour les applications .NET. (150‑160 chars)
og_image_alt: Developer guide showing linestring creation and covers check in C# with
  Aspose.GIS
og_title: Créer une linestring c# – Vérifier qu’une géométrie couvre une autre (50‑60
  chars)
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  headline: Create linestring c# – Check geometry covers another
  type: TechArticle
- description: Learn how to create linestring c# with Aspose.GIS for .NET, add points
    to a linestring, and perform a point on line check using the covers method.
  name: Create linestring c# – Check geometry covers another
  steps:
  - name: create a linestring object
    text: The `LineString` class represents a sequence of points connected by straight
      line segments in a two‑dimensional plane. Here, we instantiate a new `LineString`
      object, which represents a sequence of connected line segments in a two‑dimensional
      space.
  - name: add points to linestring
    text: '`AddPoint` appends a coordinate pair to the end of the `LineString` collection,
      preserving the order of insertion. We **add points to linestring** using the
      `AddPoint` method. In this example, we add two points: (0, 0) and (1, 1), forming
      a simple diagonal line segment.'
  - name: create a point object
    text: The `Point` class models a single location in a two‑dimensional coordinate
      system. Instantiate a `Point` object representing a single point in a two‑dimensional
      space. Here, we create a point at coordinates (0, 0).
  - name: perform a point on line check – does the line cover the point?
    text: '`Covers` determines whether the first geometry completely contains the
      second geometry, returning true only when every point of the second geometry
      lies inside the first. Use the `Covers` method to check if the line covers the
      point. In this case, it returns `True` because the point (0, 0) lies exac'
  - name: verify the reverse relationship – is the point covered by the line?
    text: '`CoveredBy` is the inverse of `Covers`; it returns true when the invoking
      geometry is entirely inside the target geometry. Similarly, use the `CoveredBy`
      method to check if the point is covered by the line. Since the point (0, 0)
      lies on the line, it also returns `True`.'
  type: HowTo
- questions:
  - answer: Yes, you can use Aspose.GIS for .NET in both commercial and non‑commercial
      projects after obtaining the appropriate license.
    question: Can I use Aspose.GIS for .NET in my commercial projects?
  - answer: Yes, Aspose.GIS for .NET is compatible with both .NET Framework and .NET
      Core environments.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Yes, Aspose.GIS for .NET supports a wide range of GIS formats including
      Shapefile, GeoJSON, KML, and more.
    question: Does Aspose.GIS for .NET support various GIS formats?
  - answer: Aspose.GIS for .NET is a proprietary library developed by Aspose, so external
      contributions are not accepted. However, you can provide feedback and suggestions
      to improve the library.
    question: Can I contribute to the development of Aspose.GIS for .NET?
  - answer: Updates for Aspose.GIS for .NET are released regularly to introduce new
      features, enhancements, and bug fixes. Check the [website](https://releases.aspose.com/gis/net/)
      for the latest releases.
    question: How often are updates released for Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- create linestring
- Aspose.GIS
- C# geometry analysis
title: Créer une linestring c# – Vérifier qu’une géométrie couvre une autre
url: /fr/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vérifier que la géométrie couvre une autre

## Introduction
Dans ce tutoriel, vous apprendrez **comment créer linestring c#** en utilisant Aspose.GIS pour .NET, ajouter des points à une linestring et effectuer une vérification fiable du **point sur la ligne** avec les méthodes `Covers` et `CoveredBy`. Que vous construisiez un outil de cartographie, réalisiez des analyses spatiales ou ayez simplement besoin de vérifier des relations géométriques, maîtriser ces opérations donnera à votre application la précision dont elle a besoin.

## Réponses rapides
- **Que signifie “create linestring c#” ?** Cela signifie instancier un objet géométrique `LineString` et le remplir avec des points de coordonnées.  
- **Quelle méthode vérifie si un point se trouve sur une ligne ?** Utilisez la méthode `Covers` sur le `LineString` ou `CoveredBy` sur le `Point`.  
- **Ai-je besoin d'une licence pour exécuter l'exemple ?** Une licence temporaire suffit pour l'évaluation ; une licence complète est requise pour la production.  
- **Ce code peut-il être utilisé avec .NET Core ?** Oui, Aspose.GIS prend en charge .NET Framework et .NET Core.  
- **Combien de points puis-je ajouter à une linestring ?** Il n'y a pas de limite stricte ; vous pouvez ajouter autant de points que nécessaire pour votre analyse spatiale.

## Qu'est-ce que create linestring c# ?
Une `LineString` est une forme géométrique composée d'une liste ordonnée de points reliés par des segments de ligne droits. En C# vous la créez en instanciant la classe `LineString` du namespace `Aspose.Gis.Geometries` puis **ajoutez des points à la linestring** à l'aide de la méthode `AddPoint`. Cet objet sert de base à toute analyse spatiale linéaire, telle que la cartographie d'itinéraires ou le traçage de réseaux.

## Pourquoi utiliser Aspose.GIS pour une vérification point sur ligne ?
`Covers` est une méthode prédicat spatiale qui renvoie vrai lorsque la première géométrie contient complètement la seconde géométrie.  
Aspose.GIS fournit une implémentation déterministe et haute précision des prédicats spatiaux. Il prend en charge plus de 50 formats GIS d'entrée et de sortie, peut gérer des réseaux de lignes de plusieurs centaines de kilomètres sans charger l'ensemble du jeu de données en mémoire, et fonctionne sur .NET Framework, .NET Core et .NET 5/6+. L’utilisation de sa méthode `Covers` garantit que les erreurs d’arrondi en virgule flottante sont prises en compte, offrant des résultats fiables de point‑sur‑ligne même dans des scénarios d’entreprise exigeants.

## Prérequis
Avant de plonger dans l’utilisation d’Aspose.GIS pour .NET, assurez‑vous d’avoir les prérequis suivants configurés :

### 1. Installer Visual Studio
Assurez‑vous d’avoir Visual Studio installé sur votre système. Aspose.GIS pour .NET s’intègre parfaitement à Visual Studio, offrant une expérience de développement fluide.

### 2. Obtenir Aspose.GIS pour .NET
Téléchargez la bibliothèque Aspose.GIS pour .NET depuis le [site web](https://releases.aspose.com/gis/net/). Vous pouvez soit télécharger la bibliothèque directement, soit utiliser un gestionnaire de paquets comme NuGet pour l’installer dans votre projet.

### 3. Familiarité avec .NET Framework
Une connaissance de base du framework .NET et du langage de programmation C# est essentielle pour exploiter efficacement Aspose.GIS pour .NET.

### 4. Accès à la documentation et au support
Référez‑vous à la [documentation](https://reference.aspose.com/gis/net/) pour des informations détaillées sur les API et les fonctionnalités d’Aspose.GIS. En cas de problème ou de question, utilisez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour obtenir de l’aide.

### 5. Optionnel : licence temporaire
Si vous explorez Aspose.GIS pour .NET, vous pouvez obtenir une licence temporaire depuis la [page de licence temporaire](https://purchase.aspose.com/temporary-license/) pour évaluer les fonctionnalités de la bibliothèque.

## Importer les espaces de noms
Avant d’utiliser Aspose.GIS pour .NET dans votre projet, vous devez importer les espaces de noms nécessaires :

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Maintenant, décomposons l’exemple fourni en plusieurs étapes afin de comprendre comment **vérifier si une géométrie couvre une autre** en utilisant Aspose.GIS pour .NET.

## Comment créer linestring c# – guide étape par étape
Chargez votre projet, importez les espaces de noms requis, puis suivez les cinq étapes concises ci‑dessous. En quelques lignes de code, vous disposerez d’un objet `LineString`, d’un objet `Point` et de deux vérifications booléennes indiquant si la ligne couvre le point et si le point est couvert par la ligne.

### Étape 1 : créer un objet linestring
La classe `LineString` représente une séquence de points reliés par des segments de ligne droits dans un plan bidimensionnel.  
```csharp
var line = new LineString();
```
Ici, nous instancions un nouvel objet `LineString`, qui représente une séquence de segments de ligne connectés dans un espace bidimensionnel.

### Étape 2 : ajouter des points à la linestring
`AddPoint` ajoute une paire de coordonnées à la fin de la collection `LineString`, en préservant l’ordre d’insertion.  
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
Nous **ajoutons des points à la linestring** à l’aide de la méthode `AddPoint`. Dans cet exemple, nous ajoutons deux points : (0, 0) et (1, 1), formant un simple segment diagonal.

### Étape 3 : créer un objet point
La classe `Point` modélise un emplacement unique dans un système de coordonnées bidimensionnel.  
```csharp
var point = new Point(0, 0);
```
Instanciez un objet `Point` représentant un point unique dans un espace bidimensionnel. Ici, nous créons un point aux coordonnées (0, 0).

### Étape 4 : effectuer une vérification point sur ligne – la ligne couvre‑t‑elle le point ?
`Covers` détermine si la première géométrie contient complètement la seconde géométrie, renvoyant vrai uniquement lorsque chaque point de la seconde géométrie se trouve à l’intérieur de la première.  
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Utilisez la méthode `Covers` pour vérifier si la ligne couvre le point. Dans ce cas, elle renvoie `True` car le point (0, 0) se trouve exactement sur la ligne.

### Étape 5 : vérifier la relation inverse – le point est‑il couvert par la ligne ?
`CoveredBy` est l’inverse de `Covers` ; elle renvoie vrai lorsque la géométrie appelante est entièrement à l’intérieur de la géométrie cible.  
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
De même, utilisez la méthode `CoveredBy` pour vérifier si le point est couvert par la ligne. Puisque le point (0, 0) se trouve sur la ligne, elle renvoie également `True`.

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| `line.Covers(point)` renvoie `False` même si le point semble être sur la ligne | Les coordonnées du point ne sont pas exactement les mêmes en raison de la précision des nombres à virgule flottante. | Utilisez `Math.Round` sur les coordonnées ou effectuez une vérification basée sur une tolérance avec `line.Distance(point) < epsilon`. |
| Manque `using Aspose.Gis.Geometries;` | Espace de noms non importé, provoquant des erreurs de compilation. | Assurez‑vous que l’instruction d’importation est présente (voir la section **Importer les espaces de noms**). |
| Exception de licence à l'exécution | Aucune licence valide chargée pour la production. | Chargez une licence temporaire ou complète en utilisant `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.GIS pour .NET dans mes projets commerciaux ?**  
R : Oui, vous pouvez utiliser Aspose.GIS pour .NET dans des projets commerciaux et non commerciaux après avoir obtenu la licence appropriée.

**Q : Ce code est‑il compatible avec .NET Core ?**  
R : Oui, Aspose.GIS pour .NET est compatible à la fois avec .NET Framework et .NET Core.

**Q : Aspose.GIS pour .NET prend‑il en charge divers formats GIS ?**  
R : Oui, Aspose.GIS pour .NET prend en charge un large éventail de formats GIS, notamment Shapefile, GeoJSON, KML, et bien d’autres.

**Q : Puis‑je contribuer au développement d’Aspose.GIS pour .NET ?**  
R : Aspose.GIS pour .NET est une bibliothèque propriétaire développée par Aspose, les contributions externes ne sont donc pas acceptées. Vous pouvez toutefois fournir des retours et suggestions pour améliorer la bibliothèque.

**Q : À quelle fréquence les mises à jour d’Aspose.GIS pour .NET sont‑elles publiées ?**  
R : Les mises à jour d’Aspose.GIS pour .NET sont publiées régulièrement afin d’ajouter de nouvelles fonctionnalités, améliorations et corrections de bugs. Consultez le [site web](https://releases.aspose.com/gis/net/) pour les dernières versions.

## Conclusion
En suivant les étapes ci‑dessus, vous savez maintenant comment **créer linestring c#**, **ajouter des points à la linestring**, et effectuer une vérification fiable du **point sur ligne** à l’aide des méthodes `Covers` et `CoveredBy`. Cette capacité renforce les fonctionnalités d’analyse spatiale de votre logiciel et ouvre la voie à des opérations GIS plus avancées telles que la validation d’itinéraires, la vérification de topologie de réseau et les requêtes de proximité.

---

**Last Updated:** 2026-08-03  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Apprendre à créer une géométrie LineString avec Aspose.GIS pour .NET](/gis/net/geometry-creation/create-linestring-geometry/)
- [Comment ajouter un point à LineString et convertir la géométrie en format éditable avec Aspose.GIS](/gis/net/geometry-creation/convert-geometry-to-editable/)
- [point inside polygon c# – Vérifier que la géométrie contient une autre](/gis/net/geometry-analysis/check-geometry-contains-another/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}