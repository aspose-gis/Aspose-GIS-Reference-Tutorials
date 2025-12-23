---
date: 2025-12-23
description: Apprenez à convertir la géométrie en WKT avec des options variantes,
  à définir le format numérique et à ajuster la précision décimale en utilisant Aspose.GIS
  pour .NET.
linktitle: Convert Geometry to WKT
second_title: Aspose.GIS .NET API
title: Convertir la géométrie en options de variante WKT avec Aspose.GIS
url: /fr/net/geometry-processing/specify-wkt-variant-on-translation/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir la géométrie en options de variante WKT avec Aspose.GIS

## Introduction
Dans les applications .NET modernes, **convertir la géométrie en WKT** est une étape courante lorsque vous devez échanger des données spatiales avec d’autres systèmes ou les stocker dans un format texte. Aspose.GIS pour .NET rend cette conversion simple tout en vous offrant un contrôle total sur la variante WKT, le format numérique et la précision décimale. Dans ce tutoriel, vous apprendrez comment convertir la géométrie en WKT, choisir la bonne variante et affiner la sortie pour répondre exactement aux exigences de votre projet.

## Réponses rapides
- **Que signifie « convertir la géométrie en WKT » ?** Cela transforme les objets géométriques (points, lignes, polygones) en représentation Well‑Known Text.  
- **Quelles variantes WKT sont prises en charge ?** `Iso`, `SimpleFeatureAccessOutdated` et `ExtendedPostGis`.  
- **Comment contrôler la précision décimale ?** Utilisez les options `NumericFormat` telles que `General`, `RoundTrip` ou `Flat`.  
- **Ai‑je besoin d’une licence pour la production ?** Oui, une licence commerciale est requise pour une utilisation non‑essai.  
- **Quelles versions de .NET sont compatibles ?** .NET Framework 4.0+ et .NET 5/6/7.

## Qu’est‑ce que « convertir la géométrie en WKT » ?
Convertir la géométrie en WKT produit une chaîne lisible par l’homme qui décrit les objets spatiaux. Ce format est largement accepté par les outils SIG, les bases de données et les services web, ce qui le rend idéal pour l’échange de données.

## Pourquoi utiliser Aspose.GIS pour cette conversion ?
- **Contrôle de la précision** – Choisissez le nombre de décimales émises.  
- **Flexibilité des variantes** – Adaptez le dialecte WKT exact requis par votre système en aval.  
- **Aucune dépendance externe** – Bibliothèque pure .NET, sans binaires natifs.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Aspose.GIS pour .NET** – Téléchargez‑le et installez‑le depuis la [page de téléchargement](https://releases.aspose.com/gis/net/).  
2. **Environnement de développement** – Toute version récente de Visual Studio ou VS Code avec le SDK .NET.  
3. **Connaissances de base en C#** – Familiarité avec les classes, les objets et le framework .NET.

## Importer les espaces de noms
Tout d’abord, importez les espaces de noms requis :

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

## Étape 1 : Créer un objet Point
Créez un `Point` que vous **convertirez ensuite en WKT**. Le point comprend la latitude, la longitude et une valeur de mesure (M) optionnelle :

```csharp
Point point = new Point(23.5732, 25.3421) { M = 40.3 };
```

## Étape 2 : Définir le système de référence spatiale (SRS)
Attribuez un système de référence spatiale afin que la sortie WKT sache à quel système de coordonnées se référer. Ici, nous utilisons le système commun WGS84 :

```csharp
point.SpatialReferenceSystem = SpatialReferenceSystem.Wgs84;
```

## Étape 3 : Spécifier la variante WKT
Choisissez la variante WKT appropriée lorsque vous **convertissez la géométrie en WKT**. Chaque variante formate légèrement différemment la sortie :

```csharp
Console.WriteLine(point.AsText(WktVariant.Iso)); // POINT M (23.5732, 25.3421, 40.3)
Console.WriteLine(point.AsText(WktVariant.SimpleFeatureAccessOutdated)); // POINT (23.5732, 25.3421)
Console.WriteLine(point.AsText(WktVariant.ExtendedPostGis)); // SRID=4326;POINTM (23.5732, 25.3421, 40.3)
```

## Étape 4 : Contrôler le format numérique (Définir le format numérique & ajuster la précision décimale)
Affinez la représentation numérique des coordonnées. La classe `NumericFormat` vous permet de **définir le format numérique** et **d’ajuster la précision décimale** selon vos besoins :

```csharp
Console.WriteLine("G17  : " + point.AsText(WktVariant.Iso, NumericFormat.General(17))); // POINT M (23.5732 25.342099999999999 40.299999999999997)
Console.WriteLine("R    : " + point.AsText(WktVariant.Iso, NumericFormat.RoundTrip)); // POINT M (23.5732 25.3421 40.3)
Console.WriteLine("G3   : " + point.AsText(WktVariant.Iso, NumericFormat.General(3))); // POINT M (23.6 25.3 40.3)
Console.WriteLine("Flat3: " + point.AsText(WktVariant.Iso, NumericFormat.Flat(3))); // POINT M (23.573 25.342 40.3)
```

## Problèmes courants & astuces
- **Valeur M manquante** – Si vous n’avez pas besoin d’une mesure, omettez la propriété `M` ; la variante ISO la supprimera automatiquement.  
- **Précision inattendue** – Vérifiez que vous utilisez le bon `NumericFormat` ; `General` conserve la pleine précision double, tandis que `Flat` arrondit au nombre de décimales spécifié.  
- **SRID non affiché** – Seule la variante `ExtendedPostGis` préfixe la sortie avec `SRID=`. Choisissez cette variante lorsque votre système cible attend un SRID.

## Conclusion
En suivant ces étapes, vous savez maintenant comment **convertir la géométrie en WKT**, sélectionner la bonne variante et contrôler précisément la sortie numérique. Cela vous offre la flexibilité d’intégrer Aspose.GIS à n’importe quel flux de travail SIG, base de données ou service web consommant du WKT.

## FAQ's
### Aspose.GIS est‑il compatible avec toutes les versions de .NET ?
Oui, Aspose.GIS prend en charge .NET Framework 4.0 et supérieur.  

### Puis‑je utiliser Aspose.GIS pour des projets commerciaux ?
Oui, Aspose.GIS peut être utilisé tant pour des projets personnels que commerciaux.  

### Aspose.GIS offre‑t‑il la prise en charge d’autres formats de données spatiales ?
Oui, Aspose.GIS supporte une large gamme de formats de données spatiales, y compris ESRI Shapefile, GeoJSON et KML.  

### Existe‑t‑il une version d’essai gratuite d’Aspose.GIS ?
Oui, vous pouvez télécharger une version d’essai gratuite d’Aspose.GIS [ici](https://releases.aspose.com/).  

### Où puis‑je obtenir de l’aide ou du support pour Aspose.GIS ?
Vous pouvez poser vos questions ou demander de l’assistance à la communauté Aspose.GIS sur le [forum](https://forum.aspose.com/c/gis/33).

## Questions fréquemment posées
**Q : Comment exporter une collection de géométries en une seule chaîne WKT ?**  
R : Parcourez chaque géométrie de la collection et concaténez leurs résultats `AsText`, en les séparant éventuellement par des virgules ou des sauts de ligne.

**Q : Puis‑je changer le SRID sans modifier les coordonnées ?**  
R : Oui, définissez la propriété `SpatialReferenceSystem` sur le SRID souhaité ; les valeurs de coordonnées restent inchangées.

**Q : Que se passe‑t‑il si j’utilise une variante WKT non prise en charge ?**  
R : Aspose.GIS lèvera une `ArgumentException`. Validez toujours la variante par rapport aux valeurs de l’énumération `WktVariant`.

---

**Dernière mise à jour :** 2025-12-23  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}