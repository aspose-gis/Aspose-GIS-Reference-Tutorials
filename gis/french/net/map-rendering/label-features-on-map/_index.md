---
title: Maîtriser l'étiquetage des fonctionnalités avec Aspose.GIS pour .NET
linktitle: Étiqueter les entités sur la carte
second_title: API Aspose.GIS .NET
description: Explorez Aspose.GIS pour .NET et maîtrisez l'art de l'étiquetage des entités sur les cartes. Améliorez vos visualisations géospatiales sans effort. #Aspose #SIG
type: docs
weight: 11
url: /fr/net/map-rendering/label-features-on-map/
---
## Introduction
Dans le monde de la visualisation de données géospatiales, l’étiquetage des entités sur une carte joue un rôle crucial dans la transmission efficace des informations. Aspose.GIS for .NET fournit une boîte à outils puissante pour y parvenir de manière transparente. Dans ce didacticiel, nous explorerons différentes méthodes d'étiquetage de points sur une carte à l'aide d'Aspose.GIS, améliorant ainsi vos visualisations de carte avec des étiquettes informatives.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Une connaissance pratique de C# et du framework .NET.
-  Aspose.GIS pour .NET installé. Vous pouvez le télécharger[ici](https://releases.aspose.com/gis/net/).
- Un fichier GeoJSON contenant des données de points. Si vous n'en avez pas, vous pouvez utiliser un exemple de fichier pour tester.
## Importer des espaces de noms
Dans votre code C#, assurez-vous d'importer les espaces de noms nécessaires pour travailler avec Aspose.GIS :
```csharp
using System;
using System.Drawing;
using Aspose.Gis;
using Aspose.Gis.Rendering;
using Aspose.Gis.Rendering.Labelings;
using Aspose.Gis.Rendering.Symbolizers;
using Aspose.GIS.Examples.CSharp;
using FontStyle = Aspose.Gis.Rendering.Labelings.FontStyle;
```
Maintenant, décomposons chaque exemple en plusieurs étapes dans un format de guide étape par étape.
##  Étiquetage des points

### Étape 1 : Définissez le chemin d'accès à votre répertoire de documents :
```csharp
string dataDir = "Your Document Directory";
```
### Étape 2 : Créez une carte avec un simple symbole de marqueur :
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Ajoutez un calque vectoriel et appliquez l'étiquetage
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Rendre la carte dans un fichier SVG
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```
## Style d'étiquetage des points

Suivez les étapes 1 et 2 de l’exemple précédent.

### Étape 1 : Personnalisez le style d'étiquetage :
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Le reste des étapes reste le même
```
## Points d'étiquetage placés

Suivez les étapes 1 et 2 du premier exemple.
### Étape 2 : Personnalisez l'emplacement de l'étiquette :
```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        HorizontalOffset = 2,
        VerticalOffset = 2,
        Rotation = 10,
    }
};
// Le reste des étapes reste le même
```
## Basé sur la fonctionnalité d'étiquetage des points

Suivez les étapes 1 et 2 du premier exemple.

### Étape 1 : Mettre en œuvre un étiquetage basé sur les fonctionnalités :
```csharp
var pointLabeling = new SimpleLabeling("name")
{
    HaloSize = 1,
    Placement = new PointLabelPlacement
    {
        VerticalAnchorPoint = VerticalAnchor.Bottom,
        HorizontalAnchorPoint = HorizontalAnchor.Left,
        VerticalOffset = 4,
        HorizontalOffset = 4,
    },
    FeatureBasedConfiguration = (feature, labeling) =>
    {
        // Récupérez la population de la fonctionnalité.
        var population = feature.GetValue<int>("population");
        // La taille de la police est calculée et basée sur la population.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // La priorité du label repose également sur la population.
        // Plus la priorité est élevée, plus l'étiquette est susceptible d'apparaître sur l'image de sortie.
        labeling.Priority = population;
    }
};
// Le reste des étapes reste le même
```
## Conclusion
Toutes nos félicitations! Vous avez appris à améliorer vos visualisations cartographiques en étiquetant les entités à l'aide d'Aspose.GIS pour .NET. Expérimentez avec différents styles et emplacements pour créer des cartes attrayantes adaptées à vos données.
## FAQ
### Puis-je étiqueter des entités à l’aide de polices personnalisées ?
Oui, vous pouvez personnaliser le style et la taille de la police dans la configuration de l'étiquetage.
### Aspose.GIS est-il compatible avec d'autres formats de données SIG ?
Aspose.GIS prend en charge divers formats géospatiaux, notamment GeoJSON, Shapefile, etc.
### Comment puis-je gérer de grands ensembles de données pour l’étiquetage ?
Aspose.GIS est optimisé pour les performances, mais envisagez d'utiliser des configurations basées sur les fonctionnalités pour hiérarchiser les étiquettes en fonction des attributs de données.
### Existe-t-il des options avancées de placement d’étiquettes ?
Oui, vous pouvez affiner le placement des étiquettes à l'aide d'options telles que la rotation, les points d'ancrage et les décalages.
### Puis-je automatiser la génération d’étiquettes dans un processus par lots ?
Absolument, vous pouvez intégrer Aspose.GIS dans vos flux de travail automatisés pour la génération d'étiquettes par lots.