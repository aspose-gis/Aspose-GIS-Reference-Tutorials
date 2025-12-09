---
date: 2025-12-06
description: Apprenez à créer un LineString en C# avec Aspose.GIS pour .NET, à ajouter
  des points à un LineString et à vérifier si une géométrie couvre une autre.
linktitle: Create LineString C# – Check Geometry Covers Another
second_title: Aspose.GIS .NET API
title: Créer un LineString C# – Vérifier si la géométrie couvre une autre
url: /fr/net/geometry-analysis/check-geometry-covers-another/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vérifier si une géométrie couvre une autre

## Introduction
Aspose.GIS for .NET est une bibliothèque puissante qui fournit aux développeurs des outils pour travailler efficacement avec des données géographiques au sein de leurs applications .NET. Que vous construisiez une application de cartographie, analysiez des données spatiales ou intégriez des fonctionnalités géographiques dans votre logiciel, Aspose.GIS offre un ensemble complet de fonctionnalités pour rationaliser votre processus de développement. Dans ce tutoriel, vous apprendrez **comment créer un LineString en C#**, ajouter des points à la ligne, et effectuer une **vérification du point sur la ligne** à l’aide des méthodes `Covers` et `CoveredBy`.

## Réponses rapides
- **Que signifie « créer un LineString en C# » ?** Cela signifie instancier un objet géométrique `LineString` et le remplir avec des points de coordonnées.  
- **Quelle méthode vérifie si un point se trouve sur une ligne ?** Utilisez la méthode `Covers` sur le `LineString` ou `CoveredBy` sur le `Point`.  
- **Ai‑je besoin d’une licence pour exécuter l’exemple ?** Une licence temporaire fonctionne pour l’évaluation ; une licence complète est requise pour la production.  
- **Cette fonctionnalité peut‑elle être utilisée avec .NET Core ?** Oui, Aspose.GIS prend en charge le .NET Framework et le .NET Core.  
- **ien de points puis‑je ajouter à un LineString ?** Il n’y a pas de limite stricte ; vous pouvez ajouter autant de points que nécessaire pour votre analyse spatiale.

## Qu’est‑ce que **créer un LineString C#** ?
Un `LineString` est une forme géométrique constituée d’une liste ordonnée de points reliés par des segments de ligne droits. En C# vous le créez en instanciant la classe `LineString` du namespace `Aspose.Gis.Geometries` puis en **ajoutant des points au LineString** à l’aide de la méthode `AddPoint`.

## Pourquoi utiliser Aspose.GIS pour une vérification point sur ligne ?
- **Précision** – Gère les calculs en virgule flottante et les prédicats spatiaux avec exactitude.  
- **Multi‑plateforme** – Fonctionne avec le .NET Framework, le .NET Core et le .NET 5/6+.  
- **API riche** – Fournit une suite complète de méthodes de relation spatiale (`Covers`, `CoveredBy`, `Intersects`, etc.).  

## Prérequis
Avant de plonger dans l’utilisation d’Aspose.GIS pour .NET, assurez‑vous que les prérequis suivants sont en place :

### 1. Installer Visual Studio
Assurez‑vous d’avoir Visual Studio installé sur votre système. Aspose.GIS for .NET s’intègre parfaitement à Visual Studio, offrant une expérience de développement fluide.

### 2. Obtenir Aspose.GIS pour .NET
Téléchargez la bibliothèque Aspose.GIS for .NET depuis le [site web](https://releases.aspose.com/gis/net/). Vous pouvez soit télécharger la bibliothèque directement, soit utiliser un gestionnaire de paquets comme NuGet pour l’installer dans votre projet.

### 3. Familiarité avec le .NET Framework
Une connaissance de base du framework .NET et du langage de programmation C# est essentielle pour exploiter efficacement Aspose.GIS for .NET.

### 4. Accès à la documentation et au support
Consultez la [documentation](https://reference.aspose.com/gis/net/) pour obtenir des informations détaillées sur les API et les fonctionnalités d’Aspose.GIS. En cas de problème ou de question, utilisez le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33) pour obtenir de l’aide.

### 5. Optionnel : licence temporaire
Si vous explorez Aspose.GIS for .NET, vous pouvez obtenir une licence temporaire depuis [ici](https://purchase.aspose.com/temporary-license/) pour évaluer les fonctionnalités de la bibliothèque.

## Importer les espaces de noms
Avant d’utiliser Aspose.GIS for .NET dans votre projet, vous devez importer les espaces de noms nécessaires :

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Maintenant, décomposons l’exemple fourni en plusieurs étapes afin de comprendre comment **vérifier si une géométrie couvre une autre** à l’aide d’Aspose.GIS for .NET.

## Comment **créer un LineString C#** – Guide étape par étape

### Étape 1 : Créer un objet LineString
```csharp
var line = new LineString();
```
Ici, nous instancions un nouvel objet `LineString`, qui représente une séquence de segments de ligne connectés dans un espace bidimensionnel.

### Étape 2 : **Ajouter des points au LineString**
```csharp
line.AddPoint(0, 0);
line.AddPoint(1, 1);
```
Nous **ajoutons des points au LineString** à l’aide de la méthode `AddPoint`. Dans cet exemple, nous ajoutons deux points : (0, 0) et (1, 1), formant un simple segment de ligne diagonal.

### Étape 3 : Créer un objet Point
```csharp
var point = new Point(0, 0);
```
Instanciez un objet `Point` représentant un point unique dans un espace bidimensionnel. Ici, nous créons un point aux coordonnées (0, 0).

### Étape 4 : Effectuer une **vérification du point sur la ligne** – La ligne couvre‑t‑elle le point ?
```csharp
Console.WriteLine(line.Covers(point));    // True
```
Utilisez la méthode `Covers` pour vérifier si la ligne couvre le point. Dans ce cas, elle renvoie `True` car le point (0, 0) se trouve exactement sur la ligne.

### Étape 5 : Vérifier la relation inverse – Le point est‑il couvert par la ligne ?
```csharp
Console.WriteLine(point.CoveredBy(line)); // True
```
De même, utilisez la méthode `CoveredBy` pour vérifier si le point est couvert par la ligne. Puisque le point (0, 0) se trouve sur la ligne, elle renvoie également `True`.

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| `line.Covers(point)` renvoie `False` même si le point semble être sur la ligne | Les coordonnées du point ne sont pas exactement les mêmes en raison de la précision des nombres à virgule flottante. | Utilisez `Math.Round` sur les coordonnées ou effectuez une vérification basée sur une tolérance avec `line.Distance(point) < epsilon`. |
| `using Aspose.Gis.Geometries;` manquant | L'espace de noms n'est pas importé, ce qui provoque des erreurs de compilation. | Assurez‑vous que l’instruction d’importation est présente (voir la section **Importer les espaces de noms**). |
| Exception de licence à l’exécution | Aucune licence valide n’est chargée pour la production. | Chargez une licence temporaire ou complète avec `License license = new License(); license.SetLicense("Aspose.GIS.lic");`. |

## Questions fréquentes

**Q : Puis‑je utiliser Aspose.GIS pour .NET dans mes projets commerciaux ?**  
R : Oui, vous pouvez utiliser Aspose.GIS pour .NET dans des projets commerciaux et non commerciaux après avoir obtenu la licence appropriée.

**Q : Aspose.GIS pour .NET est‑il compatible avec .NET Core ?**  
R : Oui, Aspose.GIS pour .NET est compatible à la fois avec le .NET Framework et les environnements .NET Core.

**Q : Aspose.GIS pour .NET prend‑il en charge différents formats GIS ?**  
R : Oui, Aspose.GIS pour .NET prend en charge un large éventail de formats GIS, notamment Shapefile, GeoJSON, KML, et bien d’autres.

**Q : Puis‑je contribuer au développement d’Aspose.GIS pour .NET ?**  
R : Aspose.GIS pour .NET est une bibliothèque propriétaire développée par Aspose, les contributions externes ne sont donc pas acceptées. Vous pouvez toutefois fournir des retours et suggestions pour améliorer la bibliothèque.

**Q : À quelle fréquence les mises à jour d’Aspose.GIS pour .NET sont‑elles publiées ?**  
R : Les mises à jour d’Aspose.GIS pour .NET sont publiées régulièrement afin d’ajouter de nouvelles fonctionnalités, des améliorations et des corrections de bugs. Consultez le [site web](https://releases.aspose.com/gis/net/) pour les dernières versions.

## Conclusion
En conclusion, Aspose.GIS for .NET fournit des outils puissants pour travailler avec des données géographiques dans les applications .NET. En suivant les étapes décrites ci‑dessus, vous pouvez efficacement **créer un LineString en C#**, **ajouter des points au LineString**, et effectuer une **vérification du point sur la ligne** pour déterminer si une géométrie couvre une autre. Cette capacité améliore les fonctionnalités d’analyse spatiale de votre logiciel et ouvre la porte à des opérations GIS plus avancées.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2025-12-06  
**Testé avec :** Aspose.GIS for .NET (latest release)  
**Auteur :** Aspose