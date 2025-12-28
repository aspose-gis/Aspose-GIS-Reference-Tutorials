---
date: 2025-12-28
description: Apprenez à définir la grille d’une couche File GDB à l’aide d’Aspose.GIS
  pour .NET, y compris l’ajout de fonctionnalités à la couche et la validation de
  la plage de coordonnées.
linktitle: Define Precision Grid for File GDB Layer
second_title: Aspose.GIS .NET API
title: Comment définir la grille pour la couche File GDB dans Aspose.GIS
url: /fr/net/layer-data-operations/define-precision-grid-for-file-gdb-layer/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir la grille pour une couche File GDB dans Aspose.GIS

## Introduction
Dans ce tutoriel, vous apprendrez **comment définir la grille** pour une couche File Geodatabase (GDB) en utilisant Aspose.GIS pour .NET. Définir une grille de précision vous aide à **valider la plage de coordonnées**, empêche les erreurs hors‑plage et garantit que les données que vous **ajoutez des entités à la couche** restent précises et fiables. Nous parcourrons chaque étape, expliquerons pourquoi ces paramètres sont importants et vous montrerons comment gérer les problèmes courants.

## Réponses rapides
- **Que signifie « définir la grille » ?** Elle définit la précision des coordonnées et la plage valide pour une couche GIS.  
- **Pourquoi utiliser une grille de précision ?** Elle protège vos données contre des coordonnées invalides et améliore l’efficacité du stockage.  
- **Quelle bibliothèque fournit cette fonctionnalité ?** Aspose.GIS pour .NET.  
- **Ai‑je besoin d’une licence ?** Une version d’essai est disponible ; une licence commerciale est requise pour la production.  
- **Puis‑je l’utiliser avec .NET Core ?** Oui, Aspose.GIS prend en charge .NET Framework et .NET Core.

## Qu’est‑ce qu’une grille de précision et pourquoi la définir ?
Une grille de précision est un ensemble de paramètres (origine, échelle, etc.) qui indique au moteur GIS comment arrondir et stocker les valeurs de coordonnées. En définissant une grille, vous **validez automatiquement la plage de coordonnées**, et toute tentative d’insérer un point en dehors de la grille déclenchera une exception—vous aidant à **gérer les scénarios hors plage** dès le début du développement.

## Prérequis
1. **Visual Studio** – toute version récente (Community, Professional ou Enterprise).  
2. **Aspose.GIS pour .NET** – téléchargez-le depuis le [site web](https://releases.aspose.com/gis/net/).  
3. **Connaissances de base en C#** – vous devez être à l’aise avec la création de projets console .NET.

## Importer les espaces de noms
Tout d'abord, importez les espaces de noms nécessaires pour travailler avec Aspose.GIS :

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Comment définir la grille dans une couche File GDB
Voici un guide étape par étape qui montre exactement comment configurer la grille, créer une couche et **ajouter des entités à la couche** en toute sécurité.

### Étape 1 : Créer un jeu de données
Nous commençons par créer un nouveau jeu de données File Geodatabase. C’est là que la couche résidera.

```csharp
var path = "Your Document Directory" + "PrecisionGrid_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

### Étape 2 : Définir les options de la grille de précision
Ici, nous spécifions les paramètres de la grille. Ajustez les origines et les échelles pour correspondre au système de coordonnées de votre projet.

```csharp
var options = new FileGdbOptions
{
    CoordinatePrecisionGrid = new FileGdbCoordinatePrecisionGrid
    {
        XOrigin = -400,
        YOrigin = -400,
        XYScale = 1e10,
        MOrigin = 0,
        MScale = 1e4,
    },
    EnsureValidCoordinatesRange = true,
};
```

*Le drapeau `EnsureValidCoordinatesRange = true` indique à Aspose.GIS de **valider la plage de coordonnées** pour chaque entité que vous ajoutez.*

### Étape 3 : Créer une couche avec la grille
Nous créons maintenant une nouvelle couche à l’intérieur du jeu de données, en appliquant les options de grille que nous venons de définir. Nous utiliserons le système de référence spatiale WGS84.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options, SpatialReferenceSystem.Wgs84))
{
```

### Étape 4 : Ajouter des entités à la couche
Nous construisons deux entités ponctuelles. Le premier point se trouve à l’intérieur de la grille, tandis que le second tombe délibérément en dehors pour démontrer **comment gérer les erreurs hors plage**.

```csharp
var feature = layer.ConstructFeature();
feature.Geometry = new Point(10, 20) { M = 10.1282 };
layer.Add(feature);
feature = layer.ConstructFeature();
feature.Geometry = new Point(-410, 0) { M = 20.2343 };
```

### Étape 5 : Gérer les exceptions lors de l’ajout d’entités hors plage
Tenter d’ajouter la seconde entité déclenchera une exception car sa coordonnée X (`-410`) est en dehors de la grille définie. Nous capturons l’exception et affichons un message clair.

```csharp
try
{
    layer.Add(feature);
}
catch (GisException e)
{
    Console.WriteLine(e.Message); // X value -410 is out of valid range.
}
```

### Étape 6 : Nettoyage
Les instructions `using` ferment et libèrent automatiquement le jeu de données et la couche, garantissant que toutes les ressources sont libérées.

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Exception : « X value … is out of valid range. »** | Les coordonnées sont en dehors de la grille de précision. | Ajustez `XOrigin`, `YOrigin` ou `XYScale` pour couvrir vos données, ou assurez‑vous que les données d’entrée sont dans la plage définie. |
| **Les entités n’apparaissent pas dans le visualiseur GIS** | La couche n’est pas enregistrée ou la référence spatiale est incorrecte. | Vérifiez que `SpatialReferenceSystem.Wgs84` correspond au CRS du visualiseur, et que `Dataset.Create` a réussi. |
| **Valeurs M ignorées** | `MScale` est à 0 ou trop faible. | Définissez un `MScale` raisonnable (par ex., `1e4`) pour stocker les valeurs de mesure. |

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.GIS pour .NET avec d’autres formats de fichiers GIS ?**  
R : Oui, Aspose.GIS prend en charge Shapefile, GeoJSON, KML et de nombreux autres formats.

**Q : Aspose.GIS pour .NET est‑il compatible avec .NET Core ?**  
R : Absolument. La bibliothèque fonctionne avec .NET Framework, .NET Core et .NET 5/6+.

**Q : Puis‑je effectuer des opérations spatiales telles que le buffering ou l’intersection ?**  
R : Oui, l’API inclut des méthodes pour le buffering, l’intersection et le calcul des distances.

**Q : Aspose.GIS offre‑t‑il des capacités de transformation de coordonnées ?**  
R : Oui, vous pouvez transformer des géométries entre différents systèmes de référence spatiale à l’aide des outils de reprojection intégrés.

**Q : Une version d’essai est‑elle disponible ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite depuis le [site web](https://releases.aspose.com/gis/net/).

**Dernière mise à jour :** 2025-12-28  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}