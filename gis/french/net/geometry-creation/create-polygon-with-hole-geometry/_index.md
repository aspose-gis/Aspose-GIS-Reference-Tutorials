---
date: 2026-09-05
description: Apprenez comment créer un polygon interior ring avec un hole en utilisant
  Aspose.GIS pour .NET. Ce guide vous montre comment ajouter un hole à un polygone
  et travailler avec les données.
keywords:
- polygon interior ring
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
lastmod: 2026-09-05
linktitle: Créer Polygon avec Hole Geometry
og_description: Apprenez comment créer un polygon interior ring avec un hole en utilisant
  Aspose.GIS pour .NET. Ce guide vous montre comment ajouter un hole à un polygone
  et travailler avec les données.
og_image_alt: Guide showing how to create a polygon interior ring with a hole using
  Aspose.GIS
og_title: Créer un polygon interior ring avec un hole en utilisant Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-05'
  description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  headline: Create a polygon interior ring with a hole using Aspose.GIS
  type: TechArticle
- description: Learn how to create a polygon interior ring with a hole using Aspose.GIS
    for .NET. This guide shows you how to add a hole to a polygon and work with data.
  name: Create a polygon interior ring with a hole using Aspose.GIS
  steps:
  - name: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
    text: '**Land parcel with an internal lake** – the lake is modeled as a hole so
      it isn’t counted in the parcel’s area.'
  - name: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
    text: '**Building footprints with courtyards** – the courtyard is excluded from
      the building’s footprint.'
  - name: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
    text: '**Protected zones inside a larger conservation area** – you can exclude
      restricted sections without creating separate layers.'
  - name: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
    text: 'Aspose.GIS for .NET Library: You can download it from the **Aspose.GIS
      for .NET download page**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).'
  - name: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
    text: 'Development Environment: Ensure you have a development environment set
      up with Visual Studio or any other .NET IDE installed.'
  type: HowTo
- questions:
  - answer: It means building a polygon that contains one or more interior rings (holes)
      that are excluded from the area.
    question: What does “create polygon with hole” mean?
  - answer: Aspose.GIS for .NET provides full support for exterior and interior rings.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  - answer: Typically under 10 minutes to implement and test.
    question: How long does it take?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- polygon interior ring
- Aspose.GIS
- geospatial .NET
- create polygon with hole
- GIS development
title: Créer un polygon interior ring avec un hole en utilisant Aspose.GIS
url: /fr/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un anneau intérieur de polygone avec un trou à l'aide d'Aspose.GIS

## Introduction
Dans ce tutoriel, vous apprendrez comment **créer un anneau intérieur de polygone** contenant un trou à l'aide d'Aspose.GIS pour .NET. Que vous développiez une application de cartographie, effectuiez une analyse spatiale ou prépariez des données pour des services GIS, intégrer un trou à l'intérieur d'un polygone est une compétence essentielle. Nous parcourrons l'ensemble du flux de travail — depuis la configuration de l'environnement de développement jusqu'à la génération d'un objet polygone valide pouvant être enregistré dans n'importe quel format géospatial pris en charge.

## Réponses rapides
- **Que signifie “create polygon with hole” ?** Cela signifie construire un polygone qui contient un ou plusieurs anneaux intérieurs (trous) qui sont exclus de la zone.  
- **Quelle bibliothèque gère cela ?** Aspose.GIS for .NET fournit une prise en charge complète des anneaux extérieurs et intérieurs.  
- **Ai-je besoin d'une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Combien de temps cela prend-il ?** Typiquement moins de 10 minutes pour implémenter et tester.

## Comment ajouter un trou à un polygone avec Aspose.GIS
Chargez votre environnement GIS, définissez un anneau extérieur, puis ajoutez un ou plusieurs anneaux intérieurs. Aspose.GIS oriente automatiquement les anneaux et valide la géométrie, vous permettant de vous concentrer sur les coordonnées qui représentent le vide dont vous avez besoin.

## Qu'est-ce qu'un anneau intérieur de polygone ?
Un **anneau intérieur de polygone** est une frontière interne qui soustrait de la surface de la forme extérieure du polygone.  
Vous le créez en définissant une séquence fermée de points que Aspose.GIS considère comme un trou, exclu lors du calcul de la surface ou du rendu de la forme.

## Pourquoi créer un anneau intérieur de polygone avec Aspose.GIS ?
Aspose.GIS valide et corrige l'orientation des anneaux en moins de 5 ms pour des polygones typiques de 200 points, éliminant ainsi le besoin de code de validation personnalisé. Il prend également en charge **plus de 30 formats de fichiers géospatiaux** (Shapefile, GeoJSON, GML, KML, etc.) et peut traiter des polygones contenant jusqu'à 10 000 points sans charger le fichier complet en mémoire, vous offrant à la fois rapidité et évolutivité.

## Scénarios réels pour les polygones avec trous
1. **Parcelle de terrain avec un lac interne** – le lac est modélisé comme un trou afin de ne pas être compté dans la surface de la parcelle.  
2. **Empreintes de bâtiments avec cours** – la cour est exclue de l'empreinte du bâtiment.  
3. **Zones protégées à l'intérieur d'une plus grande zone de conservation** – vous pouvez exclure des sections restreintes sans créer de couches séparées.

## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Bibliothèque Aspose.GIS pour .NET : Vous pouvez la télécharger depuis la **page de téléchargement d'Aspose.GIS pour .NET**([https://releases.aspose.com/gis/net/](https://releases.aspose.com/gis/net/)).  
2. Environnement de développement : Assurez-vous d'avoir un environnement de développement configuré avec Visual Studio ou tout autre IDE .NET installé.

## Importer les espaces de noms
L'espace de noms `Aspose.Gis` contient tous les types de géométrie dont vous avez besoin, y compris `Polygon`, `LinearRing` et les méthodes d'assistance pour la validation.

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Passons maintenant à la création d'une géométrie de polygone avec un trou à l'aide d'Aspose.GIS pour .NET.

## Étape 1 : créer l'objet polygone
`Polygon` est le type de géométrie d'Aspose.GIS qui représente un polygone planaire avec des anneaux intérieurs optionnels. Nous commençons par instancier un objet `Polygon` vide qui contiendra plus tard à la fois les anneaux extérieurs et intérieurs.

```csharp
Polygon polygon = new Polygon();
```

## Étape 2 : définir l'anneau extérieur
`LinearRing` est la classe utilisée pour les frontières extérieures et intérieures. L'anneau extérieur définit la frontière extérieure du polygone. Ajoutez des points dans le sens horaire pour former une forme fermée.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Étape 3 : définir l'anneau intérieur (trou)
`LinearRing` représente également les anneaux intérieurs. L'anneau intérieur est le **trou** qui sera exclu de la surface du polygone. Les points sont généralement ajoutés dans le sens anti‑horaire, mais Aspose.GIS gère automatiquement l'orientation.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Étape 4 : assigner l'anneau extérieur et ajouter l'anneau intérieur au polygone
La méthode `AddInteriorRing` attache un ou plusieurs anneaux intérieurs à un `Polygon`. Appelez‑la après avoir défini la propriété `ExteriorRing` ; vous pouvez répéter l'appel pour ajouter plusieurs trous.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Conseils et bonnes pratiques
- **L'orientation est importante pour la lisibilité** – bien qu'Aspose.GIS corrige automatiquement l'orientation, garder les anneaux extérieurs dans le sens horaire et les anneaux intérieurs dans le sens anti‑horaire rend la géométrie plus facile à inspecter dans les visualiseurs GIS.  
- **Fermer chaque anneau** – répétez toujours la première coordonnée comme dernier point ; cela garantit une forme fermée valide.  
- **Valider après création** – vous pouvez appeler `polygon.IsValid` pour vous assurer que la géométrie respecte les normes OGC avant l'enregistrement.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| Le trou n'apparaît pas dans le visualiseur GIS | Orientation de l'anneau intérieur inversée | Assurez‑vous d'ajouter les points dans le sens opposé de l'anneau extérieur (anti‑horaire). |
| Erreur de polygone invalide | Anneaux non fermés (premier ≠ dernier point) | Répétez le premier point comme dernier point dans chaque anneau (comme indiqué ci‑dessus). |
| Géométrie vide inattendue | Oublier d'assigner `ExteriorRing` avant d'ajouter les anneaux intérieurs | Définissez d'abord `polygon.ExteriorRing`, puis appelez `AddInteriorRing`. |

## Questions fréquentes
### 1. Qu'est-ce qu'Aspose.GIS ?
Aspose.GIS est une bibliothèque .NET qui permet aux développeurs de travailler avec des données géospatiales, leur permettant de créer, lire et manipuler divers formats de fichiers géospatiaux.

### 2. Puis-je utiliser Aspose.GIS pour des projets commerciaux ?
Oui, vous pouvez utiliser Aspose.GIS pour des projets personnels et commerciaux en achetant une licence. Consultez la **page d'achat d'Aspose.GIS**([https://purchase.aspose.com/buy](https://purchase.aspose.com/buy)) pour plus de détails.

### 3. Existe-t-il un essai gratuit disponible pour Aspose.GIS ?
Oui, vous pouvez profiter d'un essai gratuit d'Aspose.GIS depuis la **page de téléchargement de l'essai gratuit d'Aspose.GIS**([https://releases.aspose.com/](https://releases.aspose.com/)).

### 4. Où puis‑je trouver du support pour Aspose.GIS ?
Vous pouvez trouver du support pour Aspose.GIS sur le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Comment puis‑je obtenir une licence temporaire pour Aspose.GIS ?
Vous pouvez obtenir une licence temporaire pour Aspose.GIS depuis la **page de licence temporaire d'Aspose.GIS**([https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/)).

---

**Dernière mise à jour:** 2026-09-05  
**Testé avec:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose

## Tutoriels associés

- [Comment créer une géométrie de polygone avec Aspose.GIS pour .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Apprenez à créer une géométrie MultiPolygon avec Aspose.GIS](/gis/net/geometry-creation/create-multipolygon-geometry/)
- [Convertir un polygone en ligne avec Aspose.GIS pour .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}