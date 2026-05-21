---
date: 2026-05-21
description: Apprenez à écrire du GeoJSON dans un flux en utilisant Aspose.GIS pour
  .NET. Ce tutoriel GeoJSON .NET montre la conversion point par point et la génération
  de code GeoJSON C#.
keywords:
- how to write geojson
- convert points geojson
- geojson tutorial .net
- generate geojson c#
linktitle: Écrire du GeoJSON dans un flux
schemas:
- author: Aspose
  dateModified: '2026-05-21'
  description: Learn how to write GeoJSON to stream using Aspose.GIS for .NET. This
    geojson tutorial .net shows step‑by‑step conversion of points and generation of
    GeoJSON C# code.
  headline: How to Write GeoJSON to Stream with Aspose.GIS for .NET
  type: TechArticle
- questions:
  - answer: Yes – create a `Feature` for each point, assign a `Point` geometry, and
      add it to the `VectorLayer`.
    question: Can I generate GeoJSON from a collection of latitude/longitude points?
  - answer: You can wrap the `MemoryStream` in a `GZipStream` before saving to produce
      a compressed payload.
    question: Does Aspose.GIS support writing compressed GeoJSON (gzip)?
  - answer: The library can stream files exceeding 2 GB; memory usage stays low because
      data is written incrementally.
    question: What is the maximum size of a GeoJSON file Aspose.GIS can handle?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Comment écrire du GeoJSON dans un flux avec Aspose.GIS pour .NET
url: /fr/net/layer-data-operations/write-geojson-to-stream/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Écrire du GeoJSON dans un flux

## Introduction
Dans ce tutoriel, vous apprendrez **comment écrire du GeoJSON dans un flux** dans une application .NET en utilisant Aspose.GIS. Nous parcourrons chaque étape, de la configuration de l'environnement à la génération d'un document GeoJSON valide, afin que vous puissiez intégrer les données géospatiales de manière transparente dans vos services.

## Réponses rapides
- **Quelle est la classe principale pour la sortie GeoJSON ?** `VectorLayer` avec le `GeoJsonDriver`.
- **Ai-je besoin d'une licence pour le développement ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Puis-je convertir des collections de points en GeoJSON ?** Oui – utilisez la classe `Feature` et définissez une géométrie de point.
- **Le streaming est-il pris en charge pour les grands ensembles de données ?** Absolument ; `MemoryStream` vous permet d'écrire sans fichiers intermédiaires.

## Qu'est-ce que le GeoJSON ?
GeoJSON est un format standard ouvert pour encoder une variété de structures de données géographiques en JSON. Il définit des objets tels que FeatureCollection, Feature et les types de géométrie (Point, LineString, Polygon). Cette représentation légère et adaptée au web facilite l'échange et la visualisation de données spatiales sur de nombreuses plateformes et langages de programmation.

## Pourquoi utiliser Aspose.GIS pour la génération de GeoJSON ?
Aspose.GIS prend en charge plus de 30 formats de fichiers spatiaux et peut traiter des fichiers de plus de 2 Go sans charger l'intégralité du document en mémoire. Son moteur de streaming haute performance écrit le GeoJSON directement dans les flux, réduisant la surcharge d'E/S. Cela le rend idéal pour les charges de travail géospatiales à l'échelle de l'entreprise, les services cloud et les applications en temps réel.

## Prérequis
Avant de commencer le tutoriel, assurez-vous d'avoir les prérequis suivants :

1. Bibliothèque Aspose.GIS pour .NET : Assurez-vous d'avoir installé la bibliothèque Aspose.GIS pour .NET. Vous pouvez la télécharger [ici](https://releases.aspose.com/gis/net/).
2. Répertoire de documents : Créez un répertoire de documents dans votre projet et notez son chemin.

Maintenant, commençons le tutoriel !

## Comment écrire du GeoJSON dans un flux ?
VectorLayer représente un jeu de données vectorielles qui peut être enregistré dans divers formats, y compris GeoJSON.  
GeoJsonDriver est le pilote utilisé par Aspose.GIS pour lire et écrire des fichiers GeoJSON.  
`layer.Save` écrit le contenu de la couche dans le flux fourni en utilisant les options d'enregistrement spécifiées.

Chargez un `VectorLayer` avec le `GeoJsonDriver`, ajoutez des entités contenant une géométrie de point, puis appelez `layer.Save(stream, new GeoJsonSaveOptions())`. Cela écrit un document GeoJSON complet et conforme aux normes directement dans le `MemoryStream` fourni en quelques lignes de code seulement. La méthode sérialise la collection d'entités, gérant automatiquement les données d'attributs et la conversion de la géométrie, de sorte que vous obteniez une charge JSON prête à l'emploi sans manipulation manuelle de chaînes.

## Importer les espaces de noms
Tout d'abord, assurez-vous d'inclure les espaces de noms nécessaires pour accéder aux fonctionnalités d'Aspose.GIS dans votre code :
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
using Aspose.Gis.Geometries;
```

## Étape 1 : Configurer le répertoire de documents
```csharp
string dataDir = "Your Document Directory";
```
Remplacez « Your Document Directory » par le chemin réel de votre répertoire de documents.

## Étape 2 : Créer un MemoryStream
```csharp
using (var memoryStream = new MemoryStream())
{
    // Code for the next steps goes here
}
```

## Étape 3 : Créer une couche vectorielle avec le pilote GeoJSON
La classe `VectorLayer` représente un jeu de données vectorielles qui peut être enregistré dans divers formats, y compris GeoJSON.
```csharp
using (var layer = VectorLayer.Create(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    // Code for the next steps goes here
}
```

## Étape 4 : Définir les attributs des entités
Définissez le schéma d'attributs pour vos entités (par ex., ID, Name).
```csharp
layer.Attributes.Add(new FeatureAttribute("name", AttributeDataType.String));
layer.Attributes.Add(new FeatureAttribute("age", AttributeDataType.Integer));
```

## Étape 5 : Construire et ajouter des entités
Créez des objets `Feature`, attribuez une géométrie de point, définissez les valeurs d'attributs et ajoutez-les à la couche.
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

## Étape 6 : Afficher la sortie GeoJSON
```csharp
Console.WriteLine(Encoding.UTF8.GetString(memoryStream.ToArray()));
```

Félicitations ! Vous avez écrit du GeoJSON dans un flux avec succès en utilisant Aspose.GIS pour .NET.

## Problèmes courants et solutions
- **Flux de sortie vide :** Assurez-vous de réinitialiser la position du flux (`stream.Position = 0`) avant la lecture.
- **Ordre des coordonnées incorrect :** GeoJSON attend l'ordre longitude‑latitude ; vérifiez les valeurs de vos points.
- **Grands ensembles de données :** Utilisez `layer.Save(stream, new GeoJsonSaveOptions { WriteFeatureCollection = true })` pour diffuser les entités de façon incrémentielle.

## Questions fréquentes
### Puis-je utiliser Aspose.GIS pour .NET à la fois sous Windows et Linux ?
Oui, Aspose.GIS pour .NET est compatible avec les systèmes Windows et Linux.

### Existe-t-il un essai gratuit ?
Absolument ! Vous pouvez découvrir un essai gratuit [ici](https://releases.aspose.com/).

### Où puis-je trouver une documentation détaillée ?
Consultez la documentation [ici](https://reference.aspose.com/gis/net/).

### Comment obtenir une licence temporaire ?
Des licences temporaires sont disponibles [ici](https://purchase.aspose.com/temporary-license/).

### Besoin d'assistance ou avez-vous d'autres questions ?
Visitez notre forum d'assistance [ici](https://forum.aspose.com/c/gis/33).

**Q : Puis-je générer du GeoJSON à partir d'une collection de points latitude/longitude ?**  
R : Oui – créez une `Feature` pour chaque point, attribuez une géométrie `Point`, et ajoutez‑la à la `VectorLayer`.

**Q : Aspose.GIS prend‑il en charge l'écriture de GeoJSON compressé (gzip) ?**  
R : Vous pouvez envelopper le `MemoryStream` dans un `GZipStream` avant l'enregistrement pour produire une charge compressée.

**Q : Quelle est la taille maximale d'un fichier GeoJSON qu'Aspose.GIS peut gérer ?**  
R : La bibliothèque peut diffuser des fichiers dépassant 2 Go ; l'utilisation de la mémoire reste faible car les données sont écrites de façon incrémentielle.

---

**Dernière mise à jour :** 2026-05-21  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment lire du GeoJSON depuis un flux avec Aspose.GIS pour .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Comment convertir du GeoJSON en TopoJSON avec Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Comment convertir un Shapefile en GeoJSON en utilisant Aspose.GIS pour .NET](/gis/net/layer-management/extract-features-to-geojson/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}