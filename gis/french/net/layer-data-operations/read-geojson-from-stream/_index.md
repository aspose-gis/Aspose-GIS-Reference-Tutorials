---
date: 2026-04-24
description: Apprenez **comment lire du geojson** à partir d’un flux en utilisant
  Aspose.GIS pour .NET. Ce guide étape par étape vous montre comment **charger le
  flux geojson**, le parser et extraire les propriétés en C#.
keywords:
- how to read geojson
- load geojson stream
- Aspose GIS GeoJSON
linktitle: Lire le GeoJSON depuis le flux
second_title: Aspose.GIS .NET API
title: Comment lire du GeoJSON depuis un flux avec Aspose.GIS pour .NET
url: /fr/net/layer-data-operations/read-geojson-from-stream/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire du GeoJSON depuis un flux avec Aspose.GIS pour .NET

## Introduction
Si vous vous demandez **comment lire du geojson** dans une application .NET, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons un **exemple C# GeoJSON** complet qui montre comment convertir une chaîne GeoJSON, **charger un flux geojson** dans un flux mémoire, ouvrir une couche GeoJSON et extraire les propriétés GeoJSON à l’aide d’Aspose.GIS. À la fin, vous disposerez d’un modèle réutilisable que vous pourrez intégrer à n’importe quel projet nécessitant la gestion de données géospatiales.

## Réponses rapides
- **Quelle bibliothèque devrais-je utiliser ?** Aspose.GIS pour .NET – il gère de nombreux formats GIS dès le départ.  
- **Puis-je lire du GeoJSON directement depuis un flux ?** Oui – utilisez `VectorLayer.Open` avec `AbstractPath.FromStream`.  
- **Ai-je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **L’extraction des propriétés est‑elle simple ?** Absolument – appelez `GetValue<T>(columnName)` sur une entité.

## Qu’est‑ce que « how to read geojson » ?
Lire du GeoJSON consiste à analyser le format JSON qui décrit des entités géographiques (points, lignes, polygones) et à transformer ces entités en objets que vous pouvez interroger, modifier ou afficher dans votre application.

## Pourquoi utiliser Aspose.GIS pour **open geojson layer** ?
Aspose.GIS masque les détails de parsing bas‑niveau et vous offre une API cohérente pour de nombreux formats GIS. Il vous permet de **open geojson layer** directement depuis un flux, de gérer efficacement de gros fichiers et d’accéder aux attributs des entités sans écrire de parseurs JSON personnalisés.

## Quand chargeriez‑vous **load geojson stream** ?
- Importation de données depuis un service web qui renvoie du GeoJSON dans le corps de la réponse.  
- Traitement de fichiers GeoJSON téléchargés par l’utilisateur sans les écrire d’abord sur le disque.  
- Travail avec des données en mémoire générées à la volée (par ex., depuis une base de données ou une autre API).  

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Connaissances de base en C#** – vous devez être à l’aise avec la syntaxe .NET et l’IDE Visual Studio.  
2. **Aspose.GIS installé** – téléchargez la bibliothèque depuis [here](https://releases.aspose.com/gis/net/).  
3. **Un environnement de développement** – Visual Studio, Visual Studio Code ou JetBrains Rider conviendront parfaitement.  

## Importer les espaces de noms
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Étape 1 : **Convert GeoJSON string** – un **exemple C# GeoJSON**
Tout d’abord, nous créons une chaîne JSON qui représente une simple `FeatureCollection`. C’est la partie **convert geojson string** du flux de travail.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Étape 2 : **Load GeoJSON stream** et **extract geojson properties**
Nous injectons maintenant la chaîne dans un `MemoryStream`, l’ouvrons comme couche GIS et démontrons comment lire les valeurs d’attributs (l’étape **extract geojson properties**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Astuce :** `VectorLayer.Open` détecte automatiquement le format GeoJSON lorsque vous passez `Drivers.GeoJson`. Vous pouvez également ouvrir des fichiers directement en fournissant un chemin de fichier au lieu d’un flux.

## Problèmes courants & solutions
| Problème | Solution |
|----------|----------|
| **Format JSON invalide** | Vérifiez que la chaîne GeoJSON est bien formée ; utilisez un validateur JSON. |
| **Problèmes d’encodage** | Assurez‑vous que le flux utilise UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Propriétés manquantes** | Vérifiez que le nom de la propriété est correctement orthographié (`"name"` dans l’exemple). |
| **Exception de licence** | Utilisez une licence d’essai pour les tests ; appliquez une licence permanente pour la production. |

## Questions fréquentes
### Aspose.GIS est‑il compatible avec d’autres formats GIS ?
Oui, Aspose.GIS prend en charge GeoJSON, Shapefile, KML, GML et bien d’autres formats.

### Puis‑je essayer Aspose.GIS avant d’acheter ?
Oui, vous pouvez télécharger une version d’essai gratuite d’Aspose.GIS depuis [here](https://releases.aspose.com/).

### Où puis‑je trouver la documentation d’Aspose.GIS ?
Vous pouvez consulter la documentation d’Aspose.GIS [here](https://reference.aspose.com/gis/net/).

### Comment obtenir du support pour Aspose.GIS ?
Vous pouvez obtenir du support pour Aspose.GIS sur les forums Aspose [here](https://forum.aspose.com/c/gis/33).

### Ai‑je besoin d’une licence temporaire pour utiliser Aspose.GIS ?
Vous pouvez obtenir une licence temporaire pour Aspose.GIS depuis [here](https://purchase.aspose.com/temporary-license/).

## Conclusion
Dans ce guide, nous avons couvert **comment lire du geojson** depuis un flux mémoire avec Aspose.GIS pour .NET, démontré un flux de travail **C# read geojson**, et montré comment **extract geojson properties** depuis la couche ouverte. Avec ces étapes, vous pouvez intégrer sans effort la gestion de données géospatiales dans n’importe quelle application .NET.

---

**Dernière mise à jour :** 2026-04-24  
**Testé avec :** Aspose.GIS 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}