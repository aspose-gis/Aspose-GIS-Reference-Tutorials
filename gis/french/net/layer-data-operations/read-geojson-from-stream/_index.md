---
date: 2026-10-05
description: Apprenez à lire du geojson depuis un flux en utilisant Aspose.GIS for
  .NET. Ce guide étape par étape vous montre comment charger le flux geojson, l’analyser
  et extraire les propriétés en C#.
keywords:
- how to read geojson
- load geojson stream
- parse geojson c#
- open geojson layer
- extract geojson properties
lastmod: 2026-10-05
linktitle: Lire le GeoJSON depuis un flux
og_description: Apprenez à lire du geojson depuis un flux avec Aspose.GIS for .NET,
  y compris l’analyse, l’ouverture d’une couche geojson et l’extraction des propriétés
  en C#.
og_image_alt: Tutorial guide showing how to read geojson from a stream with Aspose.GIS
  in C#
og_title: Comment lire du geojson depuis un flux avec Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  headline: How to read geojson from a stream with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to read geojson from a stream using Aspose.GIS for .NET.
    This step‑by‑step guide shows you how to load geojson stream, parse it, and extract
    properties in C#.
  name: How to read geojson from a stream with Aspose.GIS for .NET
  steps:
  - name: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
    text: '**Basic knowledge of C#** – you should be comfortable with .NET syntax
      and the Visual Studio IDE.'
  - name: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
    text: '**Aspose.GIS installed** – download the library from [Aspose.GIS .NET download
      page](https://releases.aspose.com/gis/net/).'
  - name: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
    text: '**A development environment** – Visual Studio, Visual Studio Code, or JetBrains
      Rider will work fine.'
  type: HowTo
- questions:
  - answer: Aspose.GIS for .NET – it handles 30+ GIS formats out of the box.
    question: What library should I use?
  - answer: Yes – call `VectorLayer.Open` with `AbstractPath.FromStream`.
    question: Can I read GeoJSON directly from a stream?
  - answer: A free trial works for testing; a full license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Which .NET versions are supported?
  - answer: Absolutely – use `GetValue<T>(columnName)` on a feature.
    question: Is extracting properties simple?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- geojson
- Aspose.GIS
- .NET GIS
- C# geospatial
title: Comment lire du geojson depuis un flux avec Aspose.GIS for .NET
url: /fr/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire du geojson depuis un flux avec Aspose.GIS pour .NET

## Introduction
Si vous vous demandez **how to read geojson** dans une application .NET, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons un **C# GeoJSON example** complet qui montre comment convertir une chaîne GeoJSON, **load geojson stream** dans un flux mémoire, ouvrir une couche GeoJSON et extraire les propriétés GeoJSON à l'aide d'Aspose.GIS. À la fin, vous disposerez d'un modèle réutilisable que vous pourrez intégrer à n'importe quel projet nécessitant de travailler avec des données géospatiales.

## Réponses rapides
- **Quelle bibliothèque devrais-je utiliser ?** Aspose.GIS for .NET – elle gère plus de 30 formats GIS dès le départ.  
- **Puis-je lire le GeoJSON directement depuis un flux ?** Oui – appelez `VectorLayer.Open` avec `AbstractPath.FromStream`.  
- **Ai-je besoin d'une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **L'extraction des propriétés est-elle simple ?** Absolument – utilisez `GetValue<T>(columnName)` sur une entité.

**VectorLayer.Open** ouvre une couche GIS à partir d'une source de données telle qu'un fichier ou un flux. **AbstractPath.FromStream** crée un objet de chemin abstrait qui représente le flux fourni pour le pilote GIS. **GetValue<T>(columnName)** lit la valeur de l'attribut spécifié d'une entité et la renvoie sous forme de type T.

## Qu'est-ce que la lecture de geojson ?
Lire du geojson consiste à convertir une chaîne ou un flux au format GeoJSON en objets de caractéristiques géographiques en mémoire. Ce format encode des points, des lignes et des polygones en JSON, ce qui facilite l'échange de données spatiales entre services web, bases de données et applications clientes. Une fois analysé, vous pouvez interroger, modifier ou rendre les entités avec n'importe quelle bibliothèque .NET compatible GIS, telle qu'Aspose.GIS.

## Pourquoi utiliser Aspose.GIS pour ouvrir une couche geojson ?
Aspose.GIS vous permet d'ouvrir une couche GeoJSON directement depuis un flux, éliminant ainsi le besoin de fichiers temporaires et réduisant la surcharge d'E/S. La bibliothèque prend en charge plus de 30 formats GIS et peut traiter des fichiers jusqu'à 2 Go sans charger l'intégralité du document en mémoire, ce qui est idéal pour les grands ensembles de données. Elle normalise également les systèmes de référence de coordonnées automatiquement, vous permettant de vous concentrer sur la logique métier plutôt que sur l'analyse de bas niveau.

## Quand chargeriez‑vous un flux geojson ?
Vous chargeriez un flux GeoJSON lorsque vous recevez des données spatiales d'une API, devez gérer des fichiers téléchargés par l'utilisateur sans les enregistrer sur le disque, ou générez du GeoJSON à la volée à partir d'une requête de base de données. Le streaming évite les écritures disque inutiles, améliore les performances dans les scénarios à haut débit et maintient votre application sans état, ce qui est particulièrement précieux dans les microservices cloud‑native.

## Prérequis
1. **Connaissances de base en C#** – vous devez être à l'aise avec la syntaxe .NET et l'IDE Visual Studio.  
2. **Aspose.GIS installé** – téléchargez la bibliothèque depuis la [page de téléchargement Aspose.GIS .NET](https://releases.aspose.com/gis/net/).  
3. **Un environnement de développement** – Visual Studio, Visual Studio Code ou JetBrains Rider conviendront parfaitement.  

## Importer les espaces de noms
L'espace de noms `Aspose.GIS` fournit les classes GIS de base. `System.IO` vous donne `MemoryStream`, et `System.Text` fournit des utilitaires d'encodage UTF‑8. L'importation de ces espaces de noms rend le code suivant concis et lisible.

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Étape 1 : convertir la chaîne geojson – un exemple GeoJSON C#
Tout d'abord, nous créons une chaîne JSON qui représente une simple `FeatureCollection`. Il s'agit de la partie **convert geojson string** du flux de travail.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Étape 2 : charger le flux geojson et extraire les propriétés geojson
Nous injectons maintenant la chaîne dans un `MemoryStream`, l'ouvrons en tant que couche GIS, et démontrons comment lire les valeurs d'attributs (l'étape **extract geojson properties**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Astuce :** `VectorLayer.Open` détecte automatiquement le format GeoJSON lorsque vous transmettez `Drivers.GeoJson`. Vous pouvez également ouvrir des fichiers directement en fournissant un chemin de fichier au lieu d'un flux.

## Problèmes courants & solutions
| Problème | Solution |
|----------|----------|
| **Format JSON invalide** | Vérifiez que la chaîne GeoJSON est bien formée ; utilisez un validateur JSON. |
| **Problèmes d'encodage** | Assurez‑vous que le flux utilise UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Propriétés manquantes** | Vérifiez que le nom de la propriété est correctement orthographié (`"name"` dans l'exemple). |
| **Exception de licence** | Utilisez une licence d'essai pour les tests ; appliquez une licence permanente pour la production. |

## Questions fréquemment posées
### Aspose.GIS est‑il compatible avec d'autres formats GIS ?
Oui, Aspose.GIS prend en charge GeoJSON, Shapefile, KML, GML et plus de 20 formats supplémentaires, vous permettant de basculer entre les sources de données sans modifier le code.

### Puis‑je essayer Aspose.GIS avant d'acheter ?
Vous pouvez télécharger une version d'essai gratuite d'Aspose.GIS depuis la [page de téléchargement de l'essai gratuit Aspose.GIS](https://releases.aspose.com/).

### Où puis‑je trouver la documentation d'Aspose.GIS ?
Vous pouvez trouver la documentation d'Aspose.GIS dans la [référence API .NET Aspose.GIS](https://reference.aspose.com/gis/net/).

### Comment obtenir du support pour Aspose.GIS ?
Vous pouvez obtenir du support pour Aspose.GIS sur le forum Aspose GIS [Aspose GIS forum](https://forum.aspose.com/c/gis/33).

### Ai‑je besoin d'une licence temporaire pour utiliser Aspose.GIS ?
Vous pouvez obtenir une licence temporaire pour Aspose.GIS depuis la [page de demande de licence temporaire](https://purchase.aspose.com/temporary-license/).

## Conclusion
Dans ce guide, nous avons couvert **how to read geojson** depuis un flux mémoire en utilisant Aspose.GIS pour .NET, démontré un flux de travail **C# read geojson**, et montré comment **extract geojson properties** de la couche ouverte. Avec ces étapes, vous pouvez intégrer de manière transparente la gestion des données géospatiales dans n'importe quelle application .NET.

---

**Dernière mise à jour :** 2026-10-05  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Comment écrire du GeoJSON dans un flux avec Aspose.GIS pour .NET](/gis/net/layer-data-operations/write-geojson-to-stream/)
- [Comment convertir du GeoJSON en GDB avec Aspose.GIS pour .NET](/gis/net/layer-management/convert-geojson-layer-to-file-gdb/)
- [Convertir un Shapefile en GeoJSON avec Aspose.GIS pour .NET](/gis/net/layer-management/extract-features-to-geojson/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}