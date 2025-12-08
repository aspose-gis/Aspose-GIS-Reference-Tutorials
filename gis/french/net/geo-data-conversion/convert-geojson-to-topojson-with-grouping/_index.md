---
date: 2025-12-06
description: Apprenez à convertir du GeoJSON en TopoJSON avec regroupement, à définir
  l’attribut de nom d’objet et à regrouper les entités GeoJSON à l’aide d’Aspose.GIS
  pour .NET.
language: fr
linktitle: How to Convert GeoJSON to TopoJSON with Grouping using Aspose.GIS
second_title: Aspose.GIS .NET API
title: Comment convertir GeoJSON en TopoJSON avec regroupement à l'aide d'Aspose.GIS
url: /net/geo-data-conversion/convert-geojson-to-topojson-with-grouping/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment convertir GeoJSON en TopoJSON avec regroupement à l'aide d'Aspose.GIS

## Introduction

Dans ce tutoriel étape par étape, vous apprendrez **comment convertir des fichiers GeoJSON** en TopoJSON tout en regroupant les entités en fonction d'un attribut choisi. Utiliser l'API Aspose.GIS .NET rend la conversion rapide, fiable et entièrement contrôlable depuis votre code C#. Que vous construisiez un service de conversion GeoJSON ASP.NET ou un outil GIS de bureau, ce guide vous montre exactement ce que vous devez faire.

## Réponses rapides
- **Quelle bibliothèque gère la conversion ?** Aspose.GIS for .NET  
- **Combien de temps prend l'implémentation ?** Typiquement 5‑10 minutes pour une configuration de base  
- **Ai‑je besoin d'une licence pour la production ?** Oui, une licence commerciale est requise (essai gratuit disponible)  
- **Puis‑je regrouper les entités par n'importe quel attribut ?** Oui – définissez `ObjectNameAttribute` sur le champ que vous souhaitez utiliser pour le regroupement  
- **Le .NET Core est‑il pris en charge ?** Absolument – l'API fonctionne avec .NET Core, .NET 5/6 et le .NET Framework classique  

## Qu'est‑ce que GeoJSON et TopoJSON ?

GeoJSON est un format JSON largement utilisé pour encoder des entités géographiques telles que des points, des lignes et des polygones. TopoJSON étend GeoJSON en stockant la topologie (segments de ligne partagés) ce qui réduit la taille du fichier et améliore les performances de rendu pour les cartes complexes. Convertir entre eux est une étape courante lorsque vous avez besoin de données cartographiques compactes pour des visualisations web.

## Pourquoi regrouper les entités GeoJSON ?

Regrouper (`group geojson features`) vous permet d'organiser des géométries liées sous un même objet nommé dans le TopoJSON résultant. Ceci est particulièrement utile lorsque :
- Vous souhaitez créer des couches séparées pour différentes régions administratives.  
- Votre bibliothèque de cartographie front‑end attend des objets nommés pour le style ou l'interaction.  
- Vous devez réduire la duplication en partageant les frontières entre les entités adjacentes.

## Prérequis

Avant de commencer, assurez‑vous d'avoir les prérequis suivants :

1. **Aspose.GIS for .NET** – téléchargez et installez depuis le site officiel [ici](https://releases.aspose.com/gis/net/).  
2. **Environnement de développement** – Visual Studio, Visual Studio Code, ou tout IDE supportant C#.  
3. **Fichier GeoJSON d'exemple** – un fichier contenant les entités que vous souhaitez convertir.  

## Importer les espaces de noms

Tout d'abord, incluez les espaces de noms nécessaires dans votre projet :

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.TopoJson;
```

## Guide étape par étape

### Étape 1 : Définir les chemins de fichiers

Spécifiez où se trouve le GeoJSON source et où le TopoJSON doit être écrit :

```csharp
string sampleGeoJsonPath = "Your Document Directory" + "sample.geojson";
var outputFilePath = "Your Document Directory" + "convertedSampleWithGrouping_out.topojson";
```

> **Conseil pro :** utilisez `Path.Combine` pour construire des chemins multiplateformes si vous ciblez .NET Core.

### Étape 2 : Configurer les options de conversion (définir l'attribut de nom d'objet)

Créez une instance `ConversionOptions` et indiquez à Aspose.GIS comment regrouper les entités :

```csharp
var options = new ConversionOptions
{
    DestinationDriverOptions = new TopoJsonOptions
    {
        // Specify the attribute in GeoJSON layer by which we are going to group into objects
        ObjectNameAttribute = "group",
        // Specify the default object name for features with unknown attribute values
        DefaultObjectName = "unnamed",
    }
};
```

Remplacez `"group"` par le nom réel de la propriété dans votre GeoJSON que vous souhaitez utiliser pour le **regroupement des entités GeoJSON**. Le `DefaultObjectName` garantit que chaque entité se retrouve dans un objet TopoJSON, même si l'attribut est absent.

### Étape 3 : Effectuer la conversion (Convertir GeoJSON en TopoJSON)

Exécutez la conversion avec un appel API unique :

```csharp
VectorLayer.Convert(sampleGeoJsonPath, Drivers.GeoJson, outputFilePath, Drivers.TopoJson, options);
```

Après l'exécution, `convertedSampleWithGrouping_out.topojson` contiendra la représentation TopoJSON, avec les entités regroupées selon l'attribut que vous avez spécifié.

## Problèmes courants et dépannage

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| **Toutes les entités se retrouvent dans « unnamed »** | `ObjectNameAttribute` ne correspond à aucune propriété du GeoJSON | Vérifiez le nom exact de la propriété (sensible à la casse) et mettez à jour l'option |
| **Le fichier de sortie est vide** | Chemin de fichier incorrect ou permissions de lecture manquantes | Utilisez des chemins absolus ou assurez‑vous que l'application a accès au système de fichiers |
| **La conversion lève `NotSupportedException`** | Tentative de conversion d'un GeoJSON contenant des types de géométrie non pris en charge (par ex., GeometryCollection) | Simplifiez les données sources ou mettez à jour vers la dernière version d'Aspose.GIS |

## Questions fréquentes

**Q : Puis‑je regrouper les entités en fonction de plusieurs attributs ?**  
R : Oui, vous pouvez concaténer plusieurs champs en un seul attribut virtuel ou exécuter plusieurs passes de conversion avec différentes valeurs de `ObjectNameAttribute`.

**Q : Aspose.GIS est‑il compatible avec ASP.NET Core ?**  
R : Absolument – la bibliothèque fonctionne avec ASP.NET Core, .NET 5, .NET 6 et le .NET Framework classique.

**Q : Puis‑je convertir d'autres formats géographiques en plus de GeoJSON ?**  
R : Oui, Aspose.GIS prend en charge Shapefile, KML, GML, CSV et bien d’autres formats, tant pour l’import que pour l’export.

**Q : Aspose.GIS propose‑t‑il un essai gratuit ?**  
R : Oui, vous pouvez obtenir un essai gratuit d'Aspose.GIS depuis [ici](https://releases.aspose.com/).

**Q : Où puis‑je obtenir du support pour Aspose.GIS ?**  
R : Vous pouvez obtenir du support sur le forum communautaire Aspose.GIS [ici](https://forum.aspose.com/c/gis/33).

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-06  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose