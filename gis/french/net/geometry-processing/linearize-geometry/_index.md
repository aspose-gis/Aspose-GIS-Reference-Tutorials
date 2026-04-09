---
date: 2026-04-09
description: Apprenez à convertir les courbes en lignes (linéariser la géométrie)
  en utilisant Aspose.GIS pour .NET, permettant un traitement et une analyse géospatiaux
  efficaces dans vos applications .NET.
keywords:
- convert curves to lines
- how to linearize geometry
- Aspose.GIS .NET
linktitle: Linéariser une géométrie
second_title: Aspose.GIS .NET API
title: Comment convertir les courbes en lignes avec Aspose.GIS pour .NET
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
- **Que signifie « convertir des courbes en lignes » ?** Il transforme les géométries courbes en segments de ligne droite.  
- **Pourquoi choisir Aspose.GIS ?** La bibliothèque prend en charge des dizaines de formats GIS et gère la conversion de géométrie sans outils externes.  
- **De quoi ai‑je besoin au préalable ?** .NET Framework ou .NET Core, Visual Studio (ou tout IDE C#), et le package NuGet Aspose.GIS.  
- **Combien de temps le sample s'exécutera‑t‑il ?** Moins de cinq minutes une fois la bibliothèque installée.  
- **Puis‑je exporter vers d'autres formats ?** Absolument — remplacez le driver KML par Shapefile, GeoJSON, etc.

## Que signifie convertir des courbes en lignes ?
La conversion des courbes en lignes (également appelée **linéarisation de la géométrie**) décompose toute forme courbe ou composite en une série de segments de ligne droite, connue sous le nom de « géométrie linéaire ». Cette simplification rend le rendu plus rapide, améliore la compatibilité avec les services GIS anciens et réduit la complexité des algorithmes spatiaux.

## Pourquoi convertir des courbes en lignes ?
- **Performance :** Les géométries linéaires sont rendues et interrogées beaucoup plus rapidement.  
- **Compatibilité :** De nombreuses plateformes GIS (en particulier les services hérités) n'acceptent que des entités linéaires.  
- **Simplification :** Idéal pour les miniatures, les aperçus rapides ou l'alimentation de données dans des algorithmes nécessitant une entrée linéaire.

## Prérequis
Avant de plonger dans le code, assurez‑vous d'avoir :

1. **Aspose.GIS for .NET** – téléchargez‑le depuis le [site Web Aspose.GIS](https://releases.aspose.com/gis/net/).  
2. **.NET Framework** (ou .NET Core) installé sur votre machine de développement.  
3. **Visual Studio** (ou tout IDE compatible C#) pour écrire et exécuter l'exemple.

## Importer les espaces de noms
Pour commencer à utiliser les fonctionnalités d'Aspose.GIS, importez les espaces de noms requis.

### Étape 1 : Espaces de noms principaux d'Aspose.GIS
```csharp
using Aspose.Gis;
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

### Étape 2 : Pilote pour le format cible
Pour cet exemple, nous écrirons le résultat dans un fichier KML :
```csharp
using Aspose.GIS.Kml;
```

## Guide étape par étape pour convertir les courbes en lignes
Ci‑dessous se trouve une explication détaillée de chaque ligne de code, expliquant **comment convertir les courbes en lignes** et pourquoi chaque étape est importante.

### Étape 1 : Définir le chemin de sortie
```csharp
string path = "Your Document Directory" + "LinearizeGeometry_out.kml";
```
Remplacez `"Your Document Directory"` par le dossier où vous souhaitez enregistrer le fichier KML. L'utilisation de `Path.Combine` est recommandée pour la compatibilité multiplateforme.

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
Nous créons une géométrie à partir d'une chaîne Well‑Known Text (WKT). Cet exemple comprend un `LineString`, un `CompoundCurve` et un `CircularString` — parfait pour démontrer **convertir des courbes en lignes**.

### Étape 5 : Convertir les courbes en lignes
```csharp
var linear = geometry.ToLinearGeometry();
```
La méthode `ToLinearGeometry()` convertit toutes les courbes en segments de ligne droite, produisant une version *linéaire* de la géométrie originale.

### Étape 6 : Assigner la géométrie linéaire à l'entité
```csharp
feature.Geometry = linear;
```
L'entité contient maintenant la géométrie simplifiée et linéaire.

### Étape 7 : Ajouter l'entité à la couche
```csharp
layer.Add(feature);
```
Enfin, nous ajoutons l'entité à la couche KML, qui écrit la géométrie linéaire dans le fichier de sortie lorsque le bloc `using` se termine.

## Pièges courants et astuces professionnelles
- **Séparateurs de chemin :** Utilisez `Path.Combine` pour éviter les problèmes sous Windows vs. Linux.  
- **Géométries très volumineuses :** La linéarisation de formes complexes peut générer des milliers de sommets ; envisagez d'appeler `Simplify()` après la linéarisation pour réduire le nombre de points.  
- **Sélection du driver :** Si vous avez besoin d'un format de sortie différent, remplacez `Drivers.Kml` par `Drivers.Shapefile`, `Drivers.GeoJson`, etc., et modifiez l'extension du fichier en conséquence.  
- **Conservation des valeurs Z :** `ToLinearGeometry()` conserve les coordonnées 3‑D (Z), vous ne perdez donc pas les données d'élévation.

## Questions fréquemment posées (FAQ)

**Q : Aspose.GIS pour .NET est‑il compatible avec .NET Core ?**  
R : Oui, Aspose.GIS fonctionne avec .NET Core, permettant des applications multiplateformes.

**Q : Puis‑je travailler avec différents formats de fichiers GIS en utilisant Aspose.GIS pour .NET ?**  
R : Absolument ! La bibliothèque prend en charge KML, Shapefile, GeoJSON et bien d’autres formats.

**Q : Aspose.GIS propose‑t‑il des opérations et analyses spatiales ?**  
R : Oui, il offre un large éventail de fonctions spatiales, du tampon aux jointures spatiales.

**Q : Une version d'essai gratuite est‑elle disponible ?**  
R : Oui, vous pouvez télécharger une version d'essai gratuite depuis le [site Aspose](https://releases.aspose.com/).

**Q : Où puis‑je obtenir de l'aide en cas de problème ?**  
R : Consultez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour le support communautaire et du personnel.

### Questions supplémentaires courantes

**Q : Puis‑je linéariser des géométries contenant des coordonnées 3D (Z) ?**  
R : Oui, `ToLinearGeometry()` fonctionne avec les géométries 2D et 3D ; les valeurs Z sont conservées.

**Q : Comment la linéarisation affecte‑t‑elle la taille du fichier ?**  
R : Convertir des courbes en de nombreux courts segments de ligne peut augmenter la taille du fichier. Utilisez `Simplify()` après la linéarisation si la taille est un problème.

**Q : Puis‑je contrôler la longueur des segments lors de la conversion des courbes en lignes ?**  
R : La méthode par défaut utilise une tolérance interne. Pour une segmentation personnalisée, vous pouvez tesselliser manuellement les courbes avant d'appeler `ToLinearGeometry()`.

## Conclusion
Dans ce tutoriel, nous avons couvert **comment convertir des courbes en lignes** (linéariser la géométrie) en utilisant Aspose.GIS pour .NET, depuis la configuration de l'environnement jusqu'à l'écriture du résultat linéarisé dans un fichier KML. Vous pouvez désormais intégrer ce flux de travail dans des applications de cartographie, des pipelines de traitement de données ou tout projet lié au GIS nécessitant des géométries simplifiées.

---

**Dernière mise à jour :** 2026-04-09  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}