---
date: 2026-01-10
description: Apprenez à lire les shapefiles en C# et à convertir un shapefile de polygone
  en linestring à l'aide d'Aspose.GIS pour .NET. Boostez votre développement GIS grâce
  à des instructions claires, étape par étape.
linktitle: Convert Polygon Shapefile to Linestring
second_title: Aspose.GIS .NET API
title: Lire un shapefile C# – Convertir un shapefile de polygone en linestring
url: /fr/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire un Shapefile C# – Convertir un Shapefile Polygone en Linestring

## Introduction
Si vous travaillez avec des systèmes d'information géographique (SIG) sous .NET, **read shapefile c#** est une première étape courante avant de pouvoir manipuler les données. Aspose.GIS rend ce processus simple, vous permettant de convertir un Shapefile Polygone en Linestring en quelques lignes de code seulement. Cette fonctionnalité est particulièrement utile lorsque vous devez extraire des entités linéaires à partir de jeux de données polygonaux pour des tâches telles que la planification d'itinéraires, l'analyse de réseaux ou la visualisation de données.

## Quick Answers
- **Quelle bibliothèque vous aide à lire shapefile c# ?** Aspose.GIS for .NET  
- **Pouvez‑vous convertir un polygone en ligne ?** Oui – utilisez `LineString` avec l'anneau extérieur du polygone.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise pour une utilisation en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Une version d’essai est‑elle disponible ?** Absolument – téléchargez une version d’essai gratuite depuis le site Aspose.

## What is “read shapefile c#”?
Lire un shapefile en C# signifie charger le fichier `.shp` en mémoire afin de pouvoir interroger, modifier ou transformer ses géométries. Aspose.GIS fournit une API simple qui abstrait les détails de bas niveau et vous permet de vous concentrer sur la logique SIG.

## Why convert polygon to line with Aspose.GIS?
- **Préserver la topologie** – la conversion conserve la frontière extérieure exacte de chaque polygone.  
- **Performance** – la bibliothèque est optimisée pour les grands ensembles de données, rendant les conversions par lots rapides.  
- **Flexibilité** – vous pouvez ensuite écrire les linestrings dans un autre shapefile, GeoJSON ou tout format supporté.

## Prerequisites
Avant de plonger dans le tutoriel, assurez‑vous d’avoir les éléments suivants :

- **Bibliothèque Aspose.GIS** – Téléchargez et installez la bibliothèque Aspose.GIS depuis le [website](https://releases.aspose.com/gis/net/).  
- **Données Shapefile** – Disposez d’un Polygon Shapefile prêt pour la conversion. Si vous n’en avez pas, vous pouvez trouver des données d’exemple ou créer les vôtres.  
- **Environnement de développement** – Configurez votre environnement de développement .NET avec les outils nécessaires (Visual Studio, .NET SDK, etc.).

## Import Namespaces
Dans votre code C#, vous devez importer les espaces de noms Aspose.GIS pour accéder aux classes et méthodes requises. Ajoutez les espaces de noms suivants au début de votre fichier de code :

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## How to convert shapefile from polygon to line?
Voici un guide étape par étape qui montre **comment convertir les données shapefile** d’un polygone en ligne à l’aide d’Aspose.GIS.

### Step 1: Set the Document Directory
```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```
Remplacez `"Your Document Directory"` par le chemin réel où se trouve votre shapefile.

### Step 2: Open the Source Shapefile
```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Cette ligne **ouvre le Shapefile Polygon source** afin que vous puissiez lire ses entités.

### Step 3: Create the Destination Linestring Shapefile
```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```
Ici nous **créons un nouveau Shapefile Linestring** qui stockera les géométries converties.

### Step 4: Iterate Through Source Features
```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```
La boucle parcourt chaque entité polygone du fichier original.

### Step 5: Convert Polygon to Linestring and Write to Destination
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Dans ce bloc nous **convertissons le polygone en ligne** (`LineString`) et ajoutons la nouvelle entité au shapefile de destination.

## Common Issues and Tips
- **Incohérence du système de coordonnées** – Assurez‑vous que les couches source et destination utilisent la même référence spatiale ; sinon, les lignes peuvent apparaître déplacées.  
- **Fichiers volumineux** – Lors du traitement de shapefiles très grands, envisagez de diffuser les entités plutôt que de les charger toutes en mémoire d’un coup.  
- **Géométries nulles** – Protégez‑vous contre les entités avec des géométries vides afin d’éviter les exceptions d’exécution.

## Frequently Asked Questions

**Q: Aspose.GIS est‑il compatible avec toutes les versions de .NET ?**  
R: Oui, Aspose.GIS prend en charge diverses versions de .NET, garantissant la compatibilité avec votre environnement de développement.

**Q: Puis‑je utiliser Aspose.GIS pour des projets commerciaux ?**  
R: Oui. Pour utiliser Aspose.GIS dans des projets commerciaux, envisagez d’acheter une licence [here](https://purchase.aspose.com/buy).

**Q: Existe‑t‑il des exemples ou de la documentation disponible ?**  
R: Oui, vous pouvez trouver une documentation complète et des exemples sur la [documentation page](https://reference.aspose.com/gis/net/).

**Q: Une version d’essai est‑elle disponible ?**  
R: Oui, vous pouvez explorer Aspose.GIS avec une version d’essai gratuite en visitant [this link](https://releases.aspose.com/).

**Q: Où puis‑je obtenir de l’aide ou du support ?**  
R: Visitez le [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) pour toute assistance ou question liée au support.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.GIS for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}