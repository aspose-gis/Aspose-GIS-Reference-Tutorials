---
date: 2026-04-09
description: Apprenez comment attribuer une référence spatiale et définir la précision
  décimale lors de la création d’un point C# avec Aspose.GIS pour .NET dans vos applications
  .NET.
keywords:
- assign spatial reference
- set decimal precision
- create point c#
linktitle: Spécifier la variante WKT lors de la traduction
second_title: Aspose.GIS .NET API
title: Attribuer la référence spatiale et définir la variante WKT avec Aspose.GIS
url: /fr/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Attribuer une référence spatiale et définir la variante WKT avec Aspose.GIS

## Introduction
Dans ce tutoriel, vous apprendrez comment **attribuer une référence spatiale** à une géométrie et contrôler le format exact de sortie WKT avec Aspose.GIS pour .NET. Que vous ayez besoin de **créer des objets point C#** pour la cartographie, l'analyse ou l'échange de données, pouvoir choisir la bonne variante WKT et la précision numérique rend vos données spatiales interopérables et faciles à lire. Parcourons le processus étape par étape.

## Réponses rapides
- **Que signifie « attribuer une référence spatiale » ?** Elle lie une géométrie à un système de coordonnées spécifique tel que WGS‑84.  
- **Quelles variantes WKT sont prises en charge ?** Iso, SimpleFeatureAccessOutdated et ExtendedPostGis.  
- **Comment contrôler la précision décimale ?** Utilisez les options `NumericFormat` comme `General`, `RoundTrip` ou `Flat`.  
- **Ai-je besoin d’une licence ?** Un essai gratuit est disponible ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont compatibles ?** .NET Framework 4.0+ et .NET Core/5/6+.

## Qu’est‑ce que « attribuer une référence spatiale » ?
Attribuer une référence spatiale (ou système de référence spatiale, SRS) indique au logiciel SIG comment interpréter les valeurs de coordonnées d’une géométrie. Sans SRS, les coordonnées latitude‑longitude d’un point n’ont aucune signification dans le monde réel.

## Pourquoi contrôler la variante WKT et le format numérique ?
Différents outils SIG attendent des syntaxes WKT légèrement différentes. Sélectionner la bonne variante assure un échange de données fluide, tandis que le réglage de la précision décimale évite les erreurs d’arrondi ou les nombres trop longs qui encombrent les journaux et les fichiers.

## Prérequis
1. Aspose.GIS pour .NET – téléchargez depuis la [page de téléchargement](https://releases.aspose.com/gis/net/).  
2. Un environnement de développement .NET (Visual Studio, VS Code ou Rider).  
3. Une connaissance de base du C# et du framework .NET.

## Importer les espaces de noms
Avant d’utiliser les classes Aspose.GIS, importez les espaces de noms requis :

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

## Étape 1 : Créer un objet Point (create point C#)
Nous commençons par construire un `Point` avec les valeurs de latitude, longitude et une mesure (M) optionnelle :

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Étape 2 : Attribuer le système de référence spatiale (SRS)
Nous **attribuons maintenant une référence spatiale** au point. Ici, nous utilisons le système largement supporté WGS‑84 (SRID 4326) :

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Étape 3 : Spécifier la variante WKT souhaitée
Choisissez la variante WKT qui correspond à votre application en aval :

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Étape 4 : Définir la précision décimale pour la sortie WKT
Contrôlez le nombre de chiffres apparaissant dans la chaîne finale en utilisant `NumericFormat` :

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

### Pièges courants et astuces
- **Piège :** Oublier de définir le SRS avant d’appeler `AsText` peut entraîner l’absence d’informations SRID.  
- **Astuce :** Utilisez `NumericFormat.RoundTrip` lorsque vous avez besoin d’un aller‑retour sans perte des coordonnées.  
- **Astuce :** La variante `Iso` est la plus portable ; choisissez `ExtendedPostGis` uniquement lorsque vous avez besoin d’un SRID intégré.

## Conclusion
Vous savez maintenant comment **attribuer une référence spatiale**, choisir la variante WKT appropriée et **définir la précision décimale** lorsque vous **créez des objets point C#** avec Aspose.GIS. Ces contrôles vous offrent la flexibilité nécessaire pour répondre aux exigences exactes de tout flux de travail SIG, de la visualisation simple à l’analyse spatiale haute précision.

## Questions fréquemment posées

**Q :** Aspose.GIS est‑il compatible avec toutes les versions de .NET ?  
**R :** Oui, Aspose.GIS prend en charge .NET Framework 4.0 et supérieur, ainsi que .NET Core/5/6.

**Q :** Puis‑je utiliser Aspose.GIS pour des projets commerciaux ?  
**R :** Absolument. Une licence commerciale est requise pour une utilisation en production, mais un essai gratuit est disponible pour l’évaluation.

**Q :** Aspose.GIS prend‑il en charge d’autres formats de données spatiales ?  
**R :** Oui, il fonctionne avec ESRI Shapefile, GeoJSON, KML et de nombreux autres formats.

**Q :** Où puis‑je télécharger un essai gratuit ?  
**R :** Vous pouvez télécharger une version d’essai gratuite d’Aspose.GIS depuis [ici](https://releases.aspose.com/).

**Q :** Comment obtenir de l’aide si je rencontre des problèmes ?  
**R :** Publiez vos questions sur le [forum](https://forum.aspose.com/c/gis/33) de la communauté Aspose.GIS où le personnel d’Aspose et les membres de la communauté peuvent vous aider.

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}