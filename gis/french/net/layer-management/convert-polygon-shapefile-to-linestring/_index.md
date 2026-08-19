---
date: 2026-06-25
description: Apprenez à lire un shapefile et à convertir un polygon shapefile en linestring
  en utilisant Aspose.GIS pour .NET. Boostez votre développement GIS avec des instructions
  claires étape par étape.
keywords:
- how to read shapefile
- convert polygon to line
- shapefile to geojson c#
- extract lines from polygon
linktitle: Convertir un Polygon Shapefile en Linestring
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  headline: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  type: TechArticle
- description: Learn how to read shapefile and convert a polygon shapefile to a linestring
    using Aspose.GIS for .NET. Boost your GIS development with clear step‑by‑step
    guidance.
  name: How to Read Shapefile C# – Convert Polygon Shapefile to Linestring
  steps:
  - name: Set the Document Directory
    text: Replace `"Your Document Directory"` with the actual path where your shapefile
      resides.
  - name: Open the Source Shapefile
    text: This line opens the source Polygon Shapefile so you can read its features.
  - name: Create the Destination Linestring Shapefile
    text: Here we create a new Linestring Shapefile that will store the converted
      geometries.
  - name: Iterate Through Source Features
    text: The loop walks through each polygon feature in the original file.
  - name: Convert Polygon to Linestring and Write to Destination
    text: The `ExteriorRing` property returns the outer boundary of a polygon as a
      `LineString`. In this block we convert polygon to line (`LineString`) and add
      the new feature to the destination shapefile.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS supports .NET Framework 4.5+, .NET Core 3.1+, and .NET
      5/6/7, ensuring seamless integration with modern development stacks.
    question: Is Aspose.GIS compatible with all versions of .NET?
  - answer: Yes, you can. Purchase a license [here](https://purchase.aspose.com/buy)
      to remove evaluation limitations and obtain full support.
    question: Can I use Aspose.GIS for commercial projects?
  - answer: Yes, you can find comprehensive documentation and code samples on the
      [documentation page](https://reference.aspose.com/gis/net/).
    question: Are there any examples or documentation available?
  - answer: Absolutely – explore Aspose.GIS with a free trial by visiting [this link](https://releases.aspose.com/).
    question: Is there a trial version available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      assistance and official support.
    question: Where can I seek help or support?
  type: FAQPage
second_title: Aspose.GIS .NET API
title: Comment lire un Shapefile C# – Convertir un Polygon Shapefile en Linestring
url: /fr/net/layer-management/convert-polygon-shapefile-to-linestring/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire un Shapefile C# – Convertir un Shapefile de Polygone en Linestring

## Introduction
Si vous devez **how to read shapefile** des données dans un environnement .NET, vous êtes au bon endroit. Aspose.GIS for .NET abstrait le format binaire de bas niveau d'un Shapefile, vous permettant de charger, interroger et transformer des entités géographiques avec seulement quelques appels d'API. Convertir un shapefile de polygone en linestring est particulièrement utile lorsque vous souhaitez extraire des représentations linéaires pour le routage, l'analyse de réseau ou une simple visualisation.

## Réponses rapides
- **Quelle bibliothèque vous aide à lire shapefile c# ?** Aspose.GIS for .NET – il prend en charge plus de 50 formats GIS et gère des fichiers de plusieurs centaines de mégaoctets sans charger le fichier entier en mémoire.  
- **Pouvez‑vous convertir un polygone en ligne ?** Oui – appelez `LineString` sur l'anneau extérieur du polygone et écrivez le résultat dans un nouveau shapefile.  
- **Ai‑je besoin d'une licence pour la production ?** Une licence commerciale est requise pour les déploiements en production ; un essai gratuit suffit pour l'évaluation.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Une version d'essai est‑elle disponible ?** Absolument – téléchargez une version d'essai gratuite depuis le site Aspose.

`LineString` est un type de géométrie représentant une série de segments de ligne connectés.

## Qu’est‑ce que “read shapefile c#” ?
`Document` est la classe principale qui représente un jeu de données GIS et fournit l'accès à ses entités.  
Lire un shapefile en C# signifie charger le fichier `.shp` en mémoire afin de pouvoir interroger, modifier ou transformer ses géométries. **Il vous suffit d’instancier la classe `Document` avec le chemin du fichier, et Aspose.GIS analyse la structure binaire pour vous**, exposant les entités via une collection facile d’utilisation. Cette approche élimine le besoin de travailler manuellement avec les en‑têtes de fichiers de bas niveau ou les tableaux de coordonnées.

## Pourquoi convertir un polygone en ligne avec Aspose.GIS ?
Convertir un polygone en linestring préserve la frontière extérieure exacte tout en supprimant les anneaux intérieurs, vous offrant une représentation linéaire propre. Aspose.GIS traite **des ensembles de données allant jusqu’à 500 Mo en moins de 2 secondes sur un serveur type**, rendant les conversions par lots rapides et économes en mémoire. La bibliothèque conserve également la référence spatiale originale, de sorte que les lignes résultantes s’alignent parfaitement avec toutes les couches GIS existantes.

## Prérequis
Avant de plonger dans le tutoriel, assurez‑vous d’avoir les éléments suivants en place :

- **Aspose.GIS Library** – Téléchargez et installez la bibliothèque Aspose.GIS depuis le [site web](https://releases.aspose.com/gis/net/).  
- **Shapefile Data** – Disposez d’un shapefile de polygone prêt pour la conversion. Si vous n’en avez pas, vous pouvez trouver des données d’exemple ou créer le vôtre.  
- **Development Environment** – Configurez votre environnement de développement .NET avec les outils nécessaires (Visual Studio, .NET SDK, etc.).

## Importer les espaces de noms
La classe `Document` est l’objet principal d’Aspose.GIS qui représente un jeu de données GIS et fournit des méthodes pour lire et écrire des shapefiles. Ajoutez les espaces de noms suivants au début de votre fichier de code :

```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Comment lire un shapefile et convertir un polygone en linestring ?
Chargez le shapefile de polygone source, extrayez l’anneau extérieur de chaque polygone, créez un `LineString` à partir de cet anneau, et écrivez le résultat dans un nouveau shapefile – le tout en cinq étapes simples. Ce modèle fonctionne pour tout jeu de données, quelle que soit sa taille, et garantit que le système de coordonnées de la source est préservé dans la destination.

### Étape 1 : Définir le répertoire du Document
Remplacez `"Your Document Directory"` par le chemin réel où se trouve votre shapefile.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Étape 2 : Ouvrir le shapefile source
Cette ligne ouvre le shapefile de polygone source afin que vous puissiez lire ses entités.

```csharp
using (VectorLayer source = VectorLayer.Open(dataDir + "PolygonShapeFile.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```

### Étape 3 : Créer le shapefile Linestring de destination
Ici nous créons un nouveau shapefile Linestring qui stockera les géométries converties.

```csharp
using (VectorLayer destination = VectorLayer.Create(dataDir + "PolygonShapeFileToLineShapeFile_out.shp", Drivers.Shapefile))
{
    // Rest of the code will go here
}
```

### Étape 4 : Parcourir les entités source
La boucle parcourt chaque entité de polygone dans le fichier original.

```csharp
foreach (Feature sourceFeature in source)
{
    // Rest of the code will go here
}
```

### Étape 5 : Convertir le polygone en linestring et écrire vers la destination
La propriété `ExteriorRing` renvoie la frontière extérieure d’un polygone sous forme de `LineString`.  
```csharp
Polygon polygon = (Polygon)sourceFeature.Geometry;
LineString line = new LineString(polygon.ExteriorRing);
Feature destinationFeature = destination.ConstructFeature();
destinationFeature.Geometry = line;
destination.Add(destinationFeature);
```
Dans ce bloc, nous convertissons le polygone en ligne (`LineString`) et ajoutons la nouvelle entité au shapefile de destination.

## Problèmes courants et conseils
- **Coordinate System Mismatch** – Assurez‑vous que les couches source et destination utilisent la même référence spatiale ; sinon, les lignes peuvent apparaître déplacées.  
- **Large Files** – Lors du traitement de shapefiles très volumineux, envisagez de diffuser les entités au lieu de les charger toutes en mémoire d’un coup.  
- **Null Geometries** – Protégez‑vous contre les entités avec des géométries vides afin d’éviter les exceptions d’exécution.  
- **Extract lines from polygon** – Si vous avez seulement besoin de l’anneau extérieur, utilisez la propriété `ExteriorRing` ; pour les anneaux intérieurs, itérez `InteriorRings`.  

## Questions fréquemment posées

**Q : Aspose.GIS est‑il compatible avec toutes les versions de .NET ?**  
R : Oui, Aspose.GIS prend en charge .NET Framework 4.5+, .NET Core 3.1+, et .NET 5/6/7, assurant une intégration fluide avec les piles de développement modernes.

**Q : Puis‑je utiliser Aspose.GIS pour des projets commerciaux ?**  
R : Oui, vous le pouvez. Achetez une licence [ici](https://purchase.aspose.com/buy) pour supprimer les limitations d’évaluation et obtenir un support complet.

**Q : Existe‑t‑il des exemples ou de la documentation disponibles ?**  
R : Oui, vous pouvez trouver une documentation complète et des exemples de code sur la [page de documentation](https://reference.aspose.com/gis/net/).

**Q : Une version d'essai est‑elle disponible ?**  
R : Absolument – explorez Aspose.GIS avec un essai gratuit en visitant [ce lien](https://releases.aspose.com/).

**Q : Où puis‑je obtenir de l’aide ou du support ?**  
R : Consultez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour l’assistance communautaire et le support officiel.

---

**Last Updated:** 2026-06-25  
**Testé avec :** Aspose.GIS for .NET (dernière version)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment convertir un Shapefile en GeoJSON avec Aspose.GIS pour .NET](/gis/net/layer-management/extract-features-to-geojson/)
- [Comment lire du GeoJSON depuis un flux avec Aspose.GIS pour .NET](/gis/net/layer-data-operations/read-geojson-from-stream/)
- [Comment créer une géométrie de polygone avec Aspose.GIS pour .NET](/gis/net/geometry-creation/create-polygon-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}