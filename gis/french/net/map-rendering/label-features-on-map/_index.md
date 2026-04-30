---
date: 2026-01-15
description: Apprenez à étiqueter les entités cartographiques à l'aide d'Aspose.GIS
  pour .NET, avec des options de style d'étiquette personnalisées pour le libellé
  de grands ensembles de données.
linktitle: Label Features on Map
second_title: Aspose.GIS .NET API
title: Étiqueter les entités cartographiques avec Aspose.GIS pour .NET
url: /fr/net/map-rendering/label-features-on-map/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fonctionnalités d'étiquetage des entités cartographiques avec Aspose.GIS pour .NET

## Introduction
L'étiquetage des entités cartographiques est essentiel pour transformer des données géospatiales brutes en visualisations claires et conviviales. Dans ce tutoriel, vous découvrirez **comment étiqueter les entités cartographiques** (le mot‑clé principal) à l'aide d'Aspose.GIS pour .NET, explorerez les styles d'étiquettes personnalisés et verrez des techniques qui fonctionnent même avec de grands ensembles de données. À la fin, vous serez capable d'ajouter du texte informatif directement sur vos cartes, les rendant plus instructives pour les analystes et les utilisateurs finaux.

## Réponses rapides
- **Quelle est la classe principale pour le rendu ?** `Map` (Aspose.Gis.Rendering)
- **Quelle classe d'étiquetage ajoute du texte simple ?** `SimpleLabeling`
- **Puis‑je styliser les étiquettes (halo, police, rotation) ?** Oui – via des propriétés comme `HaloSize`, `FontStyle` et `Placement`
- **Comment gérer de grands ensembles de données ?** Utilisez `FeatureBasedConfiguration` pour prioriser les étiquettes en fonction des valeurs d'attributs
- **Ai‑je besoin d'une licence ?** Une version d'essai fonctionne pour le développement ; une licence commerciale est requise pour la production

## Qu'est‑ce que l'étiquetage des entités cartographiques ?
`label map features` signifie attacher du texte lisible (tel que des noms de villes, des chiffres de population ou des identifiants personnalisés) aux objets géométriques — points, lignes ou polygones—afin que la carte transmette à la fois les informations spatiales et attributaires d'un seul coup d'œil.

## Pourquoi utiliser Aspose.GIS pour l'étiquetage des entités cartographiques ?
- **Aucune dépendance externe** – bibliothèque .NET pure, aucune binaire GIS native requise.  
- **Options de style riches** – halos, polices personnalisées, rotation et points d’ancrage vous permettent d’ajuster finement l’apparence.  
- **Conçu pour la performance** – l’étiquetage basé sur les entités intégré vous permet de prioriser les étiquettes les plus importantes lors du rendu de grands ensembles de données.  
- **Multiples formats de sortie** – SVG, PNG, PDF, etc., avec des résultats d’étiquetage cohérents.

## Prérequis
Avant de commencer, assurez‑vous de disposer de :

- Une connaissance pratique du C# et du framework .NET.  
- Aspose.GIS pour .NET installé. Vous pouvez le télécharger **[ici](https://releases.aspose.com/gis/net/)**.  
- Un fichier GeoJSON contenant des données ponctuelles (ou tout autre format vectoriel pris en charge).  

## Importer les espaces de noms
Dans votre code C#, importez les espaces de noms requis :

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

Nous allons maintenant parcourir plusieurs scénarios d'étiquetage, chacun s’appuyant sur le précédent.

## Étiquetage de points – Comment étiqueter des points
### Étape 1 : Définir le chemin vers votre répertoire de documents
```csharp
string dataDir = "Your Document Directory";
```

### Étape 2 : Créer une carte avec un symbole de marqueur simple
```csharp
using (var map = new Map(500, 200))
{
    var symbol = new SimpleMarker
    {
        FillColor = Color.LightGray,
        StrokeStyle = StrokeStyle.None
    };
    var labeling = new SimpleLabeling(labelAttribute: "name");
    // 3. Add a vector layer and apply labeling
    map.Add(VectorLayer.Open(dataDir + "points.geojson", Drivers.GeoJson), symbol, labeling);
    map.Padding = 50;
    // 4. Render the map to an SVG file
    map.Render(dataDir + "points_labeling_out.svg", Renderers.Svg);
}
```

Dans cet exemple de base nous **how to label points** en utilisant l'attribut `name` du fichier GeoJSON.

## Étiquetage de points stylisé – Style d'étiquette personnalisé
Suivez les étapes 1 et 2 de l'exemple précédent, puis personnalisez le style d'étiquetage :

```csharp
var labeling = new SimpleLabeling(labelAttribute: "name")
{
    HaloSize = 2,
    HaloColor = Color.LightGray,
    FontSize = 15,
    FontStyle = FontStyle.Italic,
};
// Rest of the steps remain the same
```

Le halo ajouté et la police italique donnent aux étiquettes un **custom label style** qui se démarque sur des arrière‑plans chargés.

## Étiquetage de points avec placement – Options de placement avancées
Reprenez les étapes 1 et 2 du premier exemple, puis ajustez le placement :

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
// Rest of the steps remain the same
```

Ici nous contrôlons les points d’ancrage, les décalages et la rotation, vous offrant un contrôle granulaire sur **how to label points** dans des zones cartographiques encombrées.

## Étiquetage de points basé sur les entités – Étiquetage de grands ensembles de données
Lorsque vous traitez de nombreux points, vous pouvez vouloir prioriser les étiquettes selon un attribut tel que la population. Suivez les étapes 1 et 2 du premier exemple, puis implémentez l'étiquetage basé sur les entités :

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
        // Retrieve population from the feature.
        var population = feature.GetValue<int>("population");
        // Font size is computed and is based on the population.
        labeling.FontSize = Math.Min(20, 5 * population / 1000);
        // Priority of the label is also based on the population.
        // The greater the priority is, the more likely label will appear on the output image.
        labeling.Priority = population;
    }
};
// Rest of the steps remain the same
```

Cette stratégie **large dataset labeling** garantit que les villes les plus importantes (par population) sont affichées en premier, tandis que les points moins critiques peuvent être omis lorsque l’espace est limité.

## Conclusion
Félicitations ! Vous savez maintenant plusieurs façons **d'étiqueter les entités cartographiques** avec Aspose.GIS pour .NET — du simple étiquetage de points au style sophistiqué basé sur les entités pour de grands ensembles de données. Expérimentez avec les halos, les rotations et les règles de priorité pour créer des cartes qui communiquent exactement ce que votre audience doit voir.

## Foire aux questions

**Q : Puis‑je étiqueter les entités avec des polices personnalisées ?**  
R : Oui. Définissez `FontFamily` et `FontStyle` dans la configuration `SimpleLabeling` pour utiliser n’importe quelle police installée.

**Q : Aspose.GIS est‑il compatible avec d’autres formats de données GIS ?**  
R : Absolument. Il prend en charge GeoJSON, Shapefile, KML, GML et bien d’autres formats.

**Q : Comment gérer de grands ensembles de données pour l'étiquetage ?**  
R : Utilisez `FeatureBasedConfiguration` pour attribuer des priorités et ajuster dynamiquement les tailles de police en fonction des valeurs d’attributs, comme montré dans l’exemple basé sur les entités.

**Q : Existe‑t‑il des options avancées de placement d’étiquettes ?**  
R : Oui. Vous pouvez affiner le placement avec `PointLabelPlacement`, en ajustant les points d’ancrage, les décalages et la rotation.

**Q : Puis‑je automatiser la génération d’étiquettes dans un processus batch ?**  
R : Bien sûr. Enveloppez le code de rendu de la carte dans une boucle ou un service en arrière‑plan pour traiter automatiquement plusieurs couches ou fichiers.

---

**Dernière mise à jour :** 2026-01-15  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}