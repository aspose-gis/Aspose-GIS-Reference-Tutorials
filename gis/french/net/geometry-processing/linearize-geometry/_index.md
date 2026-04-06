---
date: 2026-04-06
description: Apprenez à convertir les courbes en lignes et à linéariser la géométrie
  avec Aspose.GIS pour .NET, permettant un traitement et une analyse géospatiaux rapides
  dans vos applications .NET.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS linearize geometry
linktitle: Linéariser une géométrie
second_title: Aspose.GIS .NET API
title: Convertir les courbes en lignes à l'aide d'Aspose.GIS pour .NET
url: /fr/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir des courbes en lignes avec Aspose.GIS pour .NET

## Introduction
Si vous devez **convertir des courbes en lignes** pour la cartographie, l'analyse spatiale ou les tâches d'échange de données, Aspose.GIS pour .NET vous offre une méthode propre et programmatique pour le faire. Dans ce tutoriel, nous parcourrons un exemple complet et réel qui montre comment prendre une géométrie complexe — contenant des courbes et des formes composées — et la transformer en une représentation linéaire simple qui fonctionne avec n'importe quel système SIG.

## Réponses rapides
- **Que signifie la linéarisation d’une géométrie ?** Conversion des courbes et des formes complexes en segments de ligne droite.  
- **Pourquoi utiliser Aspose.GIS ?** Il prend en charge des dizaines de formats SIG et gère la conversion de géométrie sans outils externes.  
- **Prérequis ?** .NET Framework ou .NET Core, Visual Studio et la bibliothèque Aspose.GIS.  
- **Combien de temps prend l’exemple ?** Moins de cinq minutes à exécuter une fois la bibliothèque installée.  
- **Puis-je enregistrer dans d’autres formats ?** Oui — remplacez le pilote KML par Shapefile, GeoJSON, etc.

## Qu’est‑ce que la linéarisation de la géométrie ?
La linéarisation de la géométrie consiste à décomposer toute forme courbe ou composite en une série de segments de ligne droite (une « géométrie linéaire »). Cela simplifie le rendu, l’analyse et l’interopérabilité avec les outils qui ne comprennent que les lignes et les points.

## Pourquoi convertir des courbes en lignes ?
- **Performance :** Les géométries linéaires sont plus rapides à rendre et à interroger.  
- **Compatibilité :** De nombreuses plateformes SIG (par ex., les services de cartes anciens) n’acceptent que des entités linéaires.  
- **Simplification :** Utile pour créer des vignettes, des aperçus rapides ou alimenter des algorithmes qui nécessitent des entrées linéaires.

## Prérequis
Avant de plonger dans le code, assurez‑vous d'avoir :

1. **Aspose.GIS for .NET** – téléchargez‑le depuis le site [Aspose.GIS website](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (ou .NET Core) installé sur votre machine de développement.  
3. **Visual Studio** (ou tout IDE compatible C#) pour écrire et exécuter l’exemple.

## Importer les espaces de noms
Pour commencer à utiliser les fonctionnalités d’Aspose.GIS, importez les espaces de noms requis.

### Étape 1 : Importer les espaces de noms principaux d’Aspose.GIS
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Étape 2 : Importer le pilote pour le format cible
Pour cet exemple, nous écrirons le résultat dans un fichier KML :
```csharp
using Aspose.GIS.Kml;
```

## Comment convertir des courbes en lignes – Guide étape par étape
Voici une explication détaillée de chaque ligne de code, expliquant **comment convertir des courbes en lignes** et pourquoi chaque étape est importante.

### Étape 1 : Définir le chemin de sortie
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Remplacez `"Your Document Directory"` par le dossier où vous souhaitez enregistrer le fichier KML.

### Étape 2 : Créer une couche pour le fichier de sortie
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
Une *couche* est un conteneur d’entités géographiques. Ici, nous créons une nouvelle couche KML qui contiendra notre géométrie linéarisée.

### Étape 3 : Construire une nouvelle entité
```csharp
var feature = layer.ConstructFeature();
```
Une *entité* représente un seul objet géographique (point, ligne, polygone, etc.). Nous attacherons notre géométrie linéaire à cette entité.

### Étape 4 : Définir la géométrie complexe originale
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Nous créons une géométrie à partir d’une chaîne Well‑Known Text (WKT). Cet exemple comprend un `LineString`, un `CompoundCurve` et un `CircularString` — parfait pour démontrer la conversion de courbes en lignes.

### Étape 5 : Linéariser la géométrie
```csharp
var linear = geometry.ToLinearGeometry();
```
La méthode `ToLinearGeometry()` convertit toutes les courbes en segments de ligne droite, produisant une version *linéaire* de la géométrie originale.

### Étape 6 : Assigner la géométrie linéaire à l’entité
```csharp
feature.Geometry = linear;
```
L’entité contient maintenant la géométrie simplifiée et linéaire.

### Étape 7 : Ajouter l’entité à la couche
```csharp
layer.Add(feature);
```
Enfin, nous ajoutons l’entité à la couche KML, qui écrit la géométrie linéaire dans le fichier de sortie lorsque le bloc `using` se termine.

## Pièges courants et astuces
- **Séparateurs de chemin :** Utilisez `Path.Combine` pour la construction de chemins multiplateforme.  
- **Géométries volumineuses :** Linéariser des formes très complexes peut générer de nombreux sommets ; envisagez d’utiliser `Simplify()` après la linéarisation si vous avez besoin de moins de points.  
- **Sélection du pilote :** Si vous avez besoin d’un format de sortie différent, remplacez `Drivers.Kml` par `Drivers.Shapefile`, `Drivers.GeoJson`, etc., et ajustez l’extension du fichier en conséquence.

## Questions fréquemment posées (améliorées)

**Q : Aspose.GIS pour .NET est‑il compatible avec .NET Core ?**  
R : Oui, Aspose.GIS pour .NET fonctionne avec .NET Core, vous permettant de créer des applications multiplateformes.

**Q : Puis‑je travailler avec différents formats de fichiers GIS en utilisant Aspose.GIS pour .NET ?**  
R : Absolument ! Aspose.GIS prend en charge KML, Shapefile, GeoJSON et de nombreux autres formats.

**Q : Aspose.GIS propose‑t‑il une prise en charge des opérations et analyses spatiales ?**  
R : Oui, il offre un large éventail d’opérations et de capacités d’analyse spatiale pour gérer des tâches géospatiales complexes.

**Q : Existe‑t‑il une version d’essai gratuite d’Aspose.GIS pour .NET ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite depuis le site [Aspose website](https://releases.aspose.com/).

**Q : Où puis‑je trouver de l’aide et du support pour Aspose.GIS ?**  
R : Consultez le [Aspose.GIS forum](https://forum.aspose.com/c/gis/33) pour obtenir de l’assistance de la communauté et du personnel de support d’Aspose.

**Questions supplémentaires**

**Q : Puis‑je linéariser des géométries contenant des coordonnées 3D (Z) ?**  
R : Oui, `ToLinearGeometry()` fonctionne avec les géométries 2D et 3D ; les valeurs Z sont conservées dans les segments de ligne résultants.

**Q : Comment la linéarisation affecte‑t‑elle la taille du fichier de sortie ?**  
R : Convertir des courbes en de nombreux courts segments de ligne peut augmenter la taille du fichier. Utilisez `Simplify()` après la linéarisation si la taille du fichier est un problème.

**Q : Est‑il possible de contrôler la longueur des segments lors de la linéarisation ?**  
R : La méthode par défaut utilise une tolérance interne. Pour une segmentation personnalisée, vous pouvez tesselliser manuellement les courbes avant d’appeler `ToLinearGeometry()`.

## Conclusion
Dans ce tutoriel, nous avons couvert **comment convertir des courbes en lignes** avec Aspose.GIS pour .NET, depuis la configuration de l’environnement jusqu’à l’écriture du résultat linéarisé dans un fichier KML. Vous pouvez désormais intégrer ce flux de travail dans des applications cartographiques, des pipelines de traitement de données ou tout projet lié aux SIG nécessitant des géométries simplifiées.

---

**Dernière mise à jour :** 2026-04-06  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}