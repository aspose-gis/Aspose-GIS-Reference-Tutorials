---
date: 2025-12-28
description: Apprenez à lire le GeoJSON à partir d’un flux en utilisant Aspose.GIS
  pour .NET. Ce guide C# de lecture de GeoJSON fournit un exemple étape par étape
  pour l’intégration de données géospatiales.
linktitle: Read GeoJSON from Stream
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
Si vous vous demandez **how to read geojson** dans une application .NET, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons un **c# geojson example** complet qui montre comment convertir une chaîne GeoJSON, ouvrir une couche GeoJSON depuis un flux mémoire et extraire les propriétés GeoJSON à l'aide d'Aspose.GIS. À la fin, vous disposerez d'un modèle réutilisable que vous pourrez intégrer à n'importe quel projet nécessitant de travailler avec des données géospatiales.

## Réponses rapides
- **Quelle bibliothèque devrais-je utiliser ?** Aspose.GIS for .NET  
- **Puis-je lire du GeoJSON directement depuis un flux ?** Yes – use `VectorLayer.Open` with `AbstractPath.FromStream`.  
- **Ai-je besoin d'une licence pour le développement ?** A free trial works for testing; a license is required for production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **L'extraction des propriétés est-elle simple ?** Yes – call `GetValue<T>(columnName)` on a feature.

## Qu'est-ce que “how to read geojson” ?
Lire du GeoJSON signifie analyser le format basé sur JSON qui décrit des entités géographiques (points, lignes, polygones) et rendre ces entités disponibles sous forme d'objets que vous pouvez interroger, modifier ou afficher dans votre application.

## Pourquoi utiliser Aspose.GIS geojson layer** ?
Aspose.GIS abstrait les détails d'analyse de bas niveau et vous fournit une API cohérente pour de nombreux formats GIS. Il vous permet de **open geojson layer** directement depuis un flux, de gérer efficacement les gros fichiers et d'accéder aux attributs des entités sans écrire de parseurs JSON personnalisés.

## Prérequis
1. **Connaissances de base en C#** – vous devez être à l'aise avec la syntaxe .NET et l'IDE Visual Studio.  
2. **Aspose.GIS installé** – téléchargez la bibliothèque depuis [here](https://releases.aspose.com/gis/net/).  
3. **Un environnement de développement** – Visual Studio, Visual Studio Code ou JetBrains Rider conviendront parfaitement.  

## Importer les espaces de noms
```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Gis;
```

## Étape 1 : **Convert GeoJSON string** – un **c# geojson example**
Tout d'abord, nous créons une chaîne JSON qui représente une `FeatureCollection` simple. Il s'agit de la partie **convert geojson string** du flux de travail.

```csharp
const string geoJson = @"{""type"":""FeatureCollection"",""features"":[
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[0, 1]},""properties"":{""name"":""John""}},
    {""type"":""Feature"",""geometry"":{""type"":""Point"",""coordinates"":[2, 3]},""properties"":{""name"":""Mary""}}
]}";
```

## Étape 2 : **Open GeoJSON layer** depuis un flux et **extract geojson properties**
Nous injectons maintenant la chaîne dans un `MemoryStream`, l'ouvrons en tant que couche GIS, et démontrons comment lire les valeurs d'attributs (l'étape **extract geojson properties**).

```csharp
using (var memoryStream = new MemoryStream(Encoding.UTF8.GetBytes(geoJson)))
using (var layer = VectorLayer.Open(AbstractPath.FromStream(memoryStream), Drivers.GeoJson))
{
    Console.WriteLine(layer.Count); // Output: 2
    Console.WriteLine(layer[1].GetValue<string>("name")); // Output: Mary
}
```

> **Conseil pro :** `VectorLayer.Open` détecte automatiquement le format GeoJSON lorsque vous passez `Drivers.GeoJson`. Vous pouvez également ouvrir des fichiers directement en fournissant un chemin de fichier au lieu d'un flux.

## Problèmes courants & solutions
| Problème | Solution |
|----------|----------|
| **Invalid JSON format** | Vérifiez que la chaîne GeoJSON est bien formée ; utilisez un validateur JSON. |
| **Encoding problems** | Assurez‑vous que le flux utilise UTF‑8 (`Encoding.UTF8.GetBytes`). |
| **Missing properties** | Vérifiez que le nom de la propriété est correctement orthographié (`"name"` dans l'exemple). |
| **License exception** | Utilisez une licence d'essai pour les tests ; appliquez une licence permanente pour la production. |

## Questions fréquentes
### Aspose.GIS est‑il compatible avec d'autres formats GIS ?
Yes, Aspose.GIS supports GeoJSON, Shapefile, KML, GML, and many more formats.

### Puis‑je essayer Aspose.GIS avant d'acheter ?
Yes, you can download a free trial of Aspose.GIS from [here](https://releases.aspose.com/).

### Où puis‑je trouver la documentation d'Aspose.GIS ?
You can find the documentation for Aspose.GIS [here](https://reference.aspose.com/gis/net/).

### Comment obtenir du support pour Aspose.GIS ?
You can get support for Aspose.GIS on the Aspose forums [here](https://forum.aspose.com/c/gis/33).

### Ai‑je besoin d'une licence temporaire pour utiliser Aspose.GIS ?
You can obtain a temporary license for Aspose.GIS from [here](https://purchase.aspose.com/temporary-license/).

## Conclusion
Dans ce guide, nous avons couvert **how to read geojson** depuis un flux mémoire en utilisant Aspose.GIS pour .NET, démontré un flux de travail **c# read geojson**, et montré comment **extract geojson properties** à partir de la couche ouverte. Avec ces étapes, vous pouvez intégrer de manière transparente la gestion des données géospatiales dans n'importe quelle application .NET.

---

**Dernière mise à jour :** 2025-12-28  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}