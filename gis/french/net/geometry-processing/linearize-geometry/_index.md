---
date: 2025-12-21
description: Apprenez à linéariser la géométrie avec Aspose.GIS pour .NET, permettant
  un traitement efficace des données géospatiales, l'analyse spatiale et la manipulation
  de géométrie dans vos applications .NET.
linktitle: Linearize a Geometry
second_title: Aspose.GIS .NET API
title: Comment linéariser la géométrie avec Aspose.GIS pour .NET
url: /fr/net/geometry-processing/linearize-geometry/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Linéariser une Géométrie

## Introduction
Si vous avez besoin de **savoir comment linéariser une géométrie** pour la cartographie, l'analyse spatiale ou les tâches d'échange de données, Aspose.GIS pour .NET vous offre une méthode propre et programmatique pour le faire. Dans ce tutoriel, nous parcourrons un exemple complet et réel qui montre comment prendre une géométrie complexe — contenant des courbes et des formes composées — et la transformer en une représentation linéaire simple qui fonctionne avec n'importe quel système SIG.

## Réponses rapides
- **Que signifie linéariser une géométrie ?** Convertir les courbes et les formes complexes en segments de ligne droite.  
- **Pourquoi utiliser Aspose.GIS ?** Il prend en charge des dizaines de formats SIG et gère la conversion de géométrie sans outils externes.  
- **Prérequis ?** .NET Framework ou .NET Core, Visual Studio et la bibliothèque Aspose.GIS.  
- **Combien de temps prend l'exemple ?** Moins de cinq minutes à exécuter une fois la bibliothèque installée.  
- **Puis-je enregistrer dans d'autres formats ?** Oui — remplacez le pilote KML par Shapefile, GeoJSON, etc.

## Qu'est-ce que la linéarisation de géométrie ?
Linéariser une géométrie consiste à décomposer toute forme courbe ou composite en une série de segments de ligne droite (une « géométrie linéaire »). Cela simplifie le rendu, l'analyse et l'interopérabilité avec les outils qui ne comprennent que les lignes et les points.

## Pourquoi linéariser une géométrie ?
- **Performance :** Les géométries linéaires sont plus rapides à rendre et à interroger.  
- **Compatibilité :** De nombreuses plateformes SIG (par ex., les services de cartes anciens) n'acceptent que des entités linéaires.  
- **Simplification :** Utile pour créer des vignettes, des aperçus rapides ou alimenter des algorithmes qui nécessitent des entrées linéaires.

## Prérequis
Avant de plonger dans le code, assurez-vous d'avoir :

1. **Aspose.GIS pour .NET** – téléchargez-le depuis le [site Web Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (ou .NET Core) installé sur votre machine de développement.  
3. **Visual Studio** (ou tout IDE compatible C#) pour écrire et exécuter l'exemple.

## Importer les espaces de noms
Pour commencer à utiliser les fonctionnalités d'Aspose.GIS, importez les espaces de noms requis.

### Étape 1 : Importer les espaces de noms principaux d'Aspose.GIS
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

## Comment linéariser une géométrie – Guide étape par étape
Ci-dessous se trouve une explication détaillée de chaque ligne de code, expliquant **comment linéariser une géométrie** et pourquoi chaque étape est importante.

### Étape 1 : Définir le chemin de sortie
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Remplacez `"Your Document Directory"` par le dossier où vous souhaitez enregistrer le fichier KML.

### Étape 2 : Créer une couche pour le fichier de sortie
```csharp
using (var layer = Drivers.Kml.CreateLayer(path))
```
Une *couche* est un conteneur pour les entités géographiques. Ici, nous créons une nouvelle couche KML qui contiendra notre géométrie linéarisée.

### Étape 3 : Construire une nouvelle entité
```csharp
var feature = layer.ConstructFeature();
```
Une *entité* représente un objet géographique unique (point, ligne, polygone, etc.). Nous attacherons notre géométrie linéaire à cette entité.

### Étape 4 : Définir la géométrie complexe originale
```csharp
var geometry = Geometry.FromText(@"GeometryCollection (LineString (0 0, 1 1, 2 0),CompoundCurve ((4 0, 5 1), CircularString (5 1, 6 2, 7 1)))");
```
Nous créons une géométrie à partir d'une chaîne Well‑Known Text (WKT). Cet exemple inclut un `LineString`, un `CompoundCurve` et un `CircularString` — parfait pour démontrer la linéarisation.

### Étape 5 : Linéariser la géométrie
```csharp
var linear = geometry.ToLinearGeometry();
```
La méthode `ToLinearGeometry()` convertit toutes les courbes en segments de ligne droite, produisant une version *linéaire* de la géométrie originale.

### Étape 6 : Assigner la géométrie linéaire à l'entité
```csharp
feature.Geometry = linear;
```
L'entité détient maintenant la géométrie simplifiée et linéaire.

### Étape 7 : Ajouter l'entité à la couche
```csharp
layer.Add(feature);
```
Enfin, nous ajoutons l'entité à la couche KML, qui écrit la géométrie linéaire dans le fichier de sortie lorsque le bloc `using` se termine.

## Pièges courants et conseils
- **Séparateurs de chemin :** Utilisez `Path.Combine` pour la construction de chemins multiplateformes.  
- **Géométries volumineuses :** Linéariser des formes très complexes peut produire de nombreux sommets ; envisagez d'utiliser `Simplify()` après la linéarisation si vous avez besoin de moins de points.  
- **Sélection du pilote :** Si vous avez besoin d'un format de sortie différent, remplacez `Drivers.Kml` par `Drivers.Shapefile`, `Drivers.GeoJson`, etc., et ajustez l'extension du fichier en conséquence.

## Conclusion
Dans ce tutoriel, nous avons couvert **comment linéariser une géométrie** en utilisant Aspose.GIS pour .NET, depuis la configuration de l'environnement jusqu'à l'écriture du résultat linéarisé dans un fichier KML. Vous pouvez désormais intégrer ce flux de travail dans des applications de cartographie, des pipelines de traitement de données ou tout projet lié aux SIG nécessitant des géométries simplifiées.

## FAQ
### Q : Aspose.GIS pour .NET est‑il compatible avec .NET Core ?
Oui, Aspose.GIS pour .NET est compatible avec .NET Core, vous permettant de créer des applications multiplateformes.

### Q : Puis‑je travailler avec différents formats de fichiers GIS en utilisant Aspose.GIS pour .NET ?
Absolument ! Aspose.GIS prend en charge divers formats de fichiers GIS, y compris KML, Shapefile, GeoJSON, et plus encore.

### Q : Aspose.GIS offre‑t‑il un support pour les opérations et analyses spatiales ?
Oui, Aspose.GIS fournit une large gamme d'opérations et de capacités d'analyse spatiale pour gérer des tâches géospatiales complexes.

### Q : Existe‑t‑il un essai gratuit pour Aspose.GIS pour .NET ?
Oui, vous pouvez télécharger un essai gratuit depuis le [site Web Aspose](https://releases.aspose.com/).

### Q : Où puis‑je trouver de l'aide et du support pour Aspose.GIS ?
Vous pouvez visiter le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour obtenir de l'aide de la communauté et du personnel de support d'Aspose.

## Questions fréquemment posées (supplémentaires)

**Q : Puis‑je linéariser des géométries contenant des coordonnées 3D (Z) ?**  
R : Oui, `ToLinearGeometry()` fonctionne avec les géométries 2D et 3D ; les valeurs Z sont conservées dans les segments de ligne résultants.

**Q : Comment la linéarisation affecte‑t‑elle la taille du fichier de sortie ?**  
R : Convertir les courbes en de nombreux courts segments de ligne peut augmenter la taille du fichier. Utilisez `Simplify()` après la linéarisation si la taille du fichier est un problème.

**Q : Est‑il possible de contrôler la longueur des segments lors de la linéarisation ?**  
R : La méthode par défaut utilise une tolérance interne. Pour une segmentation personnalisée, vous pouvez tesselliser manuellement les courbes avant d'appeler `ToLinearGeometry()`.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.GIS 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}