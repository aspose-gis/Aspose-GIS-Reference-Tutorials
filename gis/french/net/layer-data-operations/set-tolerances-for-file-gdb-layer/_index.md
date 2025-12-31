---
date: 2025-12-31
description: Explorez Aspose.GIS pour .NET et apprenez à créer un jeu de données File GDB
  et à définir les tolérances sans effort grâce à un guide étape par étape. Améliorez
  vos applications .NET.
linktitle: Set Tolerances for File GDB Layer
second_title: Aspose.GIS .NET API
title: Créer un jeu de données File GDB et définir les tolérances d’une couche
url: /fr/net/layer-data-operations/set-tolerances-for-file-gdb-layer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un jeu de données File GDB et définir les tolérances pour une couche

## Introduction
Si vous avez besoin de **créer un jeu de données file GDB** et de contrôler sa précision, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons l’ensemble du processus—en commençant par configurer votre projet .NET, créer un jeu de données File Geodatabase (GDB), puis appliquer les tolérances XY, Z et M à une nouvelle couche. À la fin, vous disposerez d’un jeu de données prêt à l’emploi qui fonctionne sans problème avec les outils ArcGIS et autres applications SIG.

## Quick Answers
- **Que signifie « créer un jeu de données file GDB » ?** Cela crée un nouveau conteneur File Geodatabase sur le disque pouvant contenir plusieurs couches SIG.  
- **Pourquoi définir des tolérances ?** Les tolérances définissent la précision des opérations géométriques, évitant les erreurs d’arrondi dans l’analyse spatiale.  
- **Quelle classe Aspose.GIS est utilisée ?** `Dataset.Create` avec `FileGdbOptions`.  
- **Ai‑je besoin d’une licence pour le développement ?** Une licence temporaire suffit pour les tests ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is a File GDB Dataset?
Un File Geodatabase (GDB) est un magasin de données basé sur un dossier qui contient des couches SIG, des tables et des relations. En utilisant Aspose.GIS, vous pouvez **créer un jeu de données file GDB** de manière programmatique sans avoir besoin d’ArcGIS installé, ce qui le rend idéal pour les pipelines automatisés ou les applications personnalisées.

## Why set tolerances for a layer?
Définir des tolérances garantit que les calculs géométriques (comme les intersections, le buffering ou le snapping) respectent la précision dont vous avez besoin. Ceci est particulièrement important lorsqu’on travaille avec des données à haute résolution ou lors de l’exportation vers d’autres plateformes SIG qui attendent des valeurs de tolérance spécifiques.

## Prerequisites
Avant de plonger dans le code, assurez‑vous d’avoir les éléments suivants :

- **Aspose.GIS for .NET Library** – Téléchargez et installez la bibliothèque Aspose.GIS depuis le [download link](https://releases.aspose.com/gis/net/). Si vous ne l’avez pas encore obtenue, vous pouvez explorer davantage la bibliothèque dans la [documentation](https://reference.aspose.com/gis/net/).
- **Development Environment** – Visual Studio, Rider ou tout IDE supportant le développement .NET.
- **A valid license** – Utilisez une licence temporaire pour les tests ou une licence complète pour la production (voir les liens dans la section FAQ).

Maintenant que tout est prêt, importons les espaces de noms dont nous aurons besoin.

## Import Namespaces
Dans votre application .NET, incluez les espaces de noms suivants pour exploiter les fonctionnalités d’Aspose.GIS :

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

## Step‑by‑Step Guide

### Step 1: Define Your Document Directory
Tout d’abord, indiquez dans le code le dossier où vous souhaitez créer le File GDB :

```csharp
string dataDir = "Your Document Directory";
```

> **Astuce :** Utilisez `Path.Combine` si vous devez construire le chemin de manière indépendante de la plateforme.

### Step 2: Create a File GDB Dataset
Nous **créons maintenant le jeu de données file GDB** sur le disque. La méthode `Dataset.Create` prend le chemin complet et le type de pilote (`Drivers.FileGdb`).

```csharp
var path = dataDir + "TolerancesForFileGdbLayer_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

> Le bloc `using` garantit que le jeu de données est correctement fermé et vidé sur le disque une fois terminé.

### Step 3: Set Tolerances using `FileGdbOptions`
Avant de créer une couche, définissez les tolérances dont vous avez besoin. `FileGdbOptions` vous permet de spécifier les tolérances XY, Z et M.

```csharp
var options = new FileGdbOptions
{
    XYTolerance = 0.001,
    ZTolerance = 0.1,
    MTolerance = 0.1,
};
```

Ces valeurs sont typiques pour des données d’ingénierie à haute précision, mais vous pouvez les ajuster selon votre projet.

### Step 4: Create a Layer with the Specified Tolerances
Enfin, créez une nouvelle couche à l’intérieur du jeu de données, en passant l’objet d’options que nous venons de configurer.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options))
{
    // The layer is created with the provided tolerances, ready for use in ArcGIS features/tools.
}
```

Lorsque le bloc `using` se termine, la couche est enregistrée avec les tolérances que vous avez définies.

## Common Issues & Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Chemin du jeu de données introuvable** | La variable `dataDir` pointe vers un dossier qui n’existe pas. | Assurez‑vous que le répertoire existe ou créez‑le avec `Directory.CreateDirectory(dataDir)`. |
| **Valeurs de tolérance invalides** | Les tolérances doivent être des nombres non négatifs. | Utilisez des valeurs positives ; évitez zéro sauf si vous souhaitez explicitement aucune tolérance. |
| **Erreur de licence** | Une licence d’essai ou temporaire a expiré. | Appliquez une nouvelle licence temporaire ou passez à une licence complète. |

## Frequently Asked Questions

**Q : Puis‑je utiliser Aspose.GIS pour .NET avec d’autres bibliothèques SIG ?**  
R : Oui, Aspose.GIS prend en charge l’interopérabilité, vous permettant de l’intégrer avec des bibliothèques telles que NetTopologySuite ou GDAL.

**Q : Existe‑t‑il une version d’essai disponible pour Aspose.GIS pour .NET ?**  
R : Absolument ! Vous pouvez explorer les fonctionnalités avec la [free trial version](https://releases.aspose.com/).

**Q : Comment puis‑je obtenir du support pour Aspose.GIS pour .NET ?**  
R : Visitez le [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) pour rejoindre la communauté et demander de l’aide.

**Q : Ai‑je besoin d’une licence temporaire à des fins de test ?**  
R : Oui, vous pouvez obtenir une [temporary license](https://purchase.aspose.com/temporary-license/) pour les tests et l’évaluation.

**Q : Où puis‑je acheter la licence Aspose.GIS pour .NET ?**  
R : Vous pouvez acheter la licence depuis la [buy page](https://purchase.aspose.com/buy).

## Conclusion
Dans ce guide, nous avons vu comment **créer un jeu de données file GDB**, configurer les tolérances géométriques et enregistrer une couche prête à l’emploi avec Aspose.GIS pour .NET. Ces étapes vous offrent un contrôle précis des données spatiales, rendant vos applications SIG plus fiables et interopérables.

---  
**Last Updated:** 2025-12-31  
**Tested With:** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}