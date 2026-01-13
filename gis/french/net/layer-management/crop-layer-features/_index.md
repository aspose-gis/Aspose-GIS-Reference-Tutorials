---
date: 2026-01-13
description: Apprenez à recadrer les fonctionnalités de couche avec Aspose.GIS pour
  .NET, y compris comment recadrer un raster avec un polygone, extraire la taille
  des cellules du raster et récupérer l’étendue du raster. Téléchargez votre version
  d’essai gratuite maintenant.
linktitle: How to Crop Layer Features
second_title: Aspose.GIS .NET API
title: Comment rogner les entités de couche avec Aspose.GIS pour .NET
url: /fr/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment recadrer les entités de couche

## Introduction
Dans ce tutoriel, vous apprendrez **comment recadrer les entités de couche** en utilisant Aspose.GIS for .NET, une approche puissante qui vous permet de **recadrer un raster avec un polygone**, **extraire la taille des cellules du raster**, et **récupérer l’étendue du raster** pour une analyse géospatiale précise. Que vous prépariez des données pour une carte web, que vous découpiez des images satellites, ou que vous isoliez une zone d’intérêt, ce guide pas à pas vous montre exactement comment accomplir la tâche.

## Réponses rapides
- **Que signifie « crop layer » ?** Il découpe une couche raster ou vectorielle aux limites d’une géométrie fournie.  
- **Quelle géométrie est utilisée dans cet exemple ?** Un polygone défini au format WKT.  
- **Puis‑je extraire la taille des cellules après le recadrage ?** Oui – la propriété `CellSize` fournit cette information.  
- **Ai‑je besoin d’une licence pour exécuter le code ?** Une licence temporaire fonctionne pour l’évaluation ; une licence complète est requise en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu’est‑ce que « how to crop layer » ?
Recadrer une couche consiste à limiter le jeu de données à une zone géographique spécifique, en éliminant tout ce qui se trouve en dehors de la forme définie. Cela réduit la taille du fichier, accélère le traitement et concentre l’analyse sur la région qui vous intéresse.

## Pourquoi utiliser Aspose.GIS pour le recadrage ?
- **Gestion raster haute performance** – idéal pour les gros fichiers GeoTiff.  
- **API simple** – appel `Crop` en une ligne avec n’importe quelle géométrie.  
- **Compatibilité .NET complète** – fonctionne sur les applications desktop, serveur et cloud.  
- **Gestion précise des références spatiales** – préserve automatiquement les informations CRS.

## Prérequis
Avant de plonger dans la magie de la manipulation géospatiale, assurez‑vous d’avoir les prérequis suivants :

- Bibliothèque Aspose.GIS for .NET : assurez‑vous que la bibliothèque Aspose.GIS est installée dans votre projet .NET. Vous pouvez la télécharger [ici](https://releases.aspose.com/gis/net/).  
- Répertoire de documents : créez un répertoire pour stocker vos documents. Remplacez `"Your Document Directory"` dans le code fourni par le chemin réel de votre répertoire de documents.

enant, plongeons dans le guide étape par étape.

## Importer les espaces de noms
Commencez par importer les espaces de noms nécessaires pour exploiter toute la puissance d’Aspose.GIS :

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Étape 1 : Ouvrir et recadrer la couche (recadrer le raster avec un polygone)
Commencez par ouvrir la couche GeoTiff et la recadrer en fonction d’un polygone défini. Cela garantit que vos données géospatiales sont affinées à une zone d’intérêt précise.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Étape 2 : Récupérer les informations du raster (extraire la des cellules du raster & récupérer l’étendue du raster)
Une fois la couche recadrée, extrayez les informations essentielles sur les données raster, telles que la taille des cellules, le système de référence spatiale et les limites.

```csharp
// read and print raster
var cellSize = warped.CellSize;
var extent = warped.GetExtent();
var spatialRefSys = warped.SpatialReferenceSystem;
var code = spatialRefSys == null ? "'no srs'" : spatialRefSys.EpsgCode.ToString();
var bounds = warped.Bounds;
```

## Étape 3 : Afficher les informations
Affichez les informations extraites pour comprendre l’impact du processus de recadrage sur vos données géospatiales.

```csharp
Console.WriteLine($"cellSize: {cellSize}");
Console.WriteLine($"source extent: {layer.GetExtent()}");
Console.WriteLine($"target extent: {extent}");
Console.WriteLine($"spatialRefSys: {code}");
Console.WriteLine($"bounds: {bounds}");
```

Répétez ces étapes autant que nécessaire pour affiner et adapter vos données géospatiales aux exigences spécifiques de votre projet.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
|Orientatione du polygone** | Assurez‑vous que le polygone WKT suit la règle de la main droite (sens anti‑horaire pour les anneaux extérieurs). |
| **Référence spatiale manquante** | Vérifiez que le GeoTiff source contient un CRS ; sinon, définissez‑en un manuellement avant le recadrage. |
| **Ralentissement des performances sur de très grands rasters** | Utilisez `layer.Crop` sur une copie à résolution réduite ou traitez le raster en tuiles. |

## Questions fréquemment posées
### Q : Une licence temporaire est‑ Aspose.GIS for .NET ?
R : Oui, vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Q : Où puis‑je trouver la documentation complète pour Aspose.GIS for .NET ?
R : La documentation est disponible [ici](https://reference.aspose.com/gis/net/).

### Q : Comment puis‑je obtenir du support ou rejoindre la communauté pour Aspose.GIS for .NET ?
R : Visitez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le support et l’engagement communautaire.

### Q : Puis‑je télécharger une version d’essai gratuite d’Aspose.GIS for .NET ?
R : Oui, vous pouvez télécharger un essai gratuit [ici](https://releases.aspose.com/).

### Q : Où puis‑je acheter Aspose.GIS for .NET ?
R : Vous pouvez acheter la bibliothèque [ici](https://purchase.aspose.com/buy).

### Q : Puis‑je recadrer plusieurs couches en une seule exécution ?
R : Oui—bouclez sur chaque couche et appliquez le même appel `Crop` avec la géométrie souhaitée.

### Q : L’API prend‑elle en charge d’autres formats raster (par ex., JPEG2000) ?
R : Aspose.GIS prend en charge tous les formats exposés par les pilotes GDAL sous‑jacent, y compris JPEG2000, PNG et bien d’autres.

## Conclusion
En suivant ce guide, vous savez maintenant **comment recadrer les entités de couche** efficacement avec Aspose.GIS for .NET. Vous pouvez facilement **recadrer un raster avec un polygone**, **extraire la taille des cellules du raster**, et **récupérer l’étendue du raster** pour répondre aux besoins de n’importe quel projet. Explorez d’autres API pour la reprojection, le style raster et l’analyse vectorielle afin de libérer tout le potentiel de vos flux de travail géospatiaux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose