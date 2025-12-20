---
date: 2025-12-20
description: Apprenez à créer une géométrie de polygone avec trou en utilisant Aspose.GIS
  pour .NET. Ce guide vous montre comment créer un trou dans un polygone et travailler
  avec des données géospatiales.
linktitle: Create Polygon with Hole Geometry
second_title: Aspose.GIS .NET API
title: Créer un polygone avec un trou géométrique à l'aide d'Aspose.GIS
url: /fr/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une géométrie de polygone avec trou à l'aide d'Aspose.GIS

## Introduction
Dans ce tutoriel, vous **créerez une géométrie de polygone avec trou** en utilisant Aspose.GIS pour .NET. Que vous développiez une application cartographique, effectuiez une analyse spatiale ou prépariez des données pour des services GIS, savoir comment intégrer un trou à l'intérieur d'un polygone est essentiel. Nous parcourrons l'ensemble du processus étape par étape, depuis la configuration de l'environnement jusqu'à la génération de l'objet polygone final.

## Réponses rapides
- **Que signifie « créer un polygone avec trou » ?** Cela consiste à construire un polygone contenant un ou plusieurs anneaux intérieurs (trous) qui sont exclus de la surface.
- **Quelle bibliothèque gère cela ?** Aspose.GIS pour .NET offre une prise en charge complète des anneaux extérieurs et intérieurs.
- **Ai‑je besoin d’une licence ?** Une version d'essai gratuite suffit pour le développement ; une licence commerciale est requise pour la production.
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Combien de temps cela prend‑il ?** Typiquement moins de 10 minutes pour implémenter et tester.

## Qu’est‑ce que « créer un polygone avec trou » ?
Créer un polygone avec un trou implique de définir un **anneau extérieur** qui délimite la frontière extérieure et un ou plusieurs **anneaux intérieurs** qui découpent des espaces vides. Les anneaux intérieurs sont souvent appelés *trous* car ils représentent des zones qui ne font pas partie de la surface du polygone.

## Pourquoi créer un trou dans un polygone avec Aspose.GIS ?
- **Modélisation spatiale précise** : Des éléments du monde réel comme des lacs à l'intérieur de parcelles ou des cours intérieures de bâtiments nécessitent des trous.
- **Interopérabilité** : Les formats tels que Shapefile, GeoJSON et GML supportent nativement les anneaux intérieurs ; Aspose.GIS les préserve.
- **Performance** : La bibliothèque gère la validité des géométries, vous n’avez donc pas à écrire de code de validation personnalisé.

## Prérequis
Avant de commencer, assurez‑vous de disposer des prérequis suivants :
1. Bibliothèque Aspose.GIS pour .NET : Vous pouvez la télécharger [ici](https://releases.aspose.com/gis/net/).
2. Environnement de développement : Assurez‑vous d’avoir un environnement de développement configuré avec Visual Studio ou tout autre IDE .NET installé.

## Importer les espaces de noms
Tout d’abord, vous devez importer les espaces de noms nécessaires pour travailler avec les fonctionnalités d’Aspose.GIS. Voici comment procéder :

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Passons maintenant à la création d’une géométrie de polygone avec trou en utilisant Aspose.GIS pour .NET.

## Étape 1 : Créer l’objet Polygon
Nous commençons par instancier un objet `Polygon` vide qui contiendra ultérieurement l’anneau extérieur et les anneaux intérieurs.

```csharp
Polygon polygon = new Polygon();
```

## Étape 2 : Définir l’anneau extérieur
L’anneau extérieur définit la frontière extérieure du polygone. Ajoutez les points dans le sens horaire pour former une forme fermée.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Étape 3 : Définir l’anneau intérieur (trou)
Ensuite, nous créons un anneau intérieur — c’est le **trou** qui sera exclu de la surface du polygone. Les points sont généralement ajoutés dans le sens antihoraire, mais Aspose.GIS gère automatiquement l’orientation.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Étape 4 : Assigner l’anneau extérieur et ajouter l’anneau intérieur au polygone
Enfin, attachez l’anneau extérieur au polygone puis ajoutez l’anneau intérieur (le trou). La méthode `AddInteriorRing` peut être appelée plusieurs fois si vous avez besoin de plusieurs trous.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| Le trou n’apparaît pas dans le visualiseur GIS | Orientation de l’anneau intérieur inversée | Assurez‑vous que les points sont ajoutés dans le sens opposé à celui de l’anneau extérieur (antihoraire). |
| Erreur « Polygon invalid » | Anneaux non fermés (premier ≠ dernier point) | Répétez le premier point comme dernier point dans chaque anneau (comme illustré ci‑dessus). |
| Géométrie vide inattendue | Oubli d’assigner `ExteriorRing` avant d’ajouter les anneaux intérieurs | Définissez d’abord `polygon.ExteriorRing`, puis appelez `AddInteriorRing`. |

## Conclusion
Félicitations ! Vous avez appris à **créer une géométrie de polygone avec trou** en utilisant Aspose.GIS pour .NET. Cette technique est fondamentale pour de nombreux scénarios géospatiaux où il faut représenter des formes complexes avec des vides intérieurs.

## Questions fréquentes
### 1. Qu’est‑ce qu’Aspose.GIS ?
Aspose.GIS est une bibliothèque .NET qui permet aux développeurs de travailler avec des données géospatiales, en créant, lisant et manipulant divers formats de fichiers géospatiaux.

### 2. Puis‑je utiliser Aspose.GIS pour des projets commerciaux ?
Oui, vous pouvez utiliser Aspose.GIS pour des projets personnels et commerciaux en achetant une licence. Consultez les détails [ici](https://purchase.aspose.com/buy).

### 3. Existe‑t‑il une version d’essai gratuite d’Aspose.GIS ?
Oui, vous pouvez obtenir une version d’essai gratuite d’Aspose.GIS [ici](https://releases.aspose.com/).

### 4. Où puis‑je trouver du support pour Aspose.GIS ?
Vous pouvez obtenir du support pour Aspose.GIS sur le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Comment obtenir une licence temporaire pour Aspose.GIS ?
Vous pouvez obtenir une licence temporaire pour Aspose.GIS [ici](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2025-12-20  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}