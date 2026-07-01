---
date: 2026-04-03
description: Apprenez à créer une géométrie de polygone avec trou en utilisant Aspose.GIS
  pour .NET. Ce guide vous montre comment créer un trou dans un polygone et travailler
  avec des données géospatiales.
keywords:
- create polygon with hole
- add hole to polygon
- Aspose.GIS polygon geometry
linktitle: Créer un polygone avec trou
second_title: Aspose.GIS .NET API
title: Créer un polygone avec trou géométrique à l'aide d'Aspose.GIS
url: /fr/net/geometry-creation/create-polygon-with-hole-geometry/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une géométrie de polygone avec trou à l'aide d'Aspose.GIS

## Introduction
Dans ce tutoriel, vous **créerez une géométrie de polygone avec trou** à l'aide d'Aspose.GIS pour .NET. Que vous développiez une application cartographique, effectuiez une analyse spatiale ou prépariez des données pour des services GIS, savoir comment intégrer un trou à l'intérieur d'un polygone est essentiel. Nous parcourrons l'ensemble du processus étape par étape, depuis la configuration de l'environnement jusqu'à la génération de l'objet polygone final.

## Réponses rapides
- **Que signifie « créer un polygone avec trou » ?** Cela signifie créer un polygone contenant un ou plusieurs anneaux intérieurs (trous) qui sont exclus de la surface.  
- **Quelle bibliothèque gère cela ?** Aspose.GIS pour .NET offre une prise en charge complète des anneaux extérieurs et intérieurs.  
- **Ai‑je besoin d’une licence ?** Une version d'essai gratuite suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Combien de temps cela prend‑il ?** Typiquement moins de 10 minutes pour implémenter et tester.

## Comment ajouter un trou à un polygone avec Aspose.GIS
Ajouter un trou consiste simplement à définir un **anneau intérieur** et à l'attacher au polygone. La bibliothèque se charge de l'orientation et de la validité, vous permettant ainsi de vous concentrer sur les coordonnées qui représentent le vide souhaité.

## Qu’est‑ce que « créer un polygone avec trou » ?
Créer un polygone avec un trou implique de définir un **anneau extérieur** qui délimite la frontière extérieure et un ou plusieurs **anneaux intérieurs** qui créent des espaces vides. Les anneaux intérieurs sont souvent appelés *trous* car ils représentent des zones qui ne font pas partie de la surface du polygone.

## Pourquoi créer un trou dans un polygone avec Aspose.GIS ?
- **Modélisation spatiale précise :** Des caractéristiques du monde réel comme des lacs à l'intérieur de parcelles ou des cours intérieures de bâtiments nécessitent des trous.  
- **Interopérabilité :** Des formats tels que Shapefile, GeoJSON et GML supportent nativement les anneaux intérieurs ; Aspose.GIS les préserve.  
- **Performance :** La bibliothèque gère la validité de la géométrie, vous n’avez donc pas à écrire du code de validation personnalisé.

## Scénarios réels pour les polygones avec trous
1. **Parcelle de terrain avec un lac interne** – le lac est modélisé comme un trou afin de ne pas être compté dans la surface de la parcelle.  
2. **Empreintes de bâtiments avec cours intérieures** – la cour est exclue de l'empreinte du bâtiment.  
3. **Zones protégées à l'intérieur d'une plus grande zone de conservation** – vous pouvez exclure des sections restreintes sans créer de couches séparées.

## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Bibliothèque Aspose.GIS pour .NET : Vous pouvez la télécharger depuis [ici](https://releases.aspose.com/gis/net/).  
2. Environnement de développement : Assurez‑vous d'avoir un environnement de développement configuré avec Visual Studio ou tout autre IDE .NET installé.

## Importer les espaces de noms
Tout d'abord, vous devez importer les espaces de noms nécessaires pour travailler avec les fonctionnalités d'Aspose.GIS. Voici comment procéder :

```csharp
using Aspose.Gis.Geometries;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Passons maintenant à la création d'une géométrie de polygone avec trou à l'aide d'Aspose.GIS pour .NET.

## Étape 1 : Créer l'objet Polygon
Nous commençons par instancier un objet `Polygon` vide qui contiendra ultérieurement à la fois les anneaux extérieurs et intérieurs.

```csharp
Polygon polygon = new Polygon();
```

## Étape 2 : Définir l'anneau extérieur
L'anneau extérieur définit la frontière extérieure du polygone. Ajoutez les points dans le sens horaire pour former une forme fermée.

```csharp
LinearRing ring = new LinearRing();
ring.AddPoint(50.02, 36.22);
ring.AddPoint(49.99, 36.26);
ring.AddPoint(49.97, 36.23);
ring.AddPoint(49.98, 36.17);
ring.AddPoint(50.02, 36.22);
```

## Étape 3 : Définir l'anneau intérieur (trou)
Ensuite, nous créons un anneau intérieur — il s'agit du **trou** qui sera exclu de la surface du polygone. Les points sont généralement ajoutés dans le sens antihoraire, mais Aspose.GIS gère automatiquement l'orientation.

```csharp
LinearRing hole = new LinearRing();
hole.AddPoint(50.00, 36.22);
hole.AddPoint(49.99, 36.20);
hole.AddPoint(49.98, 36.23);
hole.AddPoint(50.00, 36.24);
hole.AddPoint(50.00, 36.22);
```

## Étape 4 : Attribuer l'anneau extérieur et ajouter l'anneau intérieur au polygone
Enfin, attachez l'anneau extérieur au polygone puis ajoutez l'anneau intérieur (le trou). La méthode `AddInteriorRing` peut être appelée plusieurs fois si vous avez besoin de plusieurs trous.

```csharp
polygon.ExteriorRing = ring;
polygon.AddInteriorRing(hole);
```

## Conseils et bonnes pratiques
- **L'orientation est importante pour la lisibilité** – bien qu'Aspose.GIS corrige automatiquement l'orientation, garder les anneaux extérieurs dans le sens horaire et les anneaux intérieurs dans le sens antihoraire facilite l'inspection de la géométrie dans les visionneuses GIS.  
- **Fermez chaque anneau** – répétez toujours la première coordonnée comme dernier point ; cela garantit une forme fermée valide.  
- **Validez après création** – vous pouvez appeler `polygon.IsValid` pour vous assurer que la géométrie respecte les normes OGC avant l'enregistrement.

## Problèmes courants et solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| Le trou n'apparaît pas dans le visualiseur GIS | Orientation de l'anneau intérieur inversée | Assurez‑vous que les points sont ajoutés dans le sens opposé de l'anneau extérieur (antihoraire). |
| Erreur de polygone invalide | Anneaux non fermés (premier ≠ dernier point) | Répétez le premier point comme dernier point dans chaque anneau (comme indiqué ci‑dessus). |
| Géométrie vide inattendue | Oublier d'assigner `ExteriorRing` avant d'ajouter les anneaux intérieurs | Définissez d'abord `polygon.ExteriorRing`, puis appelez `AddInteriorRing`. |

## Foire aux questions
### 1. Qu’est‑ce qu’Aspose.GIS ?
Aspose.GIS est une bibliothèque .NET qui permet aux développeurs de travailler avec des données géospatiales, leur offrant la possibilité de créer, lire et manipuler divers formats de fichiers géospatiaux.

### 2. Puis‑je utiliser Aspose.GIS pour des projets commerciaux ?
Oui, vous pouvez utiliser Aspose.GIS pour des projets personnels et commerciaux en achetant une licence. Visitez [ici](https://purchase.aspose.com/buy) pour plus de détails.

### 3. Existe‑t‑il une version d'essai gratuite d'Aspose.GIS ?
Oui, vous pouvez profiter d'une version d'essai gratuite d'Aspose.GIS depuis [ici](https://releases.aspose.com/).

### 4. Où puis‑je trouver du support pour Aspose.GIS ?
Vous pouvez trouver du support pour Aspose.GIS sur le [forum Aspose.GIS](https://forum.aspose.com/c/gis/33).

### 5. Comment obtenir une licence temporaire pour Aspose.GIS ?
Vous pouvez obtenir une licence temporaire pour Aspose.GIS depuis [ici](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour :** 2026-04-03  
**Testé avec :** Aspose.GIS 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}