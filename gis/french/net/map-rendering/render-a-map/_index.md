---
date: 2026-01-18
description: Apprenez comment ajouter des villes à la carte et générer une carte SVG
  en utilisant Aspose.GIS pour .NET. Créez rapidement des visualisations époustouflantes.
linktitle: Render a Map
second_title: Aspose.GIS .NET API
title: Comment ajouter des villes à la carte avec Aspose.GIS pour .NET
url: /fr/net/map-rendering/render-a-map/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter des villes à une carte avec Aspose.GIS pour .NET

## Introduction
Bienvenue dans le monde passionnant d'Aspose.GIS pour .NET ! Dans ce guide étape par étape, vous apprendrez **comment ajouter des villes à une carte** et générer une sortie SVG de haute qualité. Que vous construisiez un tableau de bord de bureau ou un portail GIS basé sur le web, ce tutoriel vous montre comment dessiner des couches vectorielles, définir les dimensions de la carte et charger une carte GeoJSON en toute simplicité.

## Réponses rapides
- **Quel est le sujet de ce tutoriel ?** Ajouter des villes à une carte et l'exporter sous forme de fichier SVG.  
- **Quelle bibliothèque est requise ?** Aspose.GIS pour .NET.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit est disponible ; une licence est requise pour la production.  
- **Puis‑je l’utiliser dans des applications web ?** Oui – le même code fonctionne avec ASP.NET, Blazor et d’autres frameworks web .NET.  
- **Quel format de sortie est produit ?** Une carte SVG qui peut être affichée dans les navigateurs ou éditée davantage.

## Prérequis
Avant de plonger dans le tutoriel, assurez‑vous d’avoir les prérequis suivants :
- Bibliothèque Aspose.GIS pour .NET : Assurez‑vous d’avoir installé la bibliothèque Aspose.GIS pour .NET. Vous pouvez la télécharger [ici](https://releases.aspose.com/gis/net/).
- Fichiers de données : Préparez les shapefiles et les données GeoJSON nécessaires au tutoriel. Vous pouvez trouver des données d’exemple dans la documentation ou utiliser vos propres fichiers.
- Environnement de développement : Disposez d’un environnement de développement .NET configuré, incluant un éditeur de code tel que Visual Studio.

## Importer les espaces de noms
Pour commencer, importez les espaces de noms requis dans votre projet .NET. Ces espaces de noms sont essentiels pour travailler avec les fonctionnalités d’Aspose.GIS.

```csharp
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.Drawing.Text;
using System.IO;
using System.Linq;
```

## Étape 1 : Configurer la carte (définir les dimensions de la carte)
```csharp
string dataDir = "Your Document Directory";
using (var map = new Map(800, 476))
{
    // Additional code for map setup can be added here.
}
```
Dans cette étape, nous initialisons une nouvelle carte avec une largeur de 800 pixels et une hauteur de 476 pixels. Ajustez les dimensions selon les exigences de votre conception.

## Étape 2 : Ajouter une carte de base (dessiner une couche vectorielle)
```csharp
var baseMapSymbolizer = new SimpleFill { FillColor = Color.Salmon, StrokeWidth = 0.75 };
map.Add(VectorLayer.Open(dataDir + "basemap.shp", Drivers.Shapefile), baseMapSymbolizer);
```
Ici, nous **dessinons une couche vectorielle** pour la carte de base en utilisant un shapefile. N’hésitez pas à modifier les propriétés `SimpleFill` pour correspondre à votre style visuel.

## Étape 3 : Ajouter des villes à la carte (ajouter des villes à la carte, charger une carte GeoJSON)
```csharp
var citiesSymbolizer = new SimpleMarker() { FillColor = Color.LightBlue };
citiesSymbolizer.FeatureBasedConfiguration = (feature, symbolizer) =>
{
    // Additional configuration logic can be added here.
};
map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), citiesSymbolizer);
```
Cette étape charge un fichier GeoJSON contenant des données de points de villes et **ajoute des villes à la carte**. Vous pouvez enrichir le délégué `FeatureBasedConfiguration` pour styliser les villes en fonction d’attributs tels que la population.

## Étape 4 : Rendre la carte (exporter la carte en SVG, générer une carte SVG)
```csharp
map.Render(dataDir + "cities_out.svg", Renderers.Svg);
```
Enfin, nous **exportons la carte au format SVG**. Le fichier `cities_out.svg` résultant peut être ouvert dans n’importe quel navigateur moderne ou éditeur de graphiques vectoriels.

## Conclusion
Félicitations ! Vous avez réussi à **ajouter des villes à une carte** et à générer une carte SVG en utilisant Aspose.GIS pour .NET. Ce tutoriel a démontré comment définir les dimensions de la carte, dessiner des couches vectorielles, charger des données GeoJSON et exporter le résultat sous forme de SVG évolutif—parfait pour les scénarios web et impression.

## FAQ
### Puis‑je utiliser Aspose.GIS pour .NET dans mes applications web ?
Oui, Aspose.GIS pour .NET convient aussi bien aux applications de bureau qu’aux applications web.

### Une version d’essai est‑elle disponible ?
Oui, vous pouvez explorer la version d’essai gratuite [ici](https://releases.aspose.com/).

### Où puis‑je trouver du support pour Aspose.GIS pour .NET ?
Visitez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour toute assistance ou question.

### Puis‑je acheter une licence temporaire pour des projets à court terme ?
Oui, une licence temporaire est disponible [ici](https://purchase.aspose.com/temporary-license/).

### Existe‑t‑il d’autres tutoriels disponibles pour Aspose.GIS pour .NET ?
Oui, consultez la [documentation](https://reference.aspose.com/gis/net/) pour des tutoriels et guides complets.

---

**Dernière mise à jour :** 2026-01-18  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}