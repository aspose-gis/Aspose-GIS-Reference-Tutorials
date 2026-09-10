---
date: 2026-09-10
description: Apprenez à convertir des courbes en lignes (linearize geometry) avec
  Aspose.GIS for .NET, permettant un traitement et une analyse géospatiaux efficaces
  dans vos applications .NET.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
lastmod: 2026-09-10
linktitle: Linearize une géométrie
og_description: Convertissez des courbes en lignes (linearize geometry) avec Aspose.GIS
  for .NET. Apprenez étape par étape comment simplifier les géométries pour un rendu
  plus rapide et une compatibilité plus large.
og_image_alt: Guide showing how to linearize curved geometries to straight lines using
  Aspose.GIS in a .NET application
og_title: Convertir des courbes en lignes avec Aspose.GIS for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  headline: How to Convert Curves to Lines with Aspose.GIS for .NET
  type: TechArticle
- description: Learn how to convert curves to lines (linearize geometry) using Aspose.GIS
    for .NET, enabling efficient geospatial processing and analysis in your .NET apps.
  name: How to Convert Curves to Lines with Aspose.GIS for .NET
  steps:
  - name: Define the output path
    text: '`Path.Combine` builds a platform‑independent file path, handling Windows
      backslashes and Unix forward slashes automatically. Replace `"Your Document
      Directory"` with the folder where you want the KML file saved.'
  - name: Create a layer for the output file
    text: A *layer* groups geographic features of the same type. Here we instantiate
      a new KML layer that will store the linearized geometry.
  - name: Construct a new feature
    text: A *feature* represents a single geographic object (point, line, polygon,
      etc.). We’ll attach our linear geometry to this feature.
  - name: Define the original complex geometry
    text: '`Geometry.FromWkt` parses a Well‑Known Text (WKT) string into a geometry
      object. The sample WKT includes a `LineString`, a `CompoundCurve`, and a `CircularString`
      to showcase curve handling.'
  - name: Convert curves to lines
    text: '`ToLinearGeometry()` tessellates every curve in the source geometry into
      straight‑line segments, returning a new linear geometry that retains any Z‑coordinates.'
  - name: Assign the linear geometry to the feature
    text: The feature’s `Geometry` property now holds the simplified, linear version
      of the original shape.
  - name: Add the feature to the layer
    text: Adding the feature to the KML layer queues it for writing; when the `using`
      block ends, the layer flushes the data to the output file.
  type: HowTo
- questions:
  - answer: Yes, Aspose.GIS works with .NET Core, enabling cross‑platform applications.
    question: Is Aspose.GIS for .NET compatible with .NET Core?
  - answer: Absolutely! The library supports KML, Shapefile, GeoJSON, and many more
      formats—over 30 in total.
    question: Can I work with different GIS file formats using Aspose.GIS for .NET?
  - answer: Yes, it provides a wide range of spatial functions, from buffering to
      spatial joins.
    question: Does Aspose.GIS offer spatial operations and analysis?
  - answer: Yes, you can download a free trial from the [Aspose.GIS website](https://releases.aspose.com/gis/net/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) for community
      and staff support.
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.GIS .NET API
tags:
- convert curves to lines
- Aspose.GIS
- .NET GIS processing
title: Comment convertir des courbes en lignes avec Aspose.GIS for .NET
url: /fr/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir les courbes en lignes (linéariser la géométrie) avec Aspose.GIS pour .NET

## Introduction
Si vous devez **convertir des courbes en lignes** pour la cartographie, l'analyse spatiale ou les tâches d'échange de données, Aspose.GIS pour .NET vous offre une méthode propre et programmatique pour le faire. Dans ce tutoriel, nous parcourrons un exemple complet et réel qui montre comment prendre une géométrie complexe — contenant des courbes et des formes composées — et la transformer en une représentation linéaire simple qui fonctionne avec n'importe quel système GIS.

## Réponses rapides
- **Que signifie « convertir des courbes en lignes » ?** Elle transforme les géométries courbes en segments de ligne droite.  
- **Pourquoi choisir Aspose.GIS ?** La bibliothèque prend en charge plus de 30 formats GIS et gère la conversion de géométrie sans outils externes.  
- **De quoi ai‑je besoin au préalable ?** .NET Framework ou .NET Core, Visual Studio (ou tout IDE C#), et le package NuGet Aspose.GIS.  
- **Combien de temps le sample s'exécutera‑t‑il ?** Moins de cinq minutes une fois la bibliothèque installée.  
- **Puis‑je exporter vers d'autres formats ?** Absolument — remplacez le pilote KML par Shapefile, GeoJSON, etc.  
Vous pouvez télécharger la suite complète de produits depuis le [site Aspose](https://releases.aspose.com/).

## Que signifie convertir des courbes en lignes ?
La conversion des courbes en lignes (également appelée **linéarisation de la géométrie**) remplace chaque segment courbe par une série de courts morceaux de ligne droite, créant une *géométrie linéaire*. Cela rend le rendu jusqu'à cinq fois plus rapide, réduit la consommation de mémoire et garantit que les données peuvent être exploitées par les services GIS hérités qui n'acceptent que des entités linéaires.

## Pourquoi convertir des courbes en lignes ?
Les géométries linéaires sont rendues et interrogées jusqu'à **5 × plus rapidement** que leurs homologues courbes, et **plus de 30 plateformes GIS** n'acceptent que des entités linéaires. Simplifier la géométrie réduit également la taille des fichiers pour les aperçus web et permet des algorithmes — tels que l'analyse de réseau ou le clustering — qui nécessitent des entrées en ligne droite.

## Comment linéariser la géométrie ?
Utilisez la méthode `ToLinearGeometry()` fournie par Aspose.GIS. Elle tesselle automatiquement chaque courbe d'une géométrie en segments de ligne droite tout en préservant les valeurs Z, de sorte que vous obteniez une approximation linéaire sans perdre les données d'élévation. Vous pouvez également spécifier une tolérance pour contrôler la déviation maximale entre la courbe originale et les segments générés, vous permettant d'équilibrer précision et taille du fichier. La méthode fonctionne aussi bien pour les géométries 2 D que 3 D.

## Prérequis
Avant de plonger dans le code, assurez‑vous d'avoir :

1. **Aspose.GIS for .NET** – téléchargez-le depuis le [site Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (ou .NET Core) installé sur votre machine de développement.  
3. **Visual Studio** (ou tout IDE compatible C#) pour écrire et exécuter l'exemple.

## Importer les espaces de noms
Pour commencer à utiliser les fonctionnalités d'Aspose.GIS, importez les espaces de noms requis.

### Espaces de noms principaux d'Aspose.GIS
L'espace de noms `Aspose.Gis` contient les classes de géométrie de base, les pilotes et les utilitaires nécessaires à toutes les opérations GIS.  
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Pilote pour le format cible
`Aspose.Gis.Drivers` fournit des usines statiques pour chaque format de fichier supporté ; `Drivers.Kml` crée un écrivain KML.  
```csharp
using Aspose.GIS.Kml;
```

## Guide étape par étape pour convertir les courbes en lignes
Ci-dessous se trouve une explication détaillée de chaque ligne de code, expliquant **comment convertir les courbes en lignes** et pourquoi chaque étape est importante.

### Étape 1 : Définir le chemin de sortie
`Path.Combine` construit un chemin de fichier indépendant de la plateforme, gérant automatiquement les barres obliques inverses Windows et les barres obliques Unix.  
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Remplacez `"Your Document Directory"` par le dossier où vous souhaitez enregistrer le fichier KML.

### Étape 2 : Créer une couche pour le fichier de sortie
Une *couche* regroupe des entités géographiques du même type. Ici nous créons une nouvelle couche KML qui stockera la géométrie linéarisée.  
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```

### Étape 3 : Construire une nouvelle entité
Une *entité* représente un objet géographique unique (point, ligne, polygone, etc.). Nous attacherons notre géométrie linéaire à cette entité.  
```csharp
var feature = layer.ConstructFeature();
```

### Étape 4 : Définir la géométrie complexe originale
`Geometry.FromWkt` analyse une chaîne Well‑Known Text (WKT) en un objet géométrique. Le WKT d'exemple comprend un `LineString`, un `CompoundCurve` et un `CircularString` pour illustrer la gestion des courbes.  
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```

### Étape 5 : Convertir les courbes en lignes
`ToLinearGeometry()` tesselle chaque courbe de la géométrie source en segments de ligne droite, renvoyant une nouvelle géométrie linéaire qui conserve les coordonnées Z.  
```csharp
var linear = geometry.ToLinearGeometry();
```

### Étape 6 : Assigner la géométrie linéaire à l'entité
La propriété `Geometry` de l'entité contient maintenant la version simplifiée et linéaire de la forme originale.  
```csharp
feature.Geometry = linear;
```

### Étape 7 : Ajouter l'entité à la couche
Ajouter l'entité à la couche KML la place dans la file d'attente d'écriture ; lorsque le bloc `using` se termine, la couche vide les données dans le fichier de sortie.  
```csharp
layer.Add(feature);
```

## Pièges courants et astuces professionnelles
- **Séparateurs de chemin :** Utilisez `Path.Combine` pour éviter les problèmes sous Windows vs. Linux.  
- **Géométries très volumineuses :** La linéarisation de formes complexes peut générer des milliers de sommets ; envisagez d'appeler `Simplify()` après la linéarisation pour réduire le nombre de points.  
- **Sélection du pilote :** Si vous avez besoin d'un format de sortie différent, remplacez `Drivers.Kml` par `Drivers.Shapefile`, `Drivers.GeoJson`, etc., et modifiez l'extension du fichier en conséquence.  
- **Préservation des valeurs Z :** `ToLinearGeometry()` conserve les coordonnées 3 D (Z), vous ne perdez donc pas les données d'élévation.

## Questions fréquemment posées (FAQ)

**Q : Aspose.GIS pour .NET est‑il compatible avec .NET Core ?**  
R : Oui, Aspose.GIS fonctionne avec .NET Core, permettant des applications multiplateformes.

**Q : Puis‑je travailler avec différents formats de fichiers GIS en utilisant Aspose.GIS pour .NET ?**  
R : Absolument ! La bibliothèque prend en charge KML, Shapefile, GeoJSON et bien d’autres formats — plus de 30 au total.

**Q : Aspose.GIS propose‑t‑il des opérations et analyses spatiales ?**  
R : Oui, elle offre un large éventail de fonctions spatiales, du buffering aux jointures spatiales.

**Q : Une version d'essai gratuite est‑elle disponible ?**  
R : Oui, vous pouvez télécharger une version d'essai gratuite depuis le [site Aspose.GIS](https://releases.aspose.com/gis/net/).

**Q : Où puis‑je obtenir de l'aide en cas de problème ?**  
R : Consultez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le support communautaire et du personnel.

### Questions supplémentaires courantes

**Q : Puis‑je linéariser des géométries contenant des coordonnées 3D (Z) ?**  
R : Oui, `ToLinearGeometry()` fonctionne avec les géométries 2D et 3D ; les valeurs Z sont conservées.

**Q : Comment la linéarisation affecte‑t‑elle la taille du fichier ?**  
R : Convertir les courbes en de nombreux courts segments de ligne peut augmenter la taille du fichier ; exécutez `Simplify()` après la linéarisation si la taille est un problème.

**Q : Puis‑je contrôler la longueur des segments lors de la conversion des courbes en lignes ?**  
R : La méthode par défaut utilise une tolérance interne. Pour une segmentation personnalisée, vous pouvez tesseller manuellement les courbes avant d’appeler `ToLinearGeometry()`.

## Conclusion
Dans ce tutoriel, nous avons couvert **comment convertir les courbes en lignes** (linéariser la géométrie) en utilisant Aspose.GIS pour .NET, depuis la configuration de l'environnement jusqu'à l'écriture du résultat linéarisé dans un fichier KML. Vous pouvez désormais intégrer ce flux de travail dans des applications de cartographie, des pipelines de traitement de données ou tout projet lié au GIS nécessitant des géométries simplifiées.

---

**Dernière mise à jour:** 2026-09-10  
**Testé avec:** Aspose.GIS 24.11 for .NET  
**Auteur:** Aspose

## Tutoriels associés

- [Comment créer du GeoJSON avec tolérance Aspose.GIS pour .NET](/gis/net/geometry-processing/set-linearization-tolerance/)
- [Convertir un polygone en ligne avec Aspose.GIS pour .NET](/gis/net/geometry-processing/replace-polygons-with-lines/)
- [Apprendre à créer une géométrie LineString avec Aspose.GIS pour .NET](/gis/net/geometry-creation/create-linestring-geometry/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}