---
date: 2026-01-10
description: Apprenez à convertir GeoJSON en File GDB avec Aspose.GIS pour .NET. Ce
  guide étape par étape couvre la conversion de données géospatiales et la conversion
  Aspose GIS.
linktitle: Convert GeoJSON Layer to File GDB
second_title: Aspose.GIS .NET API
title: Comment convertir du GeoJSON en File GDB à l'aide d'Aspose.GIS pour .NET
url: /fr/net/layer-management/convert-geojson-layer-to-file-gdb/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment convertir GeoJSON en File GDB avec Aspose.GIS pour .NET

## Introduction
Si vous vous demandez **comment convertir GeoJSON** en une File Geodatabase (File GDB) pour des flux de travail GIS robustes, vous êtes au bon endroit. Dans ce tutoriel, nous vous guiderons à travers tout le processus avec Aspose.GIS pour .NET, en vous montrant pourquoi cette bibliothèque est un choix de premier plan pour la conversion de données géospatiales et comment vous pouvez rapidement créer une file geodatabase à partir d’une couche GeoJSON.

## Réponses rapides
- **Que couvre le tutoriel ?** Conversion d’une couche GeoJSON en File GDB avec Aspose.GIS pour .NET.  
- **Quel mot‑clé principal est ciblé ?** *how to convert geojson*.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour une conversion de base.

## Qu’est‑ce que GeoJSON et File GDB ?
GeoJSON est un format léger, basé sur du texte, pour encoder une variété de structures de données géographiques. Une File Geodatabase (File GDB) est un format basé sur des dossiers, à haute performance, utilisé par de nombreuses applications GIS de bureau. Convertir entre les deux vous permet de tirer parti des points forts de chaque format dans vos projets.

## Pourquoi utiliser Aspose.GIS pour la conversion de données géospatiales ?
Aspose.GIS offre une API unifiée qui masque les complexités de la gestion des formats. Avec le support intégré pour **geojson to file gdb**, vous pouvez :

- Lire du GeoJSON en C# sans analyseurs tiers.  
- Créer une file geodatabase de façon programmatique.  
- Conserver automatiquement les données d’attributs et les informations de référence spatiale.  

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

- Une bonne connaissance de la programmation .NET.  
- Aspose.GIS pour .NET installé. Sinon, téléchargez‑le depuis [here](https://releases.aspose.com/gis/net/) et suivez les instructions d’installation.

## Importer les espaces de noms
La première étape consiste à importer les espaces de noms requis.

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Étape 1 : Configurer la couche GeoJSON
Créez un fichier GeoJSON temporaire contenant les attributs et les entités que vous souhaitez convertir. Cet exemple ajoute deux entités ponctuelles simples.

```csharp
string dataDir = "Your Document Directory";
var geoJsonPath = dataDir + "ConvertGeoJsonLayerToLayerInFileGdbDataset_out.json";
using (VectorLayer layer = VectorLayer.Create(geoJsonPath, Drivers.GeoJson))
{
    // Add attributes
    layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
    layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
    // Construct and add features
    Feature firstFeature = layer.ConstructFeature();
    firstFeature.Geometry = new Point(33.97, -118.25);
    firstFeature.SetValue("name", "John");
    firstFeature.SetValue("age", 23);
    layer.Add(firstFeature);
    Feature secondFeature = layer.ConstructFeature();
    secondFeature.Geometry = new Point(35.81, -96.28);
    secondFeature.SetValue("name", "Mary");
    secondFeature.SetValue("age", 54);
    layer.Add(secondFeature);
}
```

## Étape 2 : Copier le jeu de données de test
Pour ne pas altérer les données de test d’origine, dupliquez le jeu de données File GDB existant. Cela garantit un environnement propre pour la conversion.

```csharp
var sourceFile = "Your Document Directory" + "ThreeLayers.gdb";
var destinationFile = "Your Document Directory" + "ThreeLayersCopy_out.gdb";
RunExamples.CopyDirectory(sourceFile, destinationFile);
```

## Étape 3 : Convertir GeoJSON en File GDB
Ouvrez la couche GeoJSON, créez une nouvelle couche dans le File GDB copié, copiez les attributs et transférez chaque entité. C’est le cœur du processus de **aspose gis conversion**.

```csharp
using (var geoJsonLayer = VectorLayer.Open(geoJsonPath, Drivers.GeoJson))
{
    using (var fileGdbDataset = Dataset.Open(destinationFile, Drivers.FileGdb))
    using (var fileGdbLayer = fileGdbDataset.CreateLayer("new_layer", SpatialReferenceSystem.Wgs84))
    {
        // Copy attributes
        fileGdbLayer.CopyAttributes(geoJsonLayer);
        // Add features
        foreach (var feature in geoJsonLayer)
        {
            fileGdbLayer.Add(feature);
        }
    }
}
```

## Problèmes courants et solutions
- **Référence spatiale manquante :** Assurez‑vous que le GeoJSON source inclut une définition CRS ou définissez explicitement `SpatialReferenceSystem.Wgs84` lors de la création de la couche File GDB.  
- **Incohérence de type d’attribut :** Les types de données d’attributs dans le GeoJSON doivent correspondre au schéma cible ; sinon, Aspose.GIS lèvera une exception.  
- **Erreurs d’accès aux fichiers :** Vérifiez que le dossier de destination possède les droits d’écriture et qu’aucun autre processus ne verrouille les fichiers GDB.

## Questions fréquemment posées
### Aspose.GIS est‑il compatible avec le dernier framework .NET ?
Oui, Aspose.GIS est compatible avec les dernières versions du framework .NET.  

### Puis‑je convertir d’autres formats géospatiaux avec Aspose.GIS ?
Absolument ! Aspose.GIS prend en charge un large éventail de formats géospatiaux pour une manipulation de données polyvalente.  

### Existe‑t‑il une version d’essai disponible pour Aspose.GIS ?
Oui, vous pouvez explorer les fonctionnalités d’Aspose.GIS en téléchargeant la version d’essai [here](https://releases.aspose.com/).  

### Comment obtenir du support pour les questions liées à Aspose.GIS ?
Rendez‑vous sur le [forum](https://forum.aspose.com/c/gis/33) Aspose.GIS pour un support dédié.  

### Puis‑je obtenir une licence temporaire pour Aspose.GIS ?
Oui, vous pouvez obtenir une licence temporaire [here](https://purchase.aspose.com/temporary-license/).  

---

**Dernière mise à jour :** 2026-01-10  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}