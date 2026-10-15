---
date: 2026-10-15
description: Apprenez à créer du GeoJSON à partir de coordonnées et à l'écrire dans
  un flux en utilisant Aspose.GIS for .NET. Ce tutoriel montre la conversion point
  par point et la génération de code C# GeoJSON.
keywords:
- create geojson from coordinates
- stream large geojson files
- write geojson to stream
- geojson tutorial c#
- compress geojson with gzip
lastmod: 2026-10-15
linktitle: Écrire du GeoJSON dans un flux
og_description: Apprenez à créer du GeoJSON à partir de coordonnées et à l'écrire
  dans un flux en utilisant Aspose.GIS for .NET – guide étape par étape pour les grands
  ensembles de données.
og_image_alt: Screenshot of Aspose.GIS code generating GeoJSON stream in C#
og_title: Créer du GeoJSON à partir de coordonnées, écrire dans un flux en .NET
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create geojson from coordinates and write it to a stream
    using Aspose.GIS for .NET. This tutorial shows step‑by‑step conversion of points
    and generation of GeoJSON C# code.
  headline: Create geojson from coordinates, write to a stream in .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET geospatial
- C# stream processing
- GIS data conversion
title: Créer du GeoJSON à partir de coordonnées, écrire dans un flux en .NET
url: /fr/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer du geojson à partir de coordonnées et l'écrire dans un flux

## Introduction
Dans ce tutoriel, vous apprendrez **comment créer du geojson à partir de coordonnées** et l’écrire directement dans un flux en utilisant Aspose.GIS pour .NET. Nous parcourrons la configuration de l’environnement, la création de couches, le peuplement des entités et le streaming du résultat, afin que vous puissiez intégrer des charges géospatiales dans des API, des fonctions cloud ou des services sans fichiers temporaires.

## Réponses rapides
- **Quelle classe écrit le GeoJSON dans un flux ?** `VectorLayer` avec le `GeoJsonDriver`.
- **Ai-je besoin d'une licence pour le développement ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Puis-je convertir des collections de points en GeoJSON ?** Oui – créez un `Feature` pour chaque point et affectez une géométrie `Point`.
- **Le streaming convient‑il aux grands ensembles de données ?** Absolument – `MemoryStream` vous permet d’écrire du GeoJSON à l’échelle du gigaoctet sans charger le fichier complet en mémoire.

## Qu'est‑ce que le GeoJSON ?
GeoJSON est un format ouvert basé sur JSON pour encoder des entités géographiques telles que des points, des lignes et des polygones. Il se compose d’une `FeatureCollection` qui regroupe des objets `Feature` individuels, chacun contenant une géométrie et des données d’attributs. Parce qu’il est léger et adapté au web, le GeoJSON est le standard de facto pour l’échange de données spatiales entre navigateurs, serveurs GIS et applications mobiles.

## Pourquoi utiliser Aspose.GIS pour la génération de geojson ?
Aspose.GIS prend en charge **plus de 35 formats de fichiers spatiaux** et peut diffuser des fichiers de plus de **2 GB** tout en maintenant l’utilisation de la mémoire sous **50 MB**. Son moteur de streaming haute performance écrit le GeoJSON directement dans n’importe quel `Stream` .NET, éliminant le besoin de fichiers temporaires intermédiaires et réduisant la latence d’E/S jusqu’à **70 %** dans les scénarios cloud typiques.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Aspose.GIS pour .NET** installé. Téléchargez le package **Aspose.GIS pour .NET** [ici](https://releases.aspose.com/gis/net/).
2. Un dossier accessible en écriture dans votre projet où vous pourrez placer des fichiers temporaires si nécessaire.
3. Le runtime .NET 5+ ou .NET Core 3.1+ installé.

Passons maintenant à l'implémentation.

## Comment créer du geojson à partir de coordonnées et l'écrire dans un flux ?
`VectorLayer` représente un jeu de données vectorielles en mémoire qui peut être enregistré dans divers formats.  
`GeoJsonDriver` est le pilote qui permet la lecture et l’écriture de fichiers GeoJSON.  

Chargez un `VectorLayer` avec le `GeoJsonDriver`, ajoutez des objets `Feature` contenant une géométrie `Point`, puis appelez `layer.Save(stream, new GeoJsonSaveOptions())`. Cet appel unique sérialise l’ensemble de la collection d’entités dans un document GeoJSON conforme aux normes, stocké dans le `MemoryStream` fourni. Le processus gère automatiquement le mappage des attributs et la conversion des coordonnées, vous offrant ainsi une charge JSON prête à l’emploi sans construction manuelle de chaînes.

### Définition des ancres
**VectorLayer** est l’objet principal d’Aspose.GIS qui représente un jeu de données vectorielles mutable en mémoire.  
**GeoJsonDriver** est le pilote responsable de la lecture et de l’écriture des fichiers GeoJSON.  

## Importer les espaces de noms
Tout d’abord, assurez‑vous d’inclure les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.GIS dans votre code :
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Étape 1 : configurer le répertoire de documents
Créez un chemin de dossier où Aspose.GIS pourra stocker les fichiers auxiliaires si besoin.  
```csharp
string dataDir = "Your Document Directory";
```
Remplacez « Your Document Directory » par le chemin réel de votre répertoire de documents.

## Étape 2 : créer un flux mémoire
Un `MemoryStream` fournit un tampon en mémoire qui peut être envoyé directement via HTTP ou enregistré dans un stockage cloud.  
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Étape 3 : créer une couche vectorielle avec le pilote GeoJSON
La classe `VectorLayer` représente un jeu de données vectorielles qui peut être enregistré dans divers formats, y compris GeoJSON.  
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Étape 4 : définir les attributs des entités
Définissez le schéma d’attributs pour vos entités (par ex., ID, Name).  
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Étape 5 : construire et ajouter des entités
Créez des objets `Feature`, affectez une géométrie de type point, définissez les valeurs d’attributs, puis ajoutez‑les à la couche.  
```csharp
// First Feature
Feature firstFeature = layer.ConstructFeature();
firstFeature.Geometry = new Point(33.97, -118.25);
firstFeature.SetValue("name", "John");
firstFeature.SetValue("age", 23);
layer.Add(firstFeature);
// Second Feature
Feature secondFeature = layer.ConstructFeature();
secondFeature.Geometry = new Point(35.81, -96.28);
secondFeature.SetValue("name", "Mary");
secondFeature.SetValue("age", 54);
layer.Add(secondFeature);
```

## Étape 6 : afficher la sortie GeoJSON
Après l’enregistrement, réinitialisez la position du flux et lisez la chaîne JSON pour vérification ou transmission.  
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Félicitations ! Vous avez créé avec succès du geojson à partir de coordonnées et l’avez écrit dans un flux en utilisant Aspose.GIS pour .NET.

## Problèmes courants et solutions
- **Flux de sortie vide :** Assurez‑vous de réinitialiser la position du flux (`stream.Position = 0`) avant la lecture.
- **Ordre des coordonnées incorrect :** Le GeoJSON attend l’ordre longitude‑latitude ; vérifiez vos valeurs de points.
- **Grands ensembles de données :** Utilisez `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` pour diffuser les entités de façon incrémentielle et garder une faible utilisation mémoire.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.GIS pour .NET à la fois sous Windows et Linux ?**  
R : Oui, Aspose.GIS pour .NET fonctionne sous Windows, Linux et macOS avec un support complet de .NET Core.

**Q : Existe‑t‑il un essai gratuit ?**  
R : Absolument ! Vous pouvez explorer la **page de téléchargement de l’essai gratuit** [ici](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation détaillée ?**  
R : Consultez la **documentation Aspose.GIS .NET** [ici](https://reference.aspose.com/gis/net/).

**Q : Comment obtenir une licence temporaire ?**  
R : Les licences temporaires sont disponibles sur la **page de licence temporaire** [ici](https://purchase.aspose.com/temporary-license/).

**Q : Besoin d’assistance ou d’autres questions ?**  
R : Visitez notre **forum de support GIS** [ici](https://forum.aspose.com/c/gis/33).

**Q : Puis‑je générer du GeoJSON à partir d’une collection de points latitude/longitude ?**  
R : Oui – créez un `Feature` pour chaque point, affectez une géométrie `Point`, puis ajoutez‑le au `VectorLayer`.

**Q : Aspose.GIS prend‑il en charge l’écriture de GeoJSON compressé (gzip) ?**  
R : Vous pouvez envelopper le `MemoryStream` dans un `GZipStream` avant l’enregistrement pour produire une charge compressée.

**Q : Quelle est la taille maximale d’un fichier GeoJSON qu’Aspose.GIS peut gérer ?**  
R : La bibliothèque peut diffuser des fichiers dépassant 2 GB ; l’utilisation de la mémoire reste faible car les données sont écrites de façon incrémentielle.

---

**Dernière mise à jour :** 2026-10-15  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose  

## Tutoriels associés

- [How to Read GeoJSON from Stream with Aspose.GIS for .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [How to Convert GeoJSON to TopoJSON with Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [How to Convert Shapefile to GeoJSON using Aspose.GIS for .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}