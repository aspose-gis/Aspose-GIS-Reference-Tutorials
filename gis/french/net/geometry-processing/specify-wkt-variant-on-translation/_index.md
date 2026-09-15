---
date: 2026-09-15
description: Apprenez comment attribuer le système de coordonnées, définir la variante
  WKT et contrôler la précision décimale lors de la création d'une géométrie de point
  en C# avec Aspose.GIS pour .NET.
keywords:
- assign coordinate system
- assign spatial reference
- set decimal precision
- create point geometry
- set numeric format
lastmod: 2026-09-15
linktitle: Spécifier la variante WKT lors de la traduction
og_description: Apprenez comment attribuer le système de coordonnées, définir la variante
  WKT et contrôler la précision décimale lors de la création d'une géométrie de point
  en C# avec Aspose.GIS pour .NET.
og_image_alt: Developer guide showing C# code to assign coordinate system and configure
  WKT output with Aspose.GIS
og_title: Attribuer le système de coordonnées, définir la variante WKT avec Aspose.GIS
schemas:
- author: Aspose
  dateModified: '2026-09-15'
  description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  headline: Assign coordinate system, set WKT variant using Aspose.GIS
  type: TechArticle
- description: Learn how to assign coordinate system, set the WKT variant and control
    decimal precision when creating point geometry in C# with Aspose.GIS for .NET.
  name: Assign coordinate system, set WKT variant using Aspose.GIS
  steps:
  - name: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
    text: Aspose.GIS for .NET – download from the [download page](https://releases.aspose.com/gis/net/).
  - name: A .NET development environment (Visual Studio, VS Code, or Rider).
    text: A .NET development environment (Visual Studio, VS Code, or Rider).
  - name: Basic familiarity with C# and the .NET framework.
    text: Basic familiarity with C# and the .NET framework.
  type: HowTo
- questions:
  - answer: It binds a geometry to a specific coordinate reference system such as
      WGS‑84.
    question: What does “assign coordinate system” mean?
  - answer: Iso, SimpleFeatureAccessOutdated, and ExtendedPostGis.
    question: Which WKT variants are supported?
  - answer: Use the `NumericFormat` enum (`General`, `RoundTrip`, `Flat`).
    question: How can I control decimal precision?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license for Aspose.GIS?
  - answer: .NET Framework 4.0+ and .NET Core/5/6+.
    question: What .NET versions are compatible?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- assign coordinate system
- Aspose.GIS
- C# geometry
- WKT variant
title: Attribuer le système de coordonnées, définir la variante WKT avec Aspose.GIS
url: /fr/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Attribuer le système de coordonnées, définir la variante WKT avec Aspose.GIS

## Introduction
Dans ce tutoriel, vous apprendrez à **attribuer un système de coordonnées**, choisir la bonne variante WKT et contrôler la précision décimale lorsque vous **créez une géométrie de point** en C# avec Aspose.GIS pour .NET. Que vous construisiez un service de cartographie, effectuiez des analyses spatiales ou échangiez des données entre plateformes SIG, ces paramètres garantissent que votre sortie soit à la fois interopérable et lisible. Parcourons le processus étape par étape.

## Réponses rapides
- **Que signifie « attribuer un système de coordonnées » ?** Cela lie une géométrie à un système de référence de coordonnées spécifique tel que WGS‑84.  
- **Quelles variantes WKT sont prises en charge ?** Iso, SimpleFeatureAccessOutdated et ExtendedPostGis.  
- **Comment contrôler la précision décimale ?** Utilisez l’énumération `NumericFormat` (`General`, `RoundTrip`, `Flat`).  
- **Ai‑je besoin d’une licence pour Aspose.GIS ?** Une version d’essai gratuite est disponible ; une licence commerciale est requise pour une utilisation en production.  
- **Quelles versions de .NET sont compatibles ?** .NET Framework 4.0+ et .NET Core/5/6+.

## Qu’est‑ce que « attribuer un système de coordonnées » ?
Attribuer une référence spatiale (ou système de référence spatiale, SRS) indique aux logiciels SIG comment interpréter les valeurs de coordonnées d’une géométrie, en reliant les nombres à un système de coordonnées du monde réel tel que WGS‑84. Sans SRS, les nombres de latitude‑longitude d’un point n’ont aucune signification dans le monde réel.

## Pourquoi contrôler la variante WKT et le format numérique ?
Plus de 30 outils SIG attendent des syntaxes WKT spécifiques, donc sélectionner la bonne variante évite les erreurs d’importation. Définir le format numérique réduit le bruit d’arrondi et garde la sortie concise, ce qui est particulièrement important lorsque les journaux ou les fichiers sont analysés programmatique­ment.

## Prérequis
1. Aspose.GIS pour .NET – téléchargez-le depuis la [page de téléchargement](https://releases.aspose.com/gis/net/).  
2. Un environnement de développement .NET (Visual Studio, VS Code ou Rider).  
3. Une connaissance de base du C# et du framework .NET.

## Importer les espaces de noms
Avant d’utiliser les classes Aspose.GIS, importez les espaces de noms requis :

```csharp
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Gis;
```

## Comment attribuer un système de coordonnées à un point ?
Chargez une instance `Point`, puis attachez un système de référence spatiale (SRS) à l’aide de la classe `SpatialReference`. Ce schéma en deux étapes garantit que la géométrie porte ses métadonnées de système de coordonnées lors de l’exportation, permettant aux outils en aval d’interpréter correctement les coordonnées. La classe `Point` représente un emplacement unique défini par les coordonnées X (longitude) et Y (latitude).

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Étape 2 : attribuer le système de référence spatiale (SRS)
Nous **attribuons maintenant la référence spatiale** au point. `SpatialReference` représente un système de référence de coordonnées identifié par un SRID. Ici, nous utilisons le système largement supporté WGS‑84 (SRID 4326) :

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Étape 3 : spécifier la variante WKT souhaitée
Choisissez la variante WKT qui correspond à votre application en aval :

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Comment définir la précision décimale pour la sortie WKT ?
Contrôlez le nombre de chiffres apparaissant dans la chaîne finale à l’aide de l’énumération `NumericFormat`, qui définit des règles de formatage telles que `General`, `RoundTrip` ou `Flat`. Sélectionner `RoundTrip` préserve la fidélité complète des coordonnées pour les scénarios de va‑et‑vient, tandis que `General` fournit une représentation concise adaptée à la plupart des tâches de visualisation. L’énumération `NumericFormat` contrôle la façon dont les nombres de coordonnées sont formatés dans la sortie WKT.

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Pièges courants et conseils
- **Piège :** Oublier de définir le SRS avant d’appeler `AsText` peut entraîner l’absence d’informations SRID.  
- **Conseil :** Utilisez `NumericFormat.RoundTrip` lorsque vous avez besoin d’un va‑et‑vient sans perte des coordonnées.  
- **Conseil :** La variante `Iso` est la plus portable ; choisissez `ExtendedPostGis` uniquement si vous avez besoin d’un SRID intégré.

## Conclusion
Vous savez maintenant comment **attribuer un système de coordonnées**, choisir la variante WKT appropriée et **définir la précision décimale** lorsque vous **créez une géométrie de point** avec Aspose.GIS. Ces contrôles vous offrent la flexibilité nécessaire pour répondre aux exigences exactes de tout flux de travail SIG, de la simple visualisation à l’analyse spatiale de haute précision.

## Questions fréquemment posées

**Q :** Aspose.GIS est‑il compatible avec toutes les versions de .NET ?  
**R :** Oui, Aspose.GIS prend en charge .NET Framework 4.0 et supérieur, ainsi que .NET Core/5/6.

**Q :** Puis‑je utiliser Aspose.GIS pour des projets commerciaux ?  
**R :** Absolument. Une licence commerciale est requise pour la production, mais une version d’essai gratuite est disponible pour l’évaluation.

**Q :** Aspose.GIS prend‑il en charge d’autres formats de données spatiales ?  
**R :** Oui, il fonctionne avec plus de 30 formats, dont ESRI Shapefile, GeoJSON, KML, CSV et bien d’autres.

**Q :** Où puis‑je télécharger une version d’essai gratuite ?  
**R :** Vous pouvez télécharger une version d’essai gratuite d’Aspose.GIS depuis la [page de téléchargement d'essai gratuit d'Aspose.GIS](https://releases.aspose.com/).

**Q :** Comment obtenir de l’aide en cas de problème ?  
**R :** Publiez vos questions sur le [forum](https://forum.aspose.com/c/gis/33) de la communauté Aspose.GIS où le personnel d’Aspose et les membres de la communauté peuvent vous aider.

---

**Dernière mise à jour :** 2026-09-15  
**Testé avec :** Aspose.GIS pour .NET (dernière version)  
**Auteur :** Aspose

## Tutoriels associés

- [Créer une couche vectorielle et définir son système de référence spatiale](/gis/net/layer-data-operations/set-layer-spatial-reference-system/)
- [Comment convertir une géométrie en WKT avec Aspose.GIS pour .NET](/gis/net/geometry-processing/translate-geometry-to-wkt/)
- [Comment limiter la précision lors de l’écriture de géométries avec Aspose.GIS](/gis/net/geometry-processing/limit-precision-writing-geometries/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}