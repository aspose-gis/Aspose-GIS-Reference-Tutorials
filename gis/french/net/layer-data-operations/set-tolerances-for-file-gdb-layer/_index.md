---
date: 2026-04-30
description: Apprenez à créer des fichiers GDB avec Aspose.GIS pour .NET, à définir
  la précision des couches et à utiliser les options de fichier GDB pour contrôler
  les tolérances.
keywords:
- how to create gdb
- create gis layer
- how to set tolerances
- set layer precision
- file gdb options
linktitle: Définir les tolérances pour la couche File GDB
second_title: Aspose.GIS .NET API
title: Comment créer un jeu de données GDB et définir les tolérances pour une couche
url: /fr/net/layer-data-operations/set-tolerances-for-file-gdb-layer/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un jeu de données GDB et définir les tolérances pour une couche

## Introduction
Si vous devez **créer un jeu de données GDB de fichier** et contrôler sa précision, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons l’ensemble du processus — de la configuration de votre projet .NET, à la création d’un jeu de données File Geodatabase (GDB), puis à l’application des tolérances XY, Z et M à une nouvelle couche. À la fin, vous disposerez d’un jeu de données prêt à l’emploi qui fonctionne sans problème avec les outils ArcGIS et autres applications SIG. Ce guide vous montre **comment créer des fichiers gdb** de façon programmatique, afin que vous puissiez automatiser les pipelines de données sans intervention manuelle.

## Réponses rapides
- **Que signifie « créer un jeu de données GDB de fichier » ?** Cela crée un nouveau conteneur de géodatabase de fichier sur le disque pouvant contenir plusieurs couches GIS.  
- **Pourquoi définir des tolérances ?** Les tolérances définissent la précision des opérations géométriques, évitant les erreurs d'arrondi dans l'analyse spatiale.  
- **Quelle classe Aspose.GIS est utilisée ?** `Dataset.Create` avec `FileGdbOptions`.  
- **Ai‑je besoin d'une licence pour le développement ?** Une licence temporaire suffit pour les tests ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu’est‑ce qu’un jeu de données File GDB ?
Une File Geodatabase (GDB) est un magasin de données basé sur un dossier qui contient des couches GIS, des tables et des relations. Avec Aspose.GIS, vous pouvez **créer un jeu de données file GDB** de façon programmatique sans avoir besoin d’ArcGIS installé, ce qui le rend idéal pour les pipelines automatisés ou les applications personnalisées.

## Pourquoi définir des tolérances pour une couche ?
Définir des tolérances garantit que les calculs géométriques (intersections, buffers, snapping, etc.) respectent la précision requise. C’est particulièrement important avec des données haute résolution ou lors de l’exportation vers d’autres plateformes SIG qui attendent des valeurs de tolérance spécifiques. En d’autres termes, vous **définissez la précision de la couche** pour éviter des erreurs géométriques inattendues.

## Prérequis
Avant de plonger dans le code, assurez‑vous d’avoir les éléments suivants :

- **Bibliothèque Aspose.GIS pour .NET** – Téléchargez et installez la bibliothèque Aspose.GIS depuis le [lien de téléchargement](https://releases.aspose.com/gis/net/). Si vous ne l’avez pas encore obtenue, vous pouvez explorer davantage la bibliothèque dans la [documentation](https://reference.aspose.com/gis/net/).
- **Environnement de développement** – Visual Studio, Rider ou tout IDE supportant le développement .NET.
- **Une licence valide** – Utilisez une licence temporaire pour les tests ou une licence complète pour la production (voir les liens dans la section FAQ).

Maintenant que tout est prêt, importons les espaces de noms dont nous aurons besoin.

## Importer les espaces de noms
Dans votre application .NET, incluez les espaces de noms suivants pour exploiter les fonctionnalités d'Aspose.GIS :

```csharp
using Aspose.Gis;
using Aspose.Gis.Formats.FileGdb;
using Aspose.Gis.Geometries;
using Aspose.Gis.SpatialReferencing;
using System;
using System.Text;
```

Avec les espaces de noms en place, nous pouvons commencer à créer le jeu de données.

## Comment créer un jeu de données GDB ?
Voici le guide étape par étape qui vous accompagne dans la création du jeu de données et la configuration des tolérances.

### Étape 1 : Définir votre répertoire de documents
Tout d'abord, indiquez dans le code le dossier où vous souhaitez créer le File GDB :

```csharp
string dataDir = "Your Document Directory";
```

> **Astuce :** Utilisez `Path.Combine` si vous devez construire le chemin de manière indépendante de la plateforme.

### Étape 2 : Créer un jeu de données File GDB
Nous allons maintenant réellement **créer un jeu de données file GDB** sur le disque. La méthode `Dataset.Create` prend le chemin complet et le type de pilote (`Drivers.FileGdb`).

```csharp
var path = dataDir + "TolerancesForFileGdbLayer_out.gdb";
using (var dataset = Dataset.Create(path, Drivers.FileGdb))
{
```

> Le bloc `using` garantit que le jeu de données est correctement fermé et vidé sur le disque une fois terminé.

### Étape 3 : Définir les tolérances avec `FileGdbOptions`
Avant de créer une couche, définissez les tolérances dont vous avez besoin. `FileGdbOptions` vous permet de spécifier les tolérances XY, Z et M — c’est l’objet **file gdb options** qui contrôle la précision.

```csharp
var options = new FileGdbOptions
{
    XYTolerance = 0.001,
    ZTolerance = 0.1,
    MTolerance = 0.1,
};
```

Ces valeurs sont typiques pour des données d’ingénierie haute précision, mais vous pouvez les ajuster selon votre projet.

### Étape 4 : Créer une couche GIS avec les tolérances spécifiées
Enfin, créez une nouvelle couche dans le jeu de données, en passant l’objet d’options que nous venons de configurer. Cette étape montre **comment définir des tolérances** tout en **créant une couche GIS**.

```csharp
using (var layer = dataset.CreateLayer("layer_name", options))
{
    // The layer is created with the provided tolerances, ready for use in ArcGIS features/tools.
}
```

Lorsque le bloc `using` se termine, la couche est enregistrée avec les tolérances que vous avez définies.

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **Chemin du jeu de données introuvable** | La variable `dataDir` pointe vers un dossier qui n'existe pas. | Assurez‑vous que le répertoire existe ou créez‑le avec `Directory.CreateDirectory(dataDir)`. |
| **Valeurs de tolérance invalides** | Les tolérances doivent être des nombres non négatifs. | Utilisez des valeurs positives ; évitez zéro sauf si vous voulez intentionnellement aucune tolérance. |
| **Erreur de licence** | Une licence d'essai ou temporaire a expiré. | Appliquez une nouvelle licence temporaire ou passez à une licence complète. |

## Questions fréquemment posées

**Q: Puis-je utiliser Aspose.GIS pour .NET avec d'autres bibliothèques GIS ?**  
A: Oui, Aspose.GIS prend en charge l'interopérabilité, vous permettant de l'intégrer à des bibliothèques telles que NetTopologySuite ou GDAL.

**Q: Existe‑t‑il une version d'essai disponible pour Aspose.GIS pour .NET ?**  
A: Absolument ! Vous pouvez explorer les fonctionnalités avec la [version d'essai gratuite](https://releases.aspose.com/).

**Q: Comment puis‑je obtenir du support pour Aspose.GIS pour .NET ?**  
A: Visitez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour rejoindre la communauté et demander de l'aide.

**Q: Ai‑je besoin d'une licence temporaire à des fins de test ?**  
A: Oui, vous pouvez obtenir une [licence temporaire](https://purchase.aspose.com/temporary-license/) pour les tests et l'évaluation.

**Q: Où puis‑je acheter la licence Aspose.GIS pour .NET ?**  
A: Vous pouvez acheter la licence depuis la [page d'achat](https://purchase.aspose.com/buy).

## Conclusion
Dans ce guide, nous avons couvert **comment créer des fichiers gdb**, configurer les tolérances géométriques et enregistrer une couche prête à l'emploi avec Aspose.GIS pour .NET. Ces étapes vous offrent un contrôle précis des données spatiales, rendant vos applications GIS plus fiables et interopérables.

---  
**Dernière mise à jour :** 2026-04-30  
**Testé avec :** Aspose.GIS for .NET 24.11 (latest at time of writing)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}