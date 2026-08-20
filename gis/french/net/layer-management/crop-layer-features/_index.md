---
date: 2026-07-05
description: Apprenez à rogner les entités de couche avec Aspose.GIS for .NET, y compris
  comment rogner un raster avec un polygone, extraire la taille des cellules du raster
  et récupérer l'étendue du raster. Téléchargez votre free trial maintenant.
keywords:
- how to crop layer
- extract raster extent
- get raster cell size
- crop raster layer
- crop raster with polygon
linktitle: Comment rogner les entités de couche
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to crop layer features with Aspose.GIS for .NET, including
    how to crop raster with polygon, extract raster cell size, and retrieve raster
    extent. Download your free trial now.
  headline: How to Crop Layer Features with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: Is a temporary license available for Aspose.GIS for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/gis/net/).
    question: Where can I find comprehensive documentation for Aspose.GIS for .NET?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for support
      and community engagement.
    question: How can I seek support or connect with the community for Aspose.GIS
      for .NET?
  - answer: Yes, you can download a free trial [here](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.GIS for .NET?
  - answer: You can purchase the library [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.GIS for .NET?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Comment rogner les entités de couche avec Aspose.GIS for .NET
url: /fr/net/layer-management/crop-layer-features/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment recadrer les fonctionnalités de couche

## Introduction
Dans ce tutoriel, vous apprendrez **comment recadrer une couche** à l'aide d'Aspose.GIS pour .NET, une bibliothèque puissante qui vous permet de **recadrer un raster avec un polygone**, **extraire la taille des cellules du raster**, et **récupérer l'étendue du raster** pour une analyse géospatiale précise. Que vous prépariez des données pour une carte web, que vous découpiez des images satellites ou que vous isoliez une région d'intérêt, ce guide étape par étape vous montre exactement comment accomplir la tâche rapidement et de manière fiable.

## Réponses rapides
- **Que signifie « recadrer une couche » ?** Cela découpe un raster ou une couche vectorielle aux limites d'une géométrie fournie, en éliminant tout ce qui se trouve à l'extérieur.  
- **Quelle géométrie est utilisée dans cet exemple ?** Un polygone défini au format WKT (Well‑Known Text).  
- **Puis‑je extraire la taille des cellules après le recadrage ?** Oui – la propriété `CellSize` renvoie la largeur et la hauteur d'une cellule raster.  
- **Ai‑je besoin d’une licence pour exécuter le code ?** Une licence temporaire suffit pour l'évaluation ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu'est‑ce que « recadrer une couche » ?
**Recadrer une couche consiste à restreindre l’ensemble de données à une zone géographique spécifique, en éliminant tout ce qui se trouve à l'extérieur.** Cette opération réduit la taille du fichier, accélère les traitements ultérieurs et concentre l'analyse sur la région qui vous intéresse. En limitant les données à la zone d'intérêt, vous simplifiez également les flux de travail en aval tels que le style, l'analyse et la publication, tout en préservant le système de référence de coordonnées et les métadonnées d'origine.

## Pourquoi utiliser Aspose.GIS pour le recadrage ?
**Aspose.GIS traite les fichiers raster jusqu'à 2 Go sans charger l'image complète en mémoire et prend en charge plus de 30 formats raster, dont GeoTIFF, JPEG2000 et PNG.** La bibliothèque offre un appel `Crop` en une seule ligne, une gestion automatique du CRS et des performances multithread qui peuvent découper un GeoTIFF de 500 Mo en moins d'une seconde sur un serveur standard.

## Prérequis
Avant de plonger dans la manipulation géospatiale, assurez‑vous d’avoir les prérequis suivants :

- Bibliothèque Aspose.GIS pour .NET : assurez‑vous que la bibliothèque Aspose.GIS est installée dans votre projet .NET. Vous pouvez la télécharger [ici](https://releases.aspose.com/gis/net/).  
- Répertoire de documents : créez un répertoire pour stocker vos documents. Remplacez `"Your Document Directory"` dans le code fourni par le chemin réel de votre répertoire de documents.

Maintenant, plongeons dans le guide étape par étape.

## Importer les espaces de noms
L’espace de noms `Aspose.Gis` contient tous les types de base pour la gestion des rasters et des vecteurs. Importez‑le pour accéder aux classes `Layer`, `Geometry` et aux classes associées.

```csharp
using System;
using System.IO;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Comment recadrer une couche avec un polygone ?
`Crop` est une méthode de la classe `Layer` qui extrait un sous‑ensemble raster défini par une géométrie.  
Chargez le raster source, définissez une géométrie polygone, puis appelez la méthode `Crop` — l’opération complète s’effectue en une seule ligne de code. La méthode renvoie un nouveau raster contenant uniquement les pixels à l’intérieur du polygone, en préservant automatiquement la référence spatiale d’origine.

## Étape 1 : Ouvrir et recadrer la couche (recadrer le raster avec un polygone)
`Layer` représente un jeu de données raster qui peut être ouvert, interrogé et modifié.  
La classe `Layer` représente un jeu de données raster qui peut être ouvert, interrogé et modifié. Ouvrir un GeoTIFF et le recadrer avec un polygone isole la zone d’intérêt en quelques instructions seulement.

```csharp
using (var layer = Drivers.GeoTiff.OpenLayer(Path.Combine(filesPath, "geodetic_world.tif")))
using (var warped = layer.Crop(Geometry.FromText("POLYGON ((-160 0, 0 60, 160 0, 0 -160, -160 0))")))
{
```

## Étape 2 : Récupérer les informations du raster (extraire la taille des cellules du raster & récupérer l'étendue du raster)
`CellSize` fournit la largeur et la hauteur de chaque cellule raster en unités de coordonnées.  
`Extent` renvoie la boîte englobante géographique du raster.  
La propriété `CellSize` fournit la largeur et la hauteur de chaque cellule raster en unités de coordonnées, tandis que la propriété `Extent` renvoie la boîte englobante géographique du raster recadré. Ces deux informations sont essentielles pour les calculs en aval tels que la mesure de surface ou la reprojection.

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

Répétez ces étapes selon les besoins pour affiner et adapter vos données géospatiales aux exigences spécifiques de votre projet.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Orientation incorrecte du polygone** | Assurez‑vous que le polygone WKT suit la règle de la main droite (sens antihoraire pour les anneaux extérieurs). |
| **Référence spatiale manquante** | Vérifiez que le GeoTiff source contient un CRS ; sinon, définissez‑en un manuellement avant le recadrage. |
| **Ralentissement des performances sur de très grands rasters** | Utilisez `layer.Crop` sur une copie à résolution réduite ou traitez le raster par tuiles. |

## Questions fréquentes
**Q : Une licence temporaire est‑elle disponible pour Aspose.GIS pour .NET ?**  
R : Oui, vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Où puis‑je trouver la documentation complète d’Aspose.GIS pour .NET ?**  
R : La documentation est disponible [ici](https://reference.aspose.com/gis/net/).

**Q : Comment obtenir du support ou rejoindre la communauté d’Aspose.GIS pour .NET ?**  
R : Visitez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le support et l’engagement communautaire.

**Q : Puis‑je télécharger une version d’essai gratuite d’Aspose.GIS pour .NET ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite [ici](https://releases.aspose.com/).

**Q : Où puis‑je acheter Aspose.GIS pour .NET ?**  
R : Vous pouvez acheter la bibliothèque [ici](https://purchase.aspose.com/buy).

**Q : Puis‑je recadrer plusieurs couches en une seule exécution ?**  
R : Oui — bouclez sur chaque couche et appliquez le même appel `Crop` avec la géométrie souhaitée.

**Q : L’API prend‑elle en charge d’autres formats raster (par ex., JPEG2000) ?**  
R : Aspose.GIS prend en charge tous les formats exposés par les pilotes GDAL sous‑jacents, y compris JPEG2000, PNG et bien d’autres.

## Conclusion
En suivant ce guide, vous savez maintenant **comment recadrer une couche** efficacement avec Aspose.GIS pour .NET. Vous pouvez facilement **recadrer un raster avec un polygone**, **extraire la taille des cellules du raster**, et **récupérer l'étendue du raster** pour répondre aux besoins de tout projet. Explorez d’autres API pour la reprojection, le style raster et l’analyse vectorielle afin de libérer tout le potentiel de vos flux de travail géospatiaux.

---

**Last Updated:** 2026-07-05  
**Tested With:** Aspose.GIS 24.10 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment créer une géométrie de polygone avec Aspose.GIS pour .NET](/gis/net/geometry-creation/create-polygon-geometry/)
- [Obtenir les attributs de couche – Récupérer les informations d'attribut de couche avec Aspose.GIS pour .NET](/gis/net/layer-interaction-and-data-access/get-layer-attribute-information/)
- [Créer une géométrie de polygone C# et vérifier l'intersection avec Aspose.GIS pour .NET](/gis/net/geometry-analysis/check-geometries-intersection/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}