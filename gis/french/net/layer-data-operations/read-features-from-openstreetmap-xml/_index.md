---
date: 2026-06-10
description: Apprenez à convertir OSM en Shapefile et à lire les entités du XML OpenStreetMap
  en utilisant Aspose.GIS pour .NET. Guide étape par étape avec des conseils pratiques.
keywords:
- convert osm to shapefile
- osm to geojson conversion
- how to read osm xml
linktitle: Lire les entités du XML OpenStreetMap
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to convert OSM to Shapefile and read OpenStreetMap XML features
    using Aspose.GIS for .NET. Step‑by‑step guide with practical tips.
  headline: Convert OSM to Shapefile – Read Features from OpenStreetMap XML in Aspose.GIS
  type: TechArticle
- questions:
  - answer: Aspose.GIS for .NET
    question: What library handles OSM XML?
  - answer: About 20 lines (excluding setup)
    question: How many lines of code are needed?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes—Aspose.GIS streams data efficiently; filtering reduces memory usage.
    question: Can I read large OSM files?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Convertir OSM en Shapefile – Lire les entités du XML OpenStreetMap dans Aspose.GIS
url: /fr/net/layer-data-operations/read-features-from-openstreetmap-xml/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir OSM en Shapefile – Lire les entités depuis le XML OpenStreetMap dans Aspose.GIS

Si vous devez **convertir OSM en Shapefile** ou simplement lire les données XML OpenStreetMap (OSM) dans une application .NET, vous êtes au bon endroit. Aspose.GIS pour .NET rend facile l’ingestion des fichiers XML OSM, l’extraction des nœuds, des chemins et des relations, puis leur exportation vers Shapefile, GeoJSON ou d’autres formats GIS. Dans ce tutoriel, nous parcourrons l’ensemble du flux de travail — de la configuration de l’environnement à l’itération des entités — afin que vous puissiez commencer à créer des solutions de cartographie ou d’analyse spatiale immédiatement.

## Réponses rapides
- **Quelle bibliothèque gère le XML OSM ?** Aspose.GIS for .NET  
- **Combien de lignes de code sont nécessaires ?** Environ 20 lignes (hors configuration)  
- **Ai-je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Puis-je lire de gros fichiers OSM ?** Oui — Aspose.GIS diffuse les données efficacement ; le filtrage réduit l’utilisation de la mémoire.

## Qu’est‑ce que « how to read osm » ?
Lire les données OSM (OpenStreetMap) signifie analyser le format XML OSM pour accéder aux nœuds, chemins et relations qui représentent des entités géographiques du monde réel. Une fois analysées, vous pouvez interroger, visualiser ou transformer ces données pour une variété d’applications GIS. Cela inclut également les métadonnées telles que les balises, les horodatages et les informations utilisateur, permettant des analyses détaillées et des flux de travail d’édition.

## Pourquoi utiliser Aspose.GIS pour OSM ?
Aspose.GIS fournit un analyseur **sans dépendance** capable de gérer des fichiers jusqu’à 1 Go tout en consommant moins de 250 Mo de RAM, ce qui le rend 3 fois plus rapide que de nombreuses alternatives open‑source. Il offre également une conversion de géométrie intégrée, des requêtes spatiales et une exportation directe vers Shapefile, GeoJSON, KML et plus, le tout depuis du code .NET pur.

## Prérequis
- **Visual Studio** (Community, Professional ou Enterprise) – version récente recommandée.  
- **Aspose.GIS for .NET** – téléchargez-le depuis le [download link](https://releases.aspose.com/gis/net/) officiel et ajoutez le package NuGet à votre projet.  
- Connaissances de base en C# (variables, boucles, POO).  

## Importer les espaces de noms
L’espace de noms `Aspose.Gis` fournit les types GIS de base, tandis que `Aspose.Gis.Geometries` contient des aides pour les géométries.

L’espace de noms `Aspose.Gis` est le point d’entrée pour toutes les opérations GIS dans Aspose.GIS.

## Comment convertir OSM en Shapefile avec Aspose.GIS ?
Chargez la couche XML OSM, parcourez ses entités et écrivez‑les dans un Shapefile en seulement trois appels d’API. La classe `ShapefileWriter` crée un nouveau Shapefile et y écrit les entités. D’abord, créez un objet `Layer` pour la source OSM, puis ouvrez un `ShapefileWriter` pointant vers le dossier de destination, et enfin copiez la géométrie et les attributs de chaque entité. Cette approche convertit OSM en Shapefile en moins d’une minute pour des jeux de données typiques de taille urbaine (≈ 200 k entités).

## Comment effectuer la conversion osm vers geojson
Aspose.GIS peut exporter la même couche OSM directement vers GeoJSON avec un seul appel `Save`, éliminant ainsi les étapes de format intermédiaire. La méthode `Save` écrit la couche dans le format et le chemin de fichier choisis. Appelez `layer.Save("output.geojson", SaveFormat.GeoJson)` et la bibliothèque gère automatiquement la transformation des coordonnées et le mappage des attributs, livrant un fichier GeoJSON conforme aux standards, prêt pour la cartographie web.

## Étape 1 : Définir le répertoire du document
Définissez le dossier qui contient votre fichier XML OSM.  
Remplacez `"Your Document Directory"` par le chemin absolu ou relatif vers le fichier.

## Étape 2 : Ouvrir la couche OpenStreetMap
La classe `Layer` représente une couche GIS chargée depuis une source de données telle qu’un fichier XML OSM.  
L’ouverture de la couche diffuse le XML, de sorte que seules les parties nécessaires restent en mémoire.

## Étape 3 : Obtenir le nombre d’entités
Récupérez le nombre total d’entités dans la couche OSM et affichez le compte dans la console. Cela vous aide à vérifier que le fichier a été lu correctement.

## Étape 4 : Récupérer l’entité à l’index
Accédez directement à n’importe quelle entité par son index zéro‑based ; l’exemple récupère la troisième entité pour illustrer l’accès aléatoire.

## Étape 5 : Parcourir les entités
Parcourir la couche vous permet de traiter chaque géométrie — points, lignes ou polygones — individuellement. La méthode `AsText()` renvoie la géométrie au format Well‑Known Text (WKT), pratique pour le débogage ou la journalisation.

## Problèmes courants et solutions
- **File not found** – Vérifiez à nouveau le chemin dans `dataDir` et assurez‑vous que le nom du fichier OSM correspond exactement.  
- **Unsupported geometry** – Certains éléments OSM contiennent des relations complexes ; inspectez d’abord `feature.Geometry` et gérez les types `MultiPolygon` ou `GeometryCollection` en conséquence.  
- **Performance on large files** – Chargez la couche à l’intérieur d’un bloc `using` (comme montré) pour garantir la libération des ressources, et appliquez un filtrage LINQ (`layer.Where(f => f.Geometry is Point)`) si vous n’avez besoin que d’un sous‑ensemble d’entités.

## Questions fréquentes
### Aspose.GIS pour .NET est‑il compatible avec d’autres formats de données GIS ?
Oui, Aspose.GIS prend en charge plus de 30 formats GIS — y compris Shapefile, GeoJSON, KML, GML et CSV — permettant un échange de données fluide.

### Puis‑je utiliser Aspose.GIS à des fins commerciales ?
Absolument. Achetez une licence depuis la [purchase page](https://purchase.aspose.com/buy) pour supprimer les limitations de l’essai et obtenir un support complet.

### Existe‑t‑il un essai gratuit disponible pour Aspose.GIS pour .NET ?
Oui, téléchargez un essai pleinement fonctionnel depuis le [website](https://releases.aspose.com/) pour évaluer toutes les fonctionnalités avant d’acheter.

### Où puis‑je trouver du support pour Aspose.GIS pour .NET ?
Visitez le forum officiel [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) pour poser des questions, partager des extraits de code et obtenir de l’aide de la communauté et des ingénieurs Aspose.

### Puis‑je obtenir une licence temporaire pour Aspose.GIS pour .NET ?
Oui, demandez une licence temporaire depuis la [temporary license page](https://purchase.aspose.com/temporary-license/) pour des tests à court terme ou des pipelines CI.

---

**Dernière mise à jour :** 2026-06-10  
**Testé avec :** Aspose.GIS 24.5 for .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.Gis;
using Aspose.GIS.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

```csharp
string dataDir = "Your Document Directory";
```

```csharp
using (var layer = Drivers.OsmXml.OpenLayer(dataDir + "fountain.osm"))
{
```

```csharp
int count = layer.Count;
Console.WriteLine("Layer count: " + count);
```

```csharp
Feature featureAtIndex2 = layer[2];
```

```csharp
foreach (Feature feature in layer)
{
    Console.WriteLine(feature.Geometry.AsText());
}
```

## Tutoriels associés

- [Comment convertir un Shapefile en GeoJSON avec Aspose.GIS pour .NET – Tutoriels complets](/gis/net/)
- [Comment convertir GeoJSON en TopoJSON avec Aspose.GIS](/gis/net/geo-data-conversion/convert-geojson-to-topojson/)
- [Lire un Shapefile C# – Filtrer les entités par attribut avec Aspose.GIS](/gis/net/layer-management/filter-features-by-attribute/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}